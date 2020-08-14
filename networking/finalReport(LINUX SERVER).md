###### tags: `Networking`, `Servers`, `Linux`
**Relatório final 5115 (LINUX SERVER)**
===
**Nome:** Duarte Matos
**Data:** 27/11/2018
**Turma:** GRSI0318B

![](https://i.imgur.com/FFmhoKc.png)


Criação de partições (==RAID==)
===

## O que é?

Em inglês **Redundant Array of Independent Disks**,é uma forma de fazer ==partições== entre os discos para obter maior ==confiabilidade==, maior capacidade de dados e também **redução de tempo** de acesso aos dados. 

**1.** Comecemos por instalar o **mdadm:**
```
yum install mdadm
```
![](https://i.imgur.com/GCzvLoh.png)


**2.** Após a instalação, iremos **listar** os discos que temos:
```
fdisk -l | grep sd
```
![](https://i.imgur.com/0vTectR.png)


**3.** Devemos agora **examinar** os discos:
```
mdadm -E /dev/sd[b-d]
```
![](https://i.imgur.com/KUGHvAO.png)


**4.** Antes de adicionarmos á ==**RAID**==, temos de definir a partição usando o comando “fdisk”:

**a)** Crie a partição ==**fdisk /dev/sdb**== em primeiro lugar e depois para as outras duas partições será os mesmos passos (**/dev/sdc e /dev/sdd**);
**b)** Pressione ==**n**== para criar uma nova partição;
**c)** Pressione ==**p**== para selecionar a partição primária;
**d)** Escolha ==**1**== para ser a primeira partição;
**e)** O passo seguinte pressione ==**duas vezes enter**== para usar o tamanho default;
**f)** Pressione ==**L**== para ver todas as opções;
**g)** Pressione ==**t**== para selecionar a repartição;
**h)** Pressione ==**fg**== para escolher o tipo de RAID;
**i)** Pressione ==**p**== para imprimir as mudanças que fizemos;
**j)** Pressione ==**w**== para gravar as alterações;

![](https://i.imgur.com/6Jdj6KT.png)

![](https://i.imgur.com/Xqt7HZV.png)

![](https://i.imgur.com/oHL1UUI.png)


**5.** Devemos agora **verificar** os 3 discos:
```
mdadm -E /dev/sd[b-d]
```
![](https://i.imgur.com/8xmBsaE.png)


**6.** Agora verifique o **RAID** das novas partições. Se não detetar super-blocks, deveremos criar uma nova **RAID 5** setup nestes discos:
```
mdadm --examine /dev/sdb1 /dev/sdc1 /dev/sdd1
```
![](https://i.imgur.com/gPByadd.png)


**7.** Agora **crie** um dispositivo Raid "md0" (ou seja, **/dev/md0**) e inclua o **nível** de RAID em todas as partições criadas (sdb1, sdc1 e sdd1):
```
mdadm --create /dev/md0 --level=5 --raid-devices=3 /dev/sdb1 /dev/sdc1 /dev/sdd1
```
![](https://i.imgur.com/F5H6W1h.png)


**8.** Depois de criar o dispositivo RAID, verifique o RAID, os dispositivos incluídos e o Nível de RAID da saída do **mdstat**:
```
cat /proc/mdstat
```
![](https://i.imgur.com/pZzCcFv.png)


**9.** Após a criação do RAID, **verifique** os dispositivos RAID:
```
mdadm -E /dev/sd[b-d]1
```
![](https://i.imgur.com/zm5eqlA.png)


**10.** Em seguida, verifique o **array** do RAID assumindo que os dispositivos que incluímos no nível de RAID estão em **execução** e começaram a ser sincronizados novamente:
```
mdadm --detail /dev/md0
```
![](https://i.imgur.com/IZcalhN.png)


**11.** Crie um sistema de arquivos para o dispositivo **"md0"** usando o ext4 antes da montagem:
```
mkfs.ext4 /dev/md0
```
![](https://i.imgur.com/Dn6oJou.png)


**12.** Agora crie um diretório em **'/mnt'**, monte o sistema de arquivos criado em **/mnt/raid5** e verifique os arquivos de montagem, você verá o diretório **lost + found**:
```
mkdir /mnt/raid5
mount /dev/md0 /mnt/raid5/
ls -l /mnt/raid5/
```
![](https://i.imgur.com/bx0E8nG.png)



**13.** Crie alguns arquivos em **/mnt/raid5** e acrescente algum texto em qualquer um dos arquivos para verificar o conteúdo:
```
touch /mnt/raid5/raid5_tecmint?{1..5}
ls -l /mnt/raid5/
```
![](https://i.imgur.com/moyzGTt.png)


**14.** Precisamos de entrar no **fstab**, senão não exibiremos a montagem após a reinicialização do sistema. Para adicionar uma entrada, devemos editar o arquivo **fstab** e acrescentar a seguinte linha. A montagem será diferente de acordo com o seu ambiente:
```
/dev/md0                /mnt/raid5              ext4    defaults        0 0
```
![](https://i.imgur.com/5wT7nWj.png)


**15.** Em seguida, execute o comando **"mount -av"** para verificar se há erros na entrada **fstab**:
```
mount -av
```
![](https://i.imgur.com/ba5O8Qc.png)


**16.** Como mencionado anteriormente na seção de requisitos, por padrão, o RAID **não possui** um arquivo de configuração. Temos que salvá-lo **manualmente**. Se este passo não for seguido, o dispositivo RAID não estará em **md0**, ele estará em algum outro número aleatório.
Portanto, precisamos de **salvar** a configuração antes de reiniciar o sistema. Se a configuração for salva, ela será carregada no **kernel** durante a reinicialização do sistema e o RAID também será carregado.
```
mdadm --detail --scan --verbose >> /etc/mdadm.conf
cat /etc/mdadm.conf
```
![](https://i.imgur.com/SkPG6QW.png)


==Serviço DHCP== e sua configuração
===

## O que é?

O DHCP é um serviço de rede com o objectivo de **automatizar** todo o processo de configuração do protocolo TCP/IP nos diversos equipamentos de uma rede (ex. computadores, dispositivos móveis, impressoras, etc). Este é sem dúvida um processo que reduz o esforço de configuração por parte de qualquer administrador de sistemas numa rede informática.

**1.** Visto já estar instalado, devemos **copiar** o ficheiro de configuração para a directoria ==/etc/dhcp==:

```
cp /usr/share/doc/dhcp-4.2.5/dhcp.conf.example /etc/dhcp/dhcpd.conf
```
![](https://i.imgur.com/HlvpTlh.png)


**2.** Configurar o ==**Dnsmasq**==:

![](https://i.imgur.com/LV4fS9M.png)


**3.** ==#linha 146:== adicionar(intervalo de endereços IP e o tempo em que o serviço irá fornecer)

![](https://i.imgur.com/1guSuN7.png)


**4.** ==#linha 316:== adicionar (definir gateway padrão)

![](https://i.imgur.com/RhUq2up.png)


**5.** ==#linha 325:== adicionar (definir NTP, DNS, servidor e subnetmask)

![](https://i.imgur.com/ytnDfuP.png)


**6.** Se a Firewall estiver em execução, ==permitir== o serviço DHCP. O Servidor DHCP usa 67 / UDP.

![](https://i.imgur.com/z8gBsCA.png)

![](https://i.imgur.com/ube2EYN.png)


**7.** Após a configuração do serviço dar sempre ==restart== ao serviço:

![](https://i.imgur.com/JRs648s.png)


**8.** Finalizado as configurações devemos ==desligar== a firewall no cliente e verificarmos se o cliente recebe o serviço:

![](https://i.imgur.com/V2c5zfn.png)

==Serviço DNS== e sua configuração
===

## O que é?

O DNS, do inglês ==Domain Name System==, funciona como um sistema de **tradução** de endereços **IP** para nomes de domínios. Na verdade, é graças ao DNS que você pode digitar www.google.com na barra de endereços do seu navegador para acessar o google.

### Configuração Dnsmasq


**1.** Primeiramente iremos instalar o ==dnsmasq==:
```
yum -y install dnsmasq
```

**2.** Para configurar o dns precisamos de **configurar** o seguinte ficheiro:
```
nano /etc/dnsmasq.conf
```

**3.** No ficheiro deveremos ==descomentar== e ==comentar== os seguintes comandos:
```
# linha 19: descomentar
domain-needed

# linha 21: descomentar
bogus-priv

# linha 41: descomentar
strict-order

# linha 123: descomentar
expand-hosts

# linha 133: adicionar (definir o dominio)
domain=atec.pt
```

**4.** Deveremos agora ==ativar== o serviço:
![](https://i.imgur.com/dEYYptG.png)

**5.** Para o DNS **guardar**, temos de adicionar em /etc/hosts ,para que o Dnsmasq consiga ==responder== aos pedidos dos clientes: 
```
nano /etc/hosts
```

**6.** ==Adicionar== os respetivos registos:
![](https://i.imgur.com/JOMqy1Z.png)

**7.** Se a Firewall estiver em execução, ==permitir== o serviço DNS:
![](https://i.imgur.com/eb2ieoB.png)

**8.** Fazendo tudo isto deveremos **reiniciar** o serviço:
![](https://i.imgur.com/FtuQV2s.png)

### Configurção Bind

**1.** Primeiramente devemos ==instalar== o bind:
```
yum -y install bind bind-utils
```

**2.** Iremos ==alterar== a **porta 53** para esta resolver qualquer pedido. E iremos também **desligar** a resolução de IPv6:

![](https://i.imgur.com/JbssCdI.png)

![](https://i.imgur.com/s227tYv.png)

**3.** Iremos **criar** uma ==view interna==. Esta irá ter as zonas internas, e iremos colocar a nossa rede (192.168.10.0/24). Deveremos também colocar o nosso ==domínio== (atec.matos).

![](https://i.imgur.com/MII4vgU.png)

**4.** Por fim, **criaremos** a ==view externa==. Esta vai resolver qualquer pedido do exterior.

![](https://i.imgur.com/7RKeBdG.png)

**5.** Agora iremos **configurar** a ==view interna== através de 2 ficheiros:
```
nano /var/named/atec.matos.lan
```

![](https://i.imgur.com/EUHshoP.png)

```
nano /var/named/10.168.192.db
```

![](https://i.imgur.com/xfe4OvH.png)

**6.** Agora iremos **configurar** a ==view externa== através de 2 ficheiros:
```
nano /var/named/atec.matos.wan
```

![](https://i.imgur.com/iW9dcXb.png)

```
nano /var/named/15.2.0.10
```

![](https://i.imgur.com/6yHWR70.png)

**7.** Por fim, deveremos fazer um ==restart== visto que fizemos alterações:

![](https://i.imgur.com/J9U8KOZ.png)

==Serviço SAMBA== e sua configuração
===

## O que é?

O Samba é um "software servidor" para Linux (e outros sistemas baseados em Unix) que permite o gerenciamento e compartilhamento de recursos em redes formadas por computadores com o Windows. Assim, é possível usar o Linux como servidor de arquivos, servidor de impressão, entre outros, como se a rede utilizasse servidores Windows (NT, 2000, XP, Server 2003).


**1.** Primeiramente devemos ==instalar== o serviço samba para podermos utilizar o serviço:

```
yum -y install samba samba-client
```

![](https://i.imgur.com/twOgSjr.png)


**2.** Para podermos configurar o ==samba== e as suas pastas de partilha termos de entrar no seguinte ficheiro:

```
vi /etc/samba/smb.conf
```

Primeiro iremos ==configurar== os dados principais:

![](https://i.imgur.com/uLCDR5J.png)

E em segundo iremos **configurar** o que queremos ==parilhar==:

![](https://i.imgur.com/xAC8yGl.png)

![](https://i.imgur.com/NMMiNY6.png)

![](https://i.imgur.com/dUVXQs4.png)

**3.** Iremos **adicionar** ==users==:

![](https://i.imgur.com/ZoFqyQV.png)

**4.** E agora devemos **dar** as respetivas passwords ao users criados no passo:

![](https://i.imgur.com/y9121kf.png)

**5.** A seguir devemos **criar** um grupo para os ==users==:

![](https://i.imgur.com/bdhVC0i.png)

**6.** Iremos **adicionar** os users criados ao mesmo grupo ==allowed==:

![](https://i.imgur.com/FjHseez.png)

**7.** Vamos **criar** as ==pastas partilhadas== para que as possamos as abrir noutros sistemas operativos:

![](https://i.imgur.com/O7swzL0.png)

**8.** Iremos permitir que estes 4 users sejam ==autorizados== dentro do **novo** grupo criado:

![](https://i.imgur.com/YEeZg1A.png)

**9.** Devemos dar ==permissões== ás **pastas**:

![](https://i.imgur.com/J5RXMa6.png)

**10.** Iremos dar **permisão** á ==firewall==:

![](https://i.imgur.com/THenIGr.png)

**11.** Devemos agora ==ativar== o serviço:

![](https://i.imgur.com/3ShXtIz.png)

**12.** Por fim, no windows ou noutro sistema operativo devemos ==confirmar== na pasta de rede:

![](https://i.imgur.com/4r6zCFA.png)


----

==Serviço SSH== e sua configuração
===

## O que é?

O **SSH** (Secure SHell) é um protocolo que permite a aceder virtualmente o servidor como se estivesse em um ==terminal== (no prompt do DOS, por exemplo). Se preferir, considere como o SSH como um computador controlado por outro computador.

**1.** Para configurarmos o serviço SSH temos de configurar primeiramente o seguinte **ficheiro** de texto:
```
nano /etc/ssh/sshd_config
```

**2.** Iremos **descomentar** e **adicionar** os seguintes comandos conforme as prints:

![](https://i.imgur.com/Xi1q8M4.png)

![](https://i.imgur.com/cWALi5B.png)

![](https://i.imgur.com/I8FLcU9.png)

**3.** No sistema operativo linux iremos **gerar** uma chave **pública** enquanto que a chave ==privada== irá ser gerada no ==puttygen em Windows==:

```
ssh-keygen -t rsa
```

![](https://i.imgur.com/i6CadK1.png)

e no ==**Windows**==

![](https://i.imgur.com/20ki59v.png)


**4.** Sendo esta já criada devemos **mover** a chave ==publica== para o ficheiro das  **chaves autorizadas** em ==linux==, o seguinte comando é:

```
mv /root/.ssh/id_rsa.pub ~/.ssh/authorized_keys
```

**5.** Já tendo movendo a chave ==pública== devemos entrar no seguinte ficheiro colocando a chave **privada** gerada pelo ==Windows== na linha abaixo da chave pública:

![](https://i.imgur.com/XQ7Yl9M.png)

**6.** Na interface Putty do Windows devemos adicionar a chave privada pelo seguinte caminho, clicando no final em ==**browse**==:

![](https://i.imgur.com/U3fSZPr.png)

**7.** Para concluir a configuração basta apenas dar o ==ip do servidor== e nos  **logarmos**:

![](https://i.imgur.com/Q1yTGPF.png)

![](https://i.imgur.com/eT29RmU.png)


==Serviço LAMP== e sua configuração
===

### HTTPD configuração

**1.** Primeiramente iremos instalar o **HTTP**:

```
yum install httpd
```

**2.** Após a instalação devemos ==remover== a página inicial do **http**:

```
rm -rf /etc/httpd/conf.d/welcome.conf
```

**3.** Iremos precisar de **configurar** o ==httpd== no seguinte ficheiro:

```
nano /etc/httpd/conf/httpd.conf
```

![](https://i.imgur.com/C9Ud5pS.png)

![](https://i.imgur.com/by4Qbwv.png)

**4.** E como já é habitual devemos ==habilitar== o serviço escrevendo:

```
systemctl enable httpd
systemctl start httpd
```

![](https://i.imgur.com/HmmR15I.png)

**5.** No ficheiro ==named== iremos adicionar o **user** e o **ip** do server:

```
nano /var/named/atec.matos.lan
```

![](https://i.imgur.com/S0ZRtys.png)

**6.** Por fim, iremos dar **permisão** á ==firewall==:

![](https://i.imgur.com/RNdmOGq.png)


### MARIADB configuração

**1.** Primeiramente, iremos ==intalar== este pacote que contém **configurações** necessárias:

```
yum install centos-release-scl
```

**2.** **Iremos** ==atualizar== o server após o primeiro passo:

```
yum update
```

**3.** E por **fim**:

```
yum install rh-mariadb102-mariadb-server
```

**4.** ==Ativar== o MySQL e **verificar** a versão:

![](https://i.imgur.com/f5cxyqr.png)

**5.** Em termos de configuração devemos **adicionar** ao seguinte ficheiro o seguinte comando ==**character-set-server=utf8**==

```
nano /etc/opt/rh/rh-mariadb102/my.cnf.d/mariadb-server.cnf
```

![](https://i.imgur.com/snDfDcO.png)

**6.** Iremos ativar o ==rh-mariadb102-mariadb== :

```
systemctl start rh-mariadb102-mariadb 
systemctl enable rh-mariadb102-mariadb
systemctl status -l rh-mariadb102-mariadb
```

![](https://i.imgur.com/zjK6v9f.png)

**7.** Neste paco iremos **instalar** o ==mysql==:

![](https://i.imgur.com/DHq8zNr.png)

e a partir dai é **responder** que ==sim==

**8.** No seguinte ficheiro iremos **adicionar** ==skip-grant-tables==:

```
nano /etc/my.cnf
```

![](https://i.imgur.com/FTXO7wF.png)

**9.** Após configurarmos devemos dar um ==restart== á **mariadb**:

```
systemctl restart rh-mariadb102-mariadb
```

**10.** Iremos **configurar** as definicoes iniciais digitando o seguinte comando:

```
mysql -u root -p
```

![](https://i.imgur.com/GMFC3z7.png)

**11.** Por fim, iremos dar **permisão** á ==firewall==:

![](https://i.imgur.com/h0OWOlY.png)

### PHP configuração

**1** Primeiramente iremos ==instalar== o **php**:

```
yum install php
```

**2** Teremos de **instalar** pacotes ==adicionais== para o php:

```
yum install epel-release
```

**3** E por fim o ==phpmyadmin==:

```
yum install phpmyadmin
```

**4** Neste ficheiro precisaremos apenas de **alterar** a linha ==17== e ==34==:

```
nano /etc/httpd/conf.d/phpMyAdmin.conf
```

![](https://i.imgur.com/Xpj0K3Q.png)

![](https://i.imgur.com/wQJMGH1.png)

**5.** O passo final deveremos abrir o browser e **confirmar** se nos conseguimos ==logar== ao phpmyadmin:

```
duarte.atec.matos/phpmyadmin/
```

![](https://i.imgur.com/Oc1pbvp.png)

![](https://i.imgur.com/rc7xtmJ.png)


----

==Serviço FTP== e sua configuração
===

## O que é?

A sigla ==FTP== significa File Transfer Protocol, que em português significa **Protocolo de Transferência de Arquivos**. Sendo esta uma ferramenta usada em todo o mundo para a ==transferência de ficheiros==, seja para a criação de um website, ou mesmo para entregar ficheiros a pessoas que estão a milhares de quilómetros em poucos minutos.


**1.** Primeiramente iremos ==instalar== o serviço **FTP**

```
yum install vsftpd
```

**2.** Devemos agora **configurar** o serviço no ficheiro:

```
nano /etc/vsftpd/vsftpd.conf 
```

```
anonymous_enable=NO

ascii_upload_enable=YES

ascii_download_enable=YES

chroot_local_user=YES

chroot_list_enable=YES

chroot_list_file=/etc/vsftpd/chroot_list

ls_recurse_enable=YES

listen=YES

listen_ipv6=NO

local_root=public_html

use_localtime=YES

seccomp_sandbox=NO
```

**3.** Após, a configuração do serviço iremos ==listar== os **users** que irão **transferir** dados e arquivos entre cliente e servidor:

```
nano /etc/vsftpd/chroot_list
```
 
![](https://i.imgur.com/g9Ljww2.png)

**4.** Como é habitual devemos dar **enable** e **restart** ao serviço:

```
systemctl enable vsftpd
systemctl start vsftpd
systemctl restart vsftpd
```

**5.** Devemos sempre também ==adicionar== á **firewall** sempre o nosso serviço:

![](https://i.imgur.com/DpIlwya.png)

**6.** No final, iremos testar a ligação entre o cliente e o servidor na aplicação **Filezila** no ==Windows==:

![](https://i.imgur.com/Jw8klJU.png)

**NOTA**: Sempre que dermos ==reboot== ao servidor e se quisermos ter ligação teremos de digitar o seguinte comando:

```
iptables -t nat -A POSTROUTING -s 192.168.10.0/24 -o enp0s3 -j MASQUERADE
```

![](https://i.imgur.com/xMQgUFS.png)

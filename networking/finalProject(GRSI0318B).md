###### tags: `Networking`, `Servers`, `Windows Server`, `Linux Server`
![](https://i.imgur.com/qwdmWKR.png)

# Projeto Final GRSI0318B

**Formador:** Ricardo Pereira
**Formandos:** David Jesus, Duarte Matos e Joao Matos
**Turma:** GRSI0318B

![](https://i.imgur.com/LKj0p2C.png)

## Objetivos

Implementar a rede, disponibilizando os seguintes serviços/funcionalidades:

**a. Windows Server:**

- [x] O AD server deve ser Domain Controler com um ==domínio== de seu nome :
ATECGR0318. 
O Administrador deve ter como ==password==: Atec+123

- [x] O servidor terá como IP o ==ultimo IP== disponível na sua rede.

- [x] O servidor terá uma pool DHCP de 10 IP ́s. O cliente PC4 deverá ter
um IP reservado que será o 2o endereço disponível na rede.

- [ ] Os PC 4 e PC5 devem estar no ==domínio==, e receber IP por DHCP.

- [x] Crie ==5 utilizadores== no domínio (NSilva, RSilva, Rpereira, Rmachado,
Cjorge) com a password “Xadrez”.

- [x] Crie ==2 Grupos==, “Coordenação” e “Formadores”, sendo que os 2
primeiros utilizadores fazem parte do grupo “Coordenação” e os
restantes do grupo “Formadores”.

- [x] Partilhe uma pasta no servidor com o nome de ==DOCS== (esta partilha
deve estar escondida); dentro dela deve conter uma pasta para cada
utilizador de forma a que os formadores apenas tenham acesso à sua
pasta e os coordenadores tenham acesso a todas. Todos os utilizadores devem
ter uma drive T: que aponte para a pasta DOCS.

- [x] Todos os utilizadores terão que ter na sua ==homefolder== apenas 1GB de quota de disco.

- [x] Todas as máquinas antes do login têm de exibir um ==aviso== para que todos os
documentos sejam gravados na sua homefolder.

- [x] Os Formadores ==devem== ter um pano de fundo do ambiente de trabalho com o
símbolo da ATEC; os restantes podem alterar o seu pano de fundo.

- [x] Os Formadores ==não têm acesso== à linha de comandos.

- [x] Todos os utilizadores têm como ==home page== do IE a pagina www.atec.pt e não podem alterar.

- [ ] Deve estar instalado o serviço de DNS e os clientes devem usar este ==servidor/serviço== para executar as resoluções de DNS.

**b. Wireless**

- [ ] Os utilizadores do Wireless ==apenas== podem ter acesso à Internet e aos serviços web, pois é um acesso para convidados
- [ ] O SSID deve ser definido e ==explicado== e ==justificando== o porquê.
- [ ] O wireless deve ser ==testado== com o recurso a um dispositivo móvel (Exem.
Telemóvel)

**c. PC Clientes**

- [ ] O PC2 e PC0 apenas têm ==acesso== à Internet e aos ==serviços web==.
- [ ] Os restantes têm acesso a ==todos== os serviços da rede.

**d. Serviço Apache/My SQL/PHP (localizados no servidor WEB)**

- [ ] Aproveitando estes serviços no servidor WEB, devem ==criar== um site de inscrição para um evento chamado “apresentação final dos projetos”, onde devem ter pelo menos os seguintes campos:
a. Nome
b. Morada
c. No de telefone
d. Data de Nascimento
e. Curso
f. No do cartão de cidadão
g. Lista de selecção entre “manhã” e “tarde”
h. Uma combo box para validar se é repetente ou não.

- [ ] Botão para ==gerar== relatório de todos os inscritos e todos os repetentes.
- [ ] Para aceder a este site os clientes ==devem== usar o seguinte endereço:
inscrição.atecgr0318.pt

**e. Serviço Asterisk :**

- [ ] O servidor deve dispor deste serviço, no qual deve ser ==criada== pelo
menos, 1 extensão para cada utilizador (NSilva, RSilva, Rpereira,
Rmachado, Cjorge) com a password “Xadrez” e respectivamente, os
seguintes números: 100,101, 102,103,104

**f. Gestão de tráfego para o exterior**

- [ ] O servidor deve ==gerir== o acesso ao ==exterior==. O cenário ideal será a instalação de uma ==PFSense== para gerir o trafego.
- [ ] O PC2 ==não deve== aceder ao youtube.com e o PC0 não pode aceder ao
facebook.com.

**g. Serviço de E-mail – Postfix (localizado no servidor WEB)**

- [ ] O servidor deve dispor deste serviço e ==devem ser criados 5 endereços==
de e-mail (NSilva@atecgr0318.pt, RSilva@atecgr0318.pt,
Rpereira@atecgr0318.pt, Rmachado@atecgr0318.pt,
Cjorge@atecgr0318.pt) com a ==password== “Xadrez”. Deve ser
demonstrado o funcionamento do mesmo.

**h. Interface de administração gráfica (Cockpit / Webmin / Zpanel )**

- [ ] O servidor deve ==dispor== de administração gráfica, tanto o ==servidor web==, como o ==servidor de asterisk==.

**i. Configurações de rede:**

- [ ] Deve existir um ==controlo== de fluxo nos routers onde a comunicação seja
feita pelas ligações serial, no sentido dos ==ponteiros do relógio==; em caso de falha, devem usar as ==ligações Ethernet== para comunicar.
- [ ] O ==router 1== será configurado como ==DHCP Server==.
- [ ] Nos ==switchs== devem ser configuradas as portas com ==portsecurity em modo Restrict==.

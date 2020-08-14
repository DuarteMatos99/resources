###### tags: `Web`, `Full Stack Development`

![](https://i.imgur.com/8e5ddIS.png)

# Web Services
## O que é?
Serviços Web são soluções para as aplicações se comunicarem independentemente da linguagem, software e hardware utilizados. Podendo dizer que os web services sao **API's** que se comunicam por meio de redes sobre o protocolo **HTTP**. 

![](https://i.imgur.com/wCcfP4A.png)

### Principais Tecnologias
- SOAP
- REST
- JSON
- XML

## SOAP
**SOAP** (Simple Object Access Protocol) - é um protocolo baseado em **XML** para acessar web services principalmente por **HTTP**. 
Pode se dizer que **SOAP** é uma definicao de como os web services se comunicam. ==Desenvolvido para facilitar integracoes entre aplicacoes==.

### Estrutura SOAP
O **SOAP MESSAGE** possui uma estrutura única que deve sempre ser seguida.

![](https://i.imgur.com/oJLJ2qn.png) 
*Exemplo de uma estrutura SOAP*

==SOAP ENVELOPE== - É o primeiro elemento do documento e é usado para encapsular toda a mensagem SOAP

==SOAP HEADER== - É o elemento onde possui informacoes de atributos e metodos de requisicao(ex: IP)

==SOAP BODY== - É o elemento que contém os detalhes da mensagem

![](https://i.imgur.com/E3chfEt.png)
*Exemplo de uma mensagem SOAP*

## XML
**XML** (Extensible Markup Language) - é uma linguagem de marcacao que nao tem limitacao de tags facilitando a separacao de conteudo.

## Entendendo o que é WSDL e XSD
**WSDL** (Web Services Description Language) - é usado para descrever Web Services, funcionando como um ==contrato de servico==. E essa descricao é feita em documento XML, onde é descrito o servico, especificacoes de acesso, operacoes e metodos.

**XSD** (XML Schema Definition) - é um schema no formato XML usado para ==definir a estrutura de dados== que será validada no XML. O XSD funciona como uma documentacao de como deve ser montado o SOAP Message(XML) que será enviado atraves do web service.

## Aprenda o que sao REST, API e JSON
**REST** (Representational State Transfer) - é um estilo de arquitetura de software que define a implementacao de um servico web, podendo este trabalhar com os formatos JSON, XML ou outros.

**API** (Application Programming Interface) - sao conjuntos de rotinas documentadas e disponibilizadas por uma aplicacao para que outras aplicacoes possam consumir suas funcionalidades.

**JSON** (JavaScript Object Notation) - formatacao leve utilizada para troca de mensagens entre sistemas

## Principais Metodos HTTP
**GET** - Solicita a representacao de um recurso
**POST** - Solicita a criacao de um recurso
**DELETE** - Solicita a exclusao de um recurso
**PUT** - Solicita a atualizacao de um recurso

## Integracao com REST e metodos HTTP

### State code(codigo de estado)
Usado pelo servidor para avisar o cliente sobre o estado da operacao solicitada:
==1xx== - Informativo 
==2xx== - Sucesso
==3xx== - Redirecionamento
==4xx== - Erro do cliente
==5xx== - Erro do servidor

# Conceitos de arquitetura em aplicações para Internet
## Tipos de arquitetura
Monolito
- Escolhemos uma Linguagem 
- Um Servidor de Aplicação
- Desenvolvíamos nossa aplicação orientada a esta plataforma

Microservicos
- uma variante do estilo estrutural da arquitetura orientada a serviços
- organiza um aplicativo como uma coleção de serviços vagamente acoplados 
- Em uma arquitetura de microsserviços, os serviços são refinados e os protocolos são leves

## Gerenciamento de erros e volume de acesso
### Gerenciamento de erros
Onde é mais complexo:
- Processos assincronos
- Pipeline

Solucao:
- Dead letter queue
- Filas de re-tentativas

# A arquitetura de aplicações móveis e internet das coisas
## O que é?
A Internet das coisas é um conceito que se refere à interconexão digital de objetos cotidianos com a internet, conexão dos objetos mais do que das pessoas. Em outras palavras, a internet das coisas nada mais é que uma rede de objetos físicos capaz de reunir e de transmitir dados.

## Arquitetura da internet das coisas
- Baixo consumo de energia
- Rede de dados limitado
- Resiliencia
- Seguranca
- Custumizacao
- Baixo custo

## Protocolo IOT
MQTT (Protocolo mais usado em IOT) - protocolo de mensagens assincrona, com base do TCP/IP. Padrao OASIS suportado pelas linguagens de programacao mais populares

## MQTT Broker
O broker é um padrão publish/subscriber (publicador/subscritor), um intermediário no processo de comunicação entre os sensores (publish) e os diversos clientes (subscriber)

### Modelo Publish/Subscribe
![](https://i.imgur.com/48fWp7G.png)

## QoS 0,1 e 2 - MQTT Essentials

==Nivel 0== - Nivel minimo de menor esforco, sem garantia de entrega, mensagem nao é retransmitida

==Nivel 1== - Garante que a mensagem  foi entregue no minimo uma vez ao recebedor, Mensagem pode ser retransmitida se nao houver confirmacao da entrega

==Nivel 2== - Garante que a mensagem  foi entregue no minimo uma vez ao recebedor, Mensagem pode ser retransmitida se nao houver confirmacao da entrega

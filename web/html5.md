**Author:** Duarte Matos
###### tags: `Web`, `HTML 5`, `CSS`

# HTML 5

![](https://i.imgur.com/zYyVpkM.png)


## O que é?
Existem 3 linguagens básicas que utilizamos para criar websites: HTML, CSS e JavaScript.
O HTML é a linguagem que irá exibir a informação. O CSS é a linguagem que vai deixar essa informação bonitona. O JavaScript é a linguagem que vai fazer essa informação receber alguns comportamentos, como por exemplo ao criar um submenu ou controlar algo que aparece e desaparece na tela.

O HTML sem dúvida é a mais importante de todas, por que como dissemos no começo, é ela que exibe a informação. Além de exibir a informação, ela dá significado. Isso é importante por que alguns sistemas como o Google, que irão ler sua página, precisam entender o que é cada elemento nela e o que cada um desses elementos significam.

## Estrutura básica
O documento HTML sempre inicia com o que chamamos de estrutura básica. Esta estrutura é quase que imutável. Sempre será dessa forma e você sempre, sempre começará seu HTML começando por esse código. 

```html
<!DOCTYPE html>
<html lang="pt-br">
  <head>
    <title>Título da página</title>
    <meta charset="utf-8">
  </head>
  <body>
    Aqui vai o código HTML que fará seu site aparecer.
  </body>
</html>
```

### Doctype - Definindo o documento
---
Uma coisa importante: SEMPRE deve existir o doctype, que é este código <!DOCTYPE html>.

O doctype não é uma tag HTML, mas uma instrução para o navegador e outros programas que podem ler seu site, que o código encontrado ali é um código HTML. Assim eles sabem o que fazer para mostrar seu site da melhor forma possível. Lembre-se: o doctype é OBRIGATÓRIO e deve ser sempre a PRIMEIRA LINHA do seu documento.

### HEAD
---
Contém informações que não são transpostas visivelmente para o usuário/leitor do documento. São dados implícitos, de uso e controle do documento: vinculação com outros arquivos, aplicação de lógica de programação de scripts e metadados. Na prática, todo o conteúdo do cabeçalho fica delimitado entre a abertura e fechamento tag head.

### BODY
----
Trata-se do documento em si, ou seja, a informação legível para o usuário/leitor do documento. É todo e qualquer texto que se deseja apresentar, assim como toda e qualquer forma de mídia de saída (imagens, sons, miniaplicativos embutidos, conteúdo multimídia, etc). Além disso, toda a apresentação de entrada de dados (formulários) também se aplica neste seção do documento. Na prática, o corpo do documento é delimitado pelo par de tags <body> e </body>.

Este é o preceito básico que deve estar muito bem claro para você: onde as marcações se aplicam, e quais são os resultados deste modelo. 

Dentro do elemento BODY sua estrutura de página terá os elementos semânticos da construção da sua página, onde serão declarados e identificados cabeçalhos, rodapé, conteúdo principal, etc.

### Tags
---
As Tags sao aquelas que comecao com < e acabam com /> como por exemplo:
```
<html> </html>
```

## Visual Studio Code
Comando para gerar a estrutura de html no editor:
```
html:5 
```

Se tivermos textos muito longos e os quisermos que esteja organizado no nosso editor selecionamos:
```
word wrap
```

# Tag HTML

Podemos explicitar o conteúdo do nosso site digitando:
```
<html lang="pt-br">
```

Comentarios em html:
```
<!-- Isto é um comentario -->
```

# Tag HEAD


## Meta
Para defenirmos um conjunto de caractreres portugueses compativel com o padrao ANSI americano digitamos o seguinte:
```
<meta charset="UTF-8"/>
```

## Titulo
Para defenirmos o titulo da pagina digitamos:
```
<title>Exemplo</title>
```

## Style
Para configurarmos o estilo da página utilizamos a tecnologia CSS, podemos o aplicar diretamente no mesmo documento digitando style:
```
<style>
    h1 {
        font-family: Arial;
        font-size: 30pt;
        color: Blue;
        text-shadow: 2px 2px 2px black;
    }
</style>
```

## Link(chamar CSS)
Para gerar uma ligacao entre o html e o html 5 utilizamos o link. Utilizamos o rel para indicar que é uma folha de estilo. O type sera CSS e o href ira procurar a localizacao do ficheiro CSS.
```
<link rel="stylesheet" type="text/css" href="_css/estilo.css">
```

## Link(chamar Js)
```
<script src='funcoes.js'></script>
```

# Tag Body

## Cores em CSS
Para alterarmos a cor de fundo em CSS utilizamos "background-color":
```
<body style="background-color: yellow;"></body>
```

Para alterarmos a cor da letra em CSS utilizamos "color":
```
<body style="color: yellow;"></body>
```

Para alterarmos a cor da letra em CSS utilizamos "color" podendo utilizar rgb():
```
<body style="color: rgb(255, 255, 255);"></body>
```

Para alterarmos a ==transparencia== da letra em CSS utilizamos "color" usando rgba() sendo o 0 totalmente transparente e 1 totalmente visivel. 
```
<body style="color: rgba(0, 0, 0, 0.5);"></body>
```

---
## Titulos
Para criar um titulo digitamos:
```
<h1>Olá, Mundo!</h1>  # O h simboliza hierarquia de titulos
```

Agrupando titulos como grupos ajuda na semantica do codigo e nao na estetica para o usuario:
```
<hgroup>
<h1> Titulo 1</h1>
<h2> Titulo 2</h2>
</hgroup>
```

### Titulos em CSS
A maneira correta de formatar é a partir de CSS utilizando o "text-align".
1. Centrar o texto.
```
<h2 style="text-align: center;">Google</h2>
```
2. Colocar o texto á direita.
```
<h2 style="text-align: right;">Google</h2>
```
3. Colocar o texto á esquerda.
```
<h2 style="text-align: left;">Google</h2>
```

---

## Formatar texto
Para formatarmos os paragrafos utilizamos:
```
<p></p>
```

Se quisermos ter um texto sob escrito.
```
<p> Exemplos de <sup>formatacao</sup></p>
```

Se quisermos ter um texto sub escrito.
```
<p> Exemplos de <sub>formatacao</sub></p>
```

Para colocarmos uma linha horinzontal:
```
<hr>
```

Para quebrarmos a linha utilizamos:
```
<br>
```

Para criarmos espacos em branco utilizamos:
```
&nbsp  # representa so 1 espaco
```

Se quisermos quebrar palavras longas utilizamos para separar palavras de acordo com o tamanho da pagina:
```
<wbr/>
```

Para colocarmos palavras em negrito utilizamos o:
```
<b></b>
```

Para colocarmos palavras em italico utilizamos o:
```
<i></i>
```

Para colocarmos palavras deitadas e enfatizar certas palavras utilizamos o:
```
<em></em>  # funciona semanticamente 
```

Para riscarmos palavras que indiquem que foram eliminadas utilizamos o:
```
<del></del> 
```

### Paragrafos em CSS
Para alterarmos a formatacao de paragrafos utilizamos "text-align":
1. Para justificar o texto tanto para a esquerda e para direia da mesma forma utilizamos:
```
<p style="text-align: justify;">Google</p>
```
2. Se quisermos identar paragrafos utilizamos o "text-indent".
```
<p style="text-align: justify; text-indent: 30px;">Google</p>
```

### Fonte em CSS
Para termos mais controle do negrito podemos usar CSS para tal, vamos utilizar o "font-weight" indicando a quantidade de negrito que o texto terá:

==Font-weight:== determina a grossura/fineza do texto

1. Para criar um texto sem nenhuma formatacao.
```
<span style= "font-weight: normal;">Google</span>
```
2. Para criar um texto com bold.
```
<span style= "font-weight: bold;">Google</span>
```
3. Para criar um texto com um bold mais intenso.
```
<span style= "font-weight: bolder;">Google</span>
```
4. Se quisermos definir um nivel de negrito colocando um valor entre 100 e 900.
```
<span style= "font-weight: 400;">Google</span>
```

Para termos um texto sublinhado
```
text-decoration: underline;
```

Para termos um texto riscado
```
text-decoration: line-through;
```

Transformar o texto
```
text-transform: uppercase;
```

Para criar espaco entre o texto
```
line-height: 200px;
```

Para alterarmos o estilo de letra:
```
font-style: italic;
```

Para definirmos o tamanho da letra:
```
font-size: 100%;
```

Que tipo de letra queremos:
```
font-family: Georgia;

// Para varias palavras utilizamos ""
font-family: "Times New Roman";

// Para o caso de querermos ter varias fontes como alternativa
font-family: "Times New Roman", Georgia;
```

### Linhas em CSS
Para sublinharmos textos no html temos de usar tecnologia CSS porque a nova versao de html removeu a tag 'u'. O "text-decoration" tem varias funcionalidades como:
1. Sublinhar o texto.
```
<span style= "text-decoration: underline;">Google</span>
```
2. Colocar uma linha em cima do texto.
```
<span style= "text-decoration: overline;">Google</span>
```
3. Posso tambem riscar o texto.
```
<span style= "text-decoration: line-through;">Google</span>
```
4. E se nao quiser sem nenhuma formatacao.
```
<span style= "text-decoration: none;">Google</span>
```
---

## Form
Para criarmos formularios de recolha de dados utilizamos 'form'

```htmlmixed=
<form>   
    //cria caixa de texto
    First Name:<input type="text"><br> 
    Last Name:<input type="text"><br> 
    
    //O type email cria um campo email com obrigacao de @
    //cria campo obrigatorio
    Email:<input type="email" required><br> 
    
    // campo password obrigatorio com minimo de 5 caracteres
    Password:<input type="password" required min="5"><br> 
    Birthday:<input type="date"><br> 
    
    //campo com bolinhas utilizando o mesmo name apenas seleciona uma
    Gender:<input type="radio" name="gender"> 
    Male<input type="radio" name="gender"> 
    Female<input type="radio" name="gender"> 
    Other<br> 
    
    //Cria uma escolha multipla
    Pets:
    <input type="checkbox">Cats
    <input type="checkbox">Dogs<br> 
    
    //Cria uma lista em que podemos selecionar o que queremos
    Cars:
    <select>
        <option value="Volvo">Volvo</option>
        <option value="Audi">Audi</option>
    </select><br>
    
    //cria botao de submit
    <input type="submit">
    
    //o texto do botao sera Next
    //<input type="submit" value="Next">
    
    //cria botao de reset
    <input type="reset">
</form>
```

### Submeter um Form
A data de um form pode ser enviada como variaveis de URL(com o method="get") ou como transacao HTTP(com method="post").
Foi adicionado os campos name e value para facil identificacao dos campos.
```htmlmixed=
<form method="GET">
        First Name:
        <input type="text" name="firstname"><br> Last Name:
        <input type="text" name="lastname"><br> Email:
        <input type="email" required name="email"><br> Password:
        <input type="password" required min="5" name="password"><br> Birthday:
        <input type="date" name="date"><br> Gender:
        <input type="radio" name="gender" value="male"> Male
        <input type="radio" name="gender" value="female"> Female
        <input type="radio" name="gender" value="other"> Other<br> Pets:
        <input type="checkbox" name="cat"> Cat
        <input type="checkbox" name="dog"> Dog<br> Cars:
        <select name="car">
            <option value="Volvo">Volvo</option>
            <option value="Audi">Audi</option>
        </select><br>
        <input type="submit">
        <input type="reset">
    </form>
```
Resultado ao submeter os dados:
```
?firstname=anng&lastname=matos&email=duartematos1999%40gmail.com
&password=123&date=2020-03-05&gender=male&cat=on&car=Volvo
```

## DIV
Para criarmos seccoes ou divisoes no nosso documento html utilizamos a tag div:
```
<div id="interface">  # id identifica a div
Exemplo de texto
</div>
```

### DIV em CSS
Para alterarmos o comprimento da nossa secao.
```
div#interface {
    width: 600px;
}
```
Para centrarmos seja o que for utilizamos a keyword 'auto', trabalha se com as margens.
```
margin: 10px auto 10px auto;
```
Para o texto nao ficar agarrado as margens utilizamos o padding. Se todos os valores forem iguais o CSS permite que coloquemos apenas um valor.
```
padding: 10px 10px 10px 10px;  # antes
padding: 10px;  # agora
```
---

## Header
Header sigifica cabecalho.
```
<header></header>
```

### Header em CSS
Para colocarmos uma linha no final do nosso header. Esse comando ira fazer uma linha cinzenta de largura 1.
```
header#cabecalho {
    border-bottom: 1px #606060 solid
}
```
Delimitamos o nosso header.
```
height: 150px;
```
Vamos alterar os nossos titulos.
```
header#cabecalho h1 {
    font-family: Arial;  # Altera o tipo de letra
    font-size: 30px;
    color: #606060;
    text-shadow: 1px 1px 1px rgba(0, 0, 0, 0.6);
}
```
Temos de configurar o padding e o margin.
```
padding: 0px;
margin-bottom: 0px;
```
---

## Section
Sessao principal do nosso site.
```
<section></section>
```

### Section em CSS
```
section#corpo {
    display: block;
    width: 600px;
}
```
Para podermos movimentar os nossos blocos utilizamos 'float'.
```
float: left;
```
---

## Article
Significa artigo/noticia. Serve para editar artigos dentro da nossa section por exemplo.
```
<article id="noticia-principal"></article>
```

## Aside
Sessao lateral do nosso site.
```
<aside></aside>
```

### Aside em CSS
```
aside#lateral {
    display: block;
    width: 400px;
}
```
Para podermos movimentar os nossos blocos utilizamos 'float'.
```
footer: right;
```
---

## Footer
Rodape do nosso site.
```
<footer></footer>
```

### Footer em CSS
Feito as divisoes na section e no aside para fazermos com que o nosso rodape nao esteja nestas divisoes.
```
footer#rodape {
    clear: both;
}
```
Centralizar o rodape.
```
footer#rodape p {
    text-align: center;
}
```
---

## NAV
Cria uma area de navegacao dentro do meu site. Tudo o que estiver dentro de 'nav' é considerado o meu menu de navegacao
```
<nav id="menu"></nav>
```

### NAV em CSS
==media query== - vai executar apenas quando o ecra for menos de 600px. Muito utilizado para menus NAV
```
@media only screen and (max-width: 600px) {
    .main-nav {
        font-size: 0.5em;
        padding: 0;
    }
}
```

#### Menu
Para colocarmos o texto todo em maiuscula.
```
text-transform: uppercase;
```
Para colocarmos os elementos de uma lista em linha.
```
nav#menu li {
    display: inline-block;
}
```
Para colocarmos cor de background.
```
background-color: grey;
```
Para darmos um espaco dentro da nossa caixa de background.
```
padding: 10px;
```
Para darmos um espaco entre as caixas de background.
```
margin: 2px;
```
Para fazermos o nosso menu(nav) flutuar pela tela.
```
nav#menu {
    display: block;
}
```
#### Listas
Para removermos os marcadores da nossa ul.
```
nav#menu ol {
    list-style=none;
}
```
Para colocarmos a lista a flutuar pela tela e com a posicao absoluta em relacao ao site.
```
nav#menu ol {
    position: absolute;
    top: -20px;
    left: 300px;
}
```
Para escondermos o h1 do main menu.
```
nav#menu h1 {
    display: none;
}
```
Para termos um efeito visual quando passarmos o rato por cima.
```
nav#menu li:hover {
    background-color: #666666;
}
```
Para aplicarmos transicoes quando passarmos o rato por cima.
```
nav#menu li {
    transsition: background-color 1s;
}
```
#### Links
Para alterarmos o estilo das hiperligacoes.
```
nav#menu a {
    color: #000000;
    text-decoration: none;  # Remove a linha por baixo do texto
}
```
Para alterarmos a cor da hiperligacao se passarmos o rato por cima.
```
nav#menu a:hover {
    color: #ffffff;
}
```
---

## Listas(ol/ul)
Existem dois tipos de listas: a 'ol' que é uma lista ordenada e a 'ul' que é uma lista nao organizada. Dentro delas temos items representados por 'li'.

### Tipos de ol
Tipo padrao(numeros):
```
<ol type="1">
```
Tipo alfabético:
```
<ol type="a">
```
Tipo numeros romanos:
```
<ol type="i">
```

Se quisermos por exemplo ter uma lista que comece pelo numero 3 fazemos da seguinte maneira:
```
<ol type="1" start="3">
```

### Tipos de ul
Tipo padrao:
```
<ul type="disk">
```
Tipo quadrado:
```
<ul type="square">
```
Tipo circulos:
```
<ul type="circles">
```

### Li
Topicos dentro duma lista
```
<ul>
    <li>Home</li>
    <li><a href="about.html">About</a></li>
    <li><a href="login.html">Login</a></li>
</ul>
```

### Listas em CSS
Remove o que estiver antes do topico(ex: bolinhas) 
```
li {
    list-style: none;
    
    // Coloca a lista em linha
    display: inline-block;
}
```
---

## Criacao de tabelas
```
<table></table>
```
O titulo da tabela.
```
<caption></caption>
```
Para alterarmos uma parte do titulo utilizamos o 'span' para alterarmos no CSS.
```
<caption>Técnicas do Google Glass <span>fev/2020</span></caption>
```
Para identificarmos varios objectos no html utilizamos a tag 'class'.
```
<td rowspan="2" class="ce">Camera</td>
```

### TR
Table rows, cria as linhas para a tabela.
```
<tr></tr>
```

### TD
Table data, celulas de dados.
```
<td></td>
```

### Rowspan
Um campo com varias celulas.
Primeiro adicionamos uma nova linha com o 'tr' com o respetivo 'td'. Para indicarmos que um campo tem duas celulas utilizamos o 'rowspan="2"'
```
<tr>
    <td rowspan="2">Conectividade</td>
    <td>Wi-Fi</td>
    <tr>
        <td>Bluetooth</td>
    </tr>
</tr>
```

### Colspan
Um campo que une varios campos num so
```
<tr><td colspan="2">Linha extra</td></tr>
```

### Tabelas CSS
#### Bordas
Para fazermos uma borda para a nossa tabela
```
tabela#tabelaspec {
    border: 1px solid #606060;
}
```
Para desenharmos linhas a volta das celulas.
```
table#tabelaspec td {
    border: 1px solid #606060;
}
```
Para removermos o espaco entre as celulas.
```
border-spacing: 0px;
```
Para centrarmos a tabela na nossa main section fazemos.
```
margin-right: auto;
margin-left: auto;
```
#### Colunas
Para darmos darmos um espacamento entre as linhas.
```
table#tabelaspec td {
    padding: 10px;
}
```
Para termos diferentes formatacoes na mesma tabela podemos utilizar a class no html. Vamos aplicar alteracoes na coluna da esquerda apenas.
```
table#tabelaspec td.ce {
    color: #ffffff;
    background-color: #606060;
    text-align: right;
    vertical-align: top;
    font-weight: bold;
}
```
#### Titulo
Nosso titulo da tabela.
```
table#tabelaspec caption {
    color: #888888;
    font-size: 13pt;
    font-weight: bolder;
}
```
Vamos configurar o nosso span.
```
table#tabelaspec caption span {
    display: block;
    float: right;
    color: #000000;
    font-size: 8pt;
    padding-top: 10px;
}
```

---

## Cordenadas
==A posicao default é **static**.==
Temos dois tipos de posicoes: a ==absoluta== que ira ser colocada em posicao consoante qual for o seu pai hierarquico. E a ==relativa== que podera ser colocada no site consoante a sua posicao no documento html.

## Imagens
### Inserir uma imagem via CSS
Para adicionarmos imagens digitamos:
```
<img src="_imagens/glass-oculos-preto-peq.png">

//ou
<img src="link" width=220 height=50>
```

A tag 'figure' semanticamente para o html 5 significa uma area especifica para delimitar imagens que fazem parte de conteudos para colocarmos uma legenda da imagem. 
```
<figure>
    <img src="_imagens/glass-quadro-homem-mulher.jpg">
</figure>
```

A tag 'figcaption' da uma legenda para a nossa imagem facilitando assim o usuario a visitar o nosso site e permitindo uma melhor organizacao no nosso site. Para podermos no CSS alterar as propriedades deste grupo figure dando uma classe.
```
<figure class="foto-legenda">
    <img src="_imagens/glass-quadro-homem-mulher.jpg">
            <figcaption>
                <h3>Google Glass</h3>
                <p>Uma nova maneira de ver o mundo.</p>
            </figcaption>
</figure>
```

### Imagens em CSS
Para defenirmos uma imagem como fundo em CSS utilizamos o "background-image" com os seguintes parametros:

==Nota:== In a **background** property you can add background-color, repeat, no-repeat and other image attributes, but in the **background-image** property you are only allowed to add image.
```
<style>
    body {
    
        // vai fazer com que a imagem nao se repita fique centrada e fixa
        background: url("fundo.jpg") no-repeat center center fixed;
        
        //Para se adaptar ao ecra
        background-size: cover;
    }
</style>
```

Podemos adicionar imagens via img que é o mais comum ou por CSS. Para fazermos por CSS. ==Como estamos no ficheiro 'estilo.css' temos de voltar atras utilizando os '..' para podermos chamar a imagem.==
```
background: url("../_imagens/glass-logo-peq.jpg")
```

Mas como a imagem é pequena o css replicou a imagem. Para resolvermos utilizamos o non-repeat.
```
background: url("../_imagens/glass-logo-peq.jpg") non-repeat;
```

Para alterarmos a posicao dele. O primeiro 0px diz respeito ao deslocamento horizontal e o outro é vertical.
```
background: url("../_imagens/glass-logo-peq.jpg") non-repeat 0px 80px;
```

Para chamar figure em css fazemos da seguinte maneira. Colocamos o nome da tag e o nome da classe.
```
figure.foto-legenda{

}
```

---

### Bordas
Para configurar uma borda utilizamos o 'border'. Primeiro definimos a largura desta, o tipo desta e a cor.
```
figure.foto-legenda {
    border: 8px solid red;
}
```

Ira verificar que algo nao esta bem, para resolver este problema iremos configurar a imagem para usar 100% de altura e largura.
```
figure.foto-legenda img {
    width: 100%;
    height: 100%;
}
```
### Legendas
Vamos remover a figcaption. A posicao vai ter uma posicao absoluta dentro do seu container que no caso é a nossa borda vermelha.
```
figure.foto-legenda figcaption {
    position: absolute;
    top: 0px;
}
```

Se quisermos criar uma caixa dentro da borda(container) utilizamos o 'box-sizing':
```
figure.foto-legenda figcaption {
    box-sizing: border-box;
}
```

Para gerirmos a ocupacidade da nossa legenda: 
```
figure.foto-legenda figcaption {
    opacity: 0;
}
```

Se quisermos com que a nossa legenda apareca ao colocar o rato em cima utilizamos o 'hover':
```
figure.foto-legenda:hover figcaption {
    opacity: 1;  //escurece
    transform: scale(1.1);  //aumenta a imagem de tamanho
}
```

Para um efeito de transicao utilizamos o 'transition':
```
figure.foto-legenda:hover figcaption {
    transition: all 1s;
}
```

### Efeito sombra
Para fazer este efeito utilizamos o 'box-shadow' com os seguintes paramentros: deslocamento horinzontal, vertical, espalhamento e cor.
```
box-shadow: 1px 1px 4px black;
```
---

### Formatos de imagens
Utilize PNG se quiser ter imagens com maior resolucao ou se quiser utilizar o modo transparencia. No entanto se quiser ter um site mais leve utilize JPG porque sites pesados exigem demais do servidor.
Quando for colocar imagens no seu site existe uma opcao em qualquer editor de imagem que é ==exportar para a web== sendo este um ficheiro mais leve para o seu site.


## Seccoes
A tag para criar cabecalhos é chamda de header:
```
<header id="cabecalho"></header>
```

## Simbolos especiais
Para criarmos simbolos especiais fazemos da seguinte maneira:
```
&copy;  # copy right
&reg;  # marca registada
&trade;  # trade mart
```

No caso de querermos criar o sinal de < e > sem o html os considerar como tags:
```
&lt;
&gt;
```

## Code(linguagens de programacao)
Se quisermos indicar ao html semanticamente que queremos mostrar linguagens de programacao utilizamos a tag:
```
<code>
if maiordeidade >= 18:
    print('Adulto')
else:
    print('A crescer')
</code>
```

Esta tag apenas indica ao html semanticamente e nao formata visualmente o nosso codigo. Para isso temos a tag 'pre' que permite que todos os meus espacos sejam considerados.
```
<pre>
<code>
if maiordeidade >= 18:
    print('Adulto')
else:
    print('A crescer')
</code>
</pre>
```

## Links
Para transformarmos palavras em links utilizamos 'a' significando **ancora** sendo esta a base da criacao do link e para que ele funcione temos de utilizar uma referencia 'href'.
```
<a href="http://glass.google.com">Project Glass</a>
```
Como esta ligacao abre na mesma pagina que o nosso site, vamos acrescentar um parametro para abrir a ligacao noutra aba.
```
<a href="http://glass.google.com" target="_blank">Project Glass</a>
```







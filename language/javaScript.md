**Author:** Duarte Matos
###### tags: `Language`, `JavaScript`

# JavaScript

![](https://i.imgur.com/2EiBLrE.png)

## O que é Js?
Se você trabalha com desenvolvimento web, conhecer JavaScript não é opcional. Essa é a linguagem de programação que roda em 100% dos navegadores, e por isso está presente em praticamente todos os projetos online.

Com JavaScript você é capaz de controlar todo o comportamento da sua aplicação no navegador, levando a experiência do usuário para outro nível e deixando sua interface totalmente dinâmica.

Além de ser essencial no desenvolvimento web, o JavaScript vem sendo muito utilizado em desenvolvimento mobile, tanto através de ferramentas híbridas como Ionic quanto tecnologias mais modernas como React Native.

Com React Native é possível inclusive desenvolver apps nativos para iOS e Android e manipular todos os recursos do smartphone como GPS, câmera, arquivos, contatos, diretamente com JavaScript.

E por tudo isso o JavaScript é a linguagem de programação mais popular da web e que possui a maior comunidade, além de ser uma das mais modernas e que vem evoluindo mais rápido, sendo aplicada na robótica, no desktop, no mobile e até machine learning.

## JavaScript não é Java
A primeira coisa que você precisa saber: JavaScript não tem nada a ver com Java. Java é uma linguagem server-side, como PHP, Ruby, Python e tantas outras. A única coisa parecida entre eles é o nome. ;-)

Sabendo disso, quero que saiba que JavaScript é uma linguagem de programação client-side. Ela é utilizada para controlar o HTML e o CSS para manipular comportamentos na página. Me pergunte agora: "Como assim comportamento?". Agora eu respondo: um comportamento comum, por exemplo, é um submenu. Sabe quando você passa o mouse em um ítem do menu, e aparece um submenu com vários outros ítens? Pois é. A obrigação de fazer aparecer esse submenu é do JavaScript. O submenu estava escondido, e quando passamos o mouse no ítem, o submenu aparece. Todo esse comportamento quem vai executar é o JavaScript.

## Quem criou o JavaScript?
O JavaScript não foi criado pelo W3C, como muitos pensam. Na verdade ele foi criado por um cara chamado Brendan Eich na Netscape (um dos precursores dos navegadores web). Ele se chamava LiveScript, mas logo seu nome foi mudado para JavaScript. Mesmo assim o nome original é ECMAScript, por que o JavaScript é mantido pela European Computer Manufacturer's Association. Ou seja, chame de JavaScript mesmo, que é como todo mundo chama.

Voltando ao assunto principal: o JavaScript não é mantido pelo W3C, ele é uma linguagem criada e mantida pela ECMA. Eles mantém uma documentação da linguagem no site deles, mas a melhor documentação ainda são os materiais que você pode encontrar na web mesmo.

## Camada de comportamento
Você já deve ter lido a parte que fala sobre o desenvolvimento separando em camadas, onde explicamos que existem três camadas básicas no desenvolvimento para Web: a informação que fica com o HTML, a formatação, que fica com o CSS e o comportamento, que fica com o JavaScript.

O JavaScript é a terceira camada de desenvolvimento por que ele manipula as duas primeiras camadas, isto é: HTML e CSS. Imagine que você precise de um Slider de imagens. Toda a movimentação, ações de cliques nas setinhas e etc, é o JavaScript que vai cuidar. É isso que chamamos de comportamento.

## Orientado a Objeto
Talvez seja cedo demais para falar sobre orientação a objetos em linguagens de programação, mas você precisa saber, pelo menos, que o JavaScript é uma linguagem com Orientação a Objetos. Não vamos entrar em detalhes agora, não queremos que você confunda as bolas. Mas saiba que um objeto na programação é um conjunto de informações. Objeto é um grupo de dados. Mas por hora, fique apenas com essas informações. Vamos nos aprofundar em momento oportuno.

## Bibliotecas vs Frameworks
==Bibliotecas:== conjunto de funcoes/codigos que poderao ser chamados para os nossos projetos quando necessarios(jQuery)
==Frameworks:== precisa se de entender como este funciona e respeitar a sua maneira de trablhar(Angular)

# Comandos de iteracao com o usuario
Para executar o Js no ficheiro html teremos de o fazer no ==body==:
```
<script>  // maior parte dos comandos em Js comeca por minuscula
</script>  // no Js nao precisa do ; para nada
```

Tendo colocado a tag 'script' dentro do body podemos digitar Js. Ira retornar um pop-up ao entrar no site, dando ok o site ira ser mostrado ao usuario.
```javascript=
window.alert('Minha 1 mensagem')
// ou
alert('Minha 1 mensagem') 
```

A funcao ==write== escreve o que estiver dentro de parenteses no corpo de html.
1. Exemplo (Ola, Mundo!):
```javascript=
document.write('Ola, Mundo!')
```
2. Exemplo (Data do sistema):
```javascript=
document.write('Ola, hoje é dia' + Date())
```

3. UFT-8, grupo de caracteres
```javascript=
window.document.write(window.charset)
```

4. Diz me o navegador
```javascript=
window.document.write(window.navigator.appname) 
```

5. Mostra o link onde esta o nosso site
```javascript=
window.document.write(window.document.URL)
```

Apresenta uma caixa de confirmacao.
```javascript=
window.confirm('Esta a gostar de Js')
```

Permite digitar na caixa de alerta, e este por default so recebe string.
```javascript=
window.prompt('Qual é o seu nome')
```

Para escrever algo na consola do navegador
```
console.log('Heloooo')
```

# Variáveis
No JavaScript moderno, alem de utilizar a palavra "var", tambem podemos usar "let" ou "const".

==Escopo local== -> var/let/const
==Escopo global== -> window

1. Identificadores no JavaScript sao os nomes das variaveis
2. Podem comecar com uma "letra", "$" ou "_"
3. Nao podem comecar com numeros
4. É possivel usar letras ou numeros
5. É possivel usar acentos e simbolos
6. Nao pode conter espacos
7. Nao podem ser palavras reservadas

## Const
A constant is a variable that cannot be changed. Like other languages had done before it, JavaScript introduced constants with ES6.
Before constants, all we had were variables, and variables could be overwritten:
```
var pizza = true
pizza = false
console.log(pizza) // false
```
We cannot reset the value of a constant variable, and it will generate a console error if we try to overwrite the value:
```
const pizza = true
pizza = false
```

## Let
The topic variable inside the if block resets the value of topic.
With the let keyword, we can scope a variable to any code block. Using let protects the value of the global variable:
```
var topic = "JavaScript"
if (topic) {
let topic = "React"
console.log('block', topic) // React
}
console.log('global', topic) // JavaScript
```

## Dicas para as variaveis:
1. Maiusculas e minimusculas fazem diferenca
2. Tente escolher nomes coerentes para as variaveis

## Representar Strings em Js
```
var s1 = "JavaScript"
var s2 = 'JavaScript'
var s3 = `JavaScript`
```

# Tipo de Dados
1. Number:
```
valores internos:
	Infinity
	NaN        //not a number
```
2. string
3. boolean
4. null
5. symbol
6. undefined(quando nada estiver associado a nada)
7. object:
```
Array
```

8. function

## Typeof
Para sabermos o tipo de variavel digitamos:
var n = 200
typeof n	  //typeof "variavel"
=='number'==

typeof 6         //typeof "valor"
=='number'==

typeof []
=='object'==

typeof {}
=='object'==

typeof function(){}
=='function'==

typeof undefined
=='undefined'==

typeof NaN
=='number'==

typeof Infinity
=='number'==

typeof null
=='object'==

# Tratamento de Dados
(number + number) -> Adicao
(string + string) -> Concatenacao

## Converter String para numero
```
# converter para inteiro
Number.parseInt(n) 

# converter para float
Number.parseFloat(n)  

# Sozinho consegue determinar que tipo de variavel ele tem de converter
Number(n)  

# se o valor vier em string de um input
Number(n.value)  
```

## Converter numero para String
```
String(n)
n.toString()
```

## Formatando strings
```
// Podemos utilizar \' para aprostefes
'This isn\'t very nice'

nome = 'Duarte'
`O ${nome} ganhou.`

# quantos caracteres a string tem
nome.length  

# tudo para MAIÚSCULAS
nome.toUpperCase()  

# tudo para minúsculas
nome.toLowerCase()  
```

## Formatando Ints:
```
var n1 = 1543.5
n1

// formata para 2 casas decimais
n1.toFixed(2)

// localiza a string por 'pt-PT' no estilo de sistema de moedas EUR
n1.toLocaleString('pt-PT', {style: 'currency', currency: 'EUR'})  
```

# Operadores
## Aritméticos
```
Operadores:
    5 + 2 -> 7
	5 - 2 -> 3
	5 * 2 -> 10
	5 / 2 -> 2.5
	5 % 2 -> 1
	5 ** 2 -> 25
Precedencia:
	()
	**
	* / %
	+ -
```
## Atribuicao
```
n = 10
n += 1
n = 11
n ++
11
n
12
++ n
13
```

## Relacionais
```
">"
"<"
">="
"<="
"=="
"!="
	Identidade:
	5 == 5  # True
	5 == '5'  # True, excessao do Js
	5 === '5'  # False, por o tipo de variavel ser diferente
	5 === 5  # True
```


## Lógicos
```
!  # negacao
	&&  # conjuncao or "and"
	||  # dinjuncao or "or"
	
    Negacao(unario):
    !true -> false
    !false -> true
        
Conjuncao(binario):
true && true  # true
true && false  # false
false && true  # false
false && false  # false
    
Disjuncao(binario):
true || true  # true
true || false  # true
false || true  # true
false || false  # false
```

## Ternário
```
'condicao' ? True : False
```

## Ordem dos operadores
1. operadores aritmeticos
2. operadores relacionais
3. operadores logicos


## Ordem dos operadores logicos
1. !
2. &&
3. ||

# Funcoes
Bloco de comandos que executam uma acao
```
function nome(parametros){
	bloco
}
```

## Funcao Expressao
```
var a = function(){
    bloco
}
```

## Arrow Functions
With the arrow, we now have an entire function declaration on one line. The function keyword is removed. We also remove return because the arrow points to what should be returned. Another benefit is that if the function only takes one argument, we can remove the parentheses around the arguments.
```
var lordify = firstname => `${firstname} of Canterbury`
```
More than one argument should be surrounded by parentheses:
```
// Old
var lordify = function(firstName, land) {
return `${firstName} of ${land}`
}
// New
var lordify = (firstName, land) => `${firstName} of ${land}`
console.log( lordify("Dale", "Maryland") ) // Dale of Maryland
console.log( lordify("Daryle", "Culpeper") ) // Daryle of Culpeper
```
More than one line needs to be surrounded with brackets:
```
// Old
var lordify = function(firstName, land) {
if (!firstName) {
throw new Error('A firstName is required to lordify')
}
if (!land) {
throw new Error('A lord must have a land')
}
return `${firstName} of ${land}`
}

// New
var _lordify = (firstName, land) => {
if (!firstName) {
throw new Error('A firstName is required to lordify')
}
if (!land) {
throw new Error('A lord must have a land')
}
return `${firstName} of ${land}`
}
console.log( lordify("Kelly", "Sonoma") ) // Kelly of Sonoma
console.log( lordify("Dave") ) // ! JAVASCRIPT ERROR
```
Arrow functions do not block this. For example, this becomes something else in the setTimeout callback, not the tahoe object:
```
var tahoe = {
resorts: ["Kirkwood","Squaw","Alpine","Heavenly","Northstar"],
print: function(delay=1000) {
setTimeout(function() {
console.log(this.resorts.join(","))
}, delay)
}
}
tahoe.print() // Cannot read property 'join' of undefined
```
This error is thrown because it’s trying to use the .join method on what this is. In this case, it’s the window object. Alternatively, we can use the arrow function syntax to protect the scope of this:
```
var tahoe = {
resorts: ["Kirkwood","Squaw","Alpine","Heavenly","Northstar"],
print: function(delay=1000) {
setTimeout(() => {
console.log(this.resorts.join(","))
}, delay)
}
}
tahoe.print() // Kirkwood, Squaw, Alpine, Heavenly, Northstar
```
This works correctly and we can .join the resorts with a comma. Be careful, though, that you’re always keeping scope in mind. Arrow functions do not block off the scope of this:
```
var tahoe = {
resorts: ["Kirkwood","Squaw","Alpine","Heavenly","Northstar"],
print: (delay=1000) => {
setTimeout(() => {
console.log(this.resorts.join(","))
}, delay)
}
}
tahoe.print() // Cannot read property resorts of undefined
```
Changing the print function to an arrow function means that this is actually the window.


# Lists/Arrays
Lists podem conter qualquer coisa que nos queiramos tipo numeros, functions, lists...
```
var list = ['tiger', 'cat', 'bear']
list[0]  // tiger
```

## List dentro de List
```
var list = [['tiger', 'cat', 'bear']]
list[0]  // ['tiger', 'cat', 'bear']
list[0][1] //cat
```

## Remover elementos
```
var list = ['tiger', 'cat', 'bear']
```

Remove o primeiro elemento da lista('tiger')
```
list.shift()  // ['cat', 'bear']
```

Remove o ultimo elemento da lista('bear')
```
list.pop()  // ['cat']
```

## Adicionar elementos
Para adicionarmos um elemento na lista
```
list.push('Elephant')  // ['cat', 'Elephant']
```

O metodo **concat()** é usado para juntar dois ou mais arrays. ==Este metodo nao altera os arrays atuais, mas retorna um novo array, contendo os valores dos arrays adicionados.==
```
list.concat(['bee', 'deer'])  // ['cat', 'Elephant', 'bee', 'deer']
```

## Metodos
Organiza a lista alfabeticamente
```
list.sort()
```

Apresenta a lista de maneira reversa
```
list.reverse()
```

Mostra o comprimento da lista
```
list.length
```

# Dicionários/Objetos
```
var user = {
    name: "John",
    age: 34,
    hobby: "Soccer",
    isMarried: false,
    
    // listas dentro de dicionarios
    spells: ["abrakabra", "shazam", "wang"], 
} 

// aceder aos valores de uma lista
user.spells[1]  // 'shazam'
```

## Dicionarios dentro de listas
Funcoes dentro listas/dicionarios sao chamadas de **metodo**.
```
var list = [
    {
    username: 'andy',
    password: 'secre'
    },
    {
    username: 'jess',
    password: '123'
    }
]

// aceder a password do dicionario 0
list[0].password
```

## Funcoes dentro de dicionarios
```
var user = {
    name: "John",
    age: 34,
    hobby: "Soccer",
    isMarried: false,
    shout: function() {
        console.log('AHHHHH')
    }
    
// Chamar funcao atraves de um dicionario
user.shout()
```

## Adicionar/Alterar Dicionarios
Adicionar elementos
```
user.favouriteFood = 'spinach'
```

Alterar elementos
```
user.isMarried = true
```

# Destructuring Assignment
## Objects/ Dicionaries
The destructuring assignment allows you to locally scope fields within an object and to declare which values will be used.
Consider this sandwich object. It has four keys, but we only want to use the values of two. We can scope bread and meat to be used locally:
```
var sandwich = {
bread: "dutch crunch",
meat: "tuna",
cheese: "swiss",
toppings: ["lettuce", "tomato", "mustard"]
}
var {bread, meat} = sandwich
console.log(bread, meat) // dutch crunch tuna
```
The code pulls bread and meat out of the object and creates local variables for them. Also, the bread and meat variables can be changed:
```
var {bread, meat} = sandwich
bread = "garlic"
meat = "turkey"
console.log(bread) // garlic
console.log(meat) // turkey
console.log(sandwich.bread, sandwich.meat) // dutch crunch tuna
```
We can also destructure incoming function arguments. Consider this function that would log a person’s name as a lord:
```
var lordify = regularPerson => {
console.log(`${regularPerson.firstname} of Canterbury`)
}
var regularPerson = {
firstname: "Bill",
lastname: "Wilson"
}
lordify(regularPerson) // Bill of Canterbury
```
Instead of using dot notation syntax to dig into objects, we can destructure the values that we need out of regularPerson:
```
var lordify = ({firstname}) => {
console.log(`${firstname} of Canterbury`)
}
lordify(regularPerson) // Bill of Canterbury
```
Destructuring is also more declarative, meaning that our code is more descriptive about what we are trying to accomplish. By destructuring firstname, we declare that we will only use the firstname variable. We’ll cover more on declarative programming in the next chapter.

## Arrays/Lists
Values can also be destructured from arrays. Imagine that we wanted to assign the first value of an array to a variable name:
```
var [firstResort] = ["Kirkwood", "Squaw", "Alpine"]
console.log(firstResort) // Kirkwood
```
We can also pass over unnecessary values with list matching using commas. List matching occurs when commas take the place of elements that should be skipped.
With the same array, we can access the last value by replacing the first two values with commas:
```
var [,,thirdResort] = ["Kirkwood", "Squaw", "Alpine"]
console.log(thirdResort) // Alpine
```
Later in this section, we’ll take this example a step further by combining array destructuring and the spread operator.

# Object Literal Enhancement
Object literal enhancement is the opposite of destructuring. It is the process of restructuring or putting back together. With object literal enhancement, we can grab variables from the global scope and turn them into an object:
```
var name = "Tallac"
var elevation = 9738
var funHike = {name,elevation}
console.log(funHike) // {name: "Tallac", elevation: 9738}
```
name and elevation are now keys of the funHike object.
We can also create object methods with object literal enhancement or restructuring:
```
var name = "Tallac"
var elevation = 9738

var print = function() {
console.log(`Mt. ${this.name} is ${this.elevation} feet tall`)
}
var funHike = {name,elevation,print}
funHike.print() // Mt. Tallac is 9738 feet tall
```
Notice we use this to access the object keys.








# DOM
Document Object Model(DOM):
Conjunto de objectos dentro do browser que ira dar acesso aos componentes
internos do nosso website.
É utilizado pelo browser para representar a sua pagina web. Nao funciona no **NodeJs**, so funciona no browser.

![](https://i.imgur.com/BBnPD17.png)

## Arvore DOM
```
window: tudo dentro do Js esta dentro do objecto window
	location: localizacao do site, qual é a URL, pagina anterior e pagina atual
	document: documento atual
		html:
			head:
				meta
				title
			body:
				h1
				p
				p:
					strong
				div
	history: vai guardando de onde eu vim para onde vou
```

## Seletores da arvore
Podemos acessar aos elementos da arvore DOM:

### getElementsByTagName()
Por **Marca(tag)** consigo selecionar mais do que um objecto, dentro de head e body.
```
getElementsByTagName("coloque a tag que deseja ver")
```

### getElementById()
Por **ID** para sites mais evoluidos, selecionando mais generalizado tipo uma familia deles ou apenas um. referenciando por id nas familias <div id='msg'>
```
getElementById()
```

### getElementsByName()
Por **Nome** se tiver uma propriedade name, tenho de utilizar [] por ser mais que um objecto é tipo marca. referenciando por name <div name='msg'>
```
getElementsByName()
```

### getElementsByClassName()
Por **Classe** se tiver uma propriedade class, tenho de utilizar [] por ser mais que um objecto é tipo marca. referenciando por class <div class='msg'>
```
getElementsByClassName()
```

Se esse classe for um array para podermos ver seu  conteudo
```
document.getElementByClassName('second')
[p.second]

//colocamos o index numero e conseguimos ver o que esta la
document.getElementByClassName('second')[0]
```

### querySelector() / all
Por **Seletor(CSS)** funciona tal e qual o **ID** mas desta vez representado por **"#"**. ex: <div id='msg'> window.document.querySelector('div#msg').
Se for uma **classe** representamos por **"."** temos outro exemplo: <div class='msg'> window.document.querySelector('div.msg')
```
querySelector()
```
6. Funciona como o plural
```
querySelectorAll()
```

### getAttribute/set
Se quisermos pegar o atributo de alguma tag por exemplo
```
document.querySeletor('li')
<li random='100'>Notebook</li>

document.querySelector('li').getAttribute('random')
'23'
```
Se quisermos alterar o atributo 
```
document.querySelector('li').setAttribute('random', 100)

document.querySeletor('li')
<li random='100'>Notebook</li>
```

### Mudar estilos
Se quisermos mudar por exemplo o nosso background do titulo
```
//style.{property} 
document.querySelector('h1')
<h1>Shopping List</h1>

document.querySelector('h1').style.background='yellow'
'yellow'
```

Se quisermos adicionar classes(className)
```
var h1 = document.querySelector('h1')

h1.className = 'coolTitle'
'coolTitle'

h1
<h1 class='coolTitle'>Shopping List</h1>
```

### ClassList
Para adicionarmos(classList.add), removermos(classList.remove) ou ligar/desligar(classList.toggle) um item fazemos
```
document.querySelector('li').classList
["bold", "red", value: "bold red"]

document.document.querySelector('li').classList.add('coolTitle')

document.querySelector('li').classList.remove('coolTitle')

document.querySelector('li').classList.toggle('coolTitle')
flase

document.querySelector('li').classList.toggle('coolTitle')
true
```

### innerHTML
Para alterarmos o nosso html atraves do Js
```
document.document.querySelector('h1').innerHTML = '<strong>!!!</strong>'
```

### Parent/Child
Da nos informacao acerca do elemento selecionado dizendo qual é o seu pai ou seu filho
```
document.querySelector('li')[1]
<li>Jello</li>

document.querySelector('li')[1].parentElement
<ul></ul>

document.querySelector('li')[1].parentElement.parentElement
<body></body>

// mostra todos os filhos de body
document.querySelector('li')[1].parentElement.parentElement.children
[h1, p,ul]
```

# Eventos
## Eventos DOM
É tudo o que possa acontecer com qualquer elemento podemos criar eventos em html ou Js, MAS as functions sao feitas em Js dentro da 'div' pode ocorrer varios eventos de mouse como:

**mouseenter**  # quando o rato entra na div
**mousemove**  # continuar movendo o rato dentro da div
**mousedown**  # clicar e segurar o botao do rato
**mouseup**  # no momento em que deixar de segurar o botao do rato
**click**  # apertar e soltar de imediato
**mouseout**  # quando o rato sai da div


## Criar eventos no html
1. Criamos o evento clicar 
```
<div id='area' onclick='clicar()'>
```
2. A seguir criamos functions no Js

## Criar eventos no Js
Criamos uma variavel global.
==Nota:== Atencao porque muitas vezes ao buscar objetos podem vir arrays e com eles nao podemos trabalhar
```
var button = document.getElementByTagName('button')[0]

// "variavel".addEventListener("evento(ex: click)", "nome da function") 
button.addEventListener("click", function() {
    console.log('CLICK!')
})
```

## createElement()
Podemos criar elementos utilizando o "createElement()":
Neste exemplo adicionamos uma imagem:
```
// cria uma imagem 'img' igual a 'img'
var img = window.document.createElement('img')

// define o atributo da imagem como id='foto'
img.setAttribute('id', 'foto')

// como criamos o objecto imagem teremos que o definir 
na arvore DOM como filho da div "resultado"
resultado.appendChild(img)
```
Neste exemplo adicionamos um elemento 'li' a nossa lista 'ul' clicando em um botao
```
var button = document.getElementById('enter')
var input = document.getElementById('userinput')
var ul = document.querySelector('ul')

button.addEventListener('click', function() {
    var li = document.createElement('li')
    
    // Adiciona 'li' como filho dando como texto o valor do nosso input.
    li.appendChild(document.createTextNode(input.value))
    ul.appendChild(li)
    
    // Para apagar o nosso input
    input.value = ''
})
```
Neste exemplo vamos clicar ENTER e vamos executar alguma acao.

==Note:== As teclas do teclado sao chamadas de KeyCode 
```
var input = document.getElementById('userinput')

input.addEventListener('keypress', function() {
   if (event.keyCode == 13)
})
```

# Condicoes
==Condicoes simples e compostas==
```
if(condicao){
	bloco de comandos  # True
} else {
	boloco de comandos  # False
}
```

==Condicoes Aninhadas==
```
if(condicao1){
	bloco1
}else{
	if(condicao2){
		bloco2
	}else{
		bloco3
	}
}
```

==Condicao Multipla==
```
switch (expressao){
	case valor1:
		bloco 1
		break
	case valor2:
		bloco 2
		break
	case valor3:
		bloco 3
		break
	default:
	bloco 4
	break
}
```

# Estruturas de Repeticao
==While==
```
function comerPizza(){
	while (temFatia()){
	comerFatia()
	}
}
```

==Do While==
```
do{
	comerFatia()
} while (temFatia())
```

==For==
```
for (var c = 1; c <= 6; c++){
	console.log(c)
}
```

==forEach==
```
function logTools(value, index) {
    console.log(value, index)
}

tools = ['martelo', 'piquereta', maco]
tools.forEach(logTools)
```

# Testes

# Bibliotecas & Frameworks
==Bibliotecas:==
![](https://i.imgur.com/h9Z0FcD.png)


==Frameworks:==
![](https://i.imgur.com/KNsFrpq.png)


# Recursos
==Pagos:==
- JavaScript O'RELLY'
- JavaScript guia do programador NOVATEC

==Gratuitos:==
- Mozilla
https://developer.mozilla.org/pt-PT/docs/Web/JavaScript

- Js, reactJs, node.js e react native 
https://rocketseat.com.br/starter

- 9 Free Programming Courses by Harvard, MIT, IBM, Google, and Microsoft
https://medium.com/better-programming/9-courses-to-learn-for-free-d7951a959f82

- Conteudo de frontend/backend/devOps/fullstack
https://free-for.dev/#/


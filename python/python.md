**Author:** Duarte Matos
###### tags: `Python`

# **Python**

![](https://i.imgur.com/x6wGT0E.png)

## **O que é Python?**
- Python é uma linguagem de programação criada por Guido van Rossum em 1991. Os objetivos do projeto da linguagem eram: produtividade e legibilidade. Em outras palavras, Python é uma linguagem que foi criada para produzir código bom e fácil de manter de maneira rápida. Entre as características da linguagem que ressaltam esses objetivos estão:

- Além disso, Python suporta múltiplos paradigmas de programação. A programação procedimental pode ser usada para programas simples e rápidos, mas estruturas de dados complexas, como tuplas, listas e dicionários, estão disponíveis para facilitar o desenvolvimento de algoritmos complexos. Grandes projetos podem ser feitos usando técnicas de orientação a objetos, que é completamente suportada em Python.

- Python tem uma biblioteca padrão imensa, que contém classes, métodos e funções para realizar essencialmente qualquer tarefa, desde acesso a bancos de dados a interfaces gráficas com o usuário.

- Por fim, e não menos importante, Python é uma linguagem livre e multiplataforma. Isso significa que os programas escritos em uma plataforma serão executados sem nenhum problema na maioria das plataformas existentes sem nenhuma modificação.

## Por que Python?

![](https://i.imgur.com/oqRfYad.png)

---

# **Operadores Aritmeticos**
==Ordem de precedencia==
```
#1 -> ()
#2 -> **
#3 -> * / // %
#4 -> + -
```

==Funcao potencia/raiz quadrada==
```
pow(n, (1/2))
```

==Raiz quadrada==
```
81**(1/2)
```

==Raiz cubica==
```
81**(1/3)
```

# **Cores no Terminal**
==Codigo==
```
\033[0:33:44m
\033[7:30m
```

==Style==
```
0 none
1 bold
4 underline
7 negative
```

==Text==
```
30 branco
31 vermelho
32 verde
33 amarelo
34 azul
35 roxo
36 azul bebe
37 cinzento
```

==Background==
```
40 branco
41 vermelho
42 verde
43 amarelo
44 azul
45 roxo
46 azul bebe
47 cinzento
```

# **String**

- String literals in python are surrounded by either single quotation marks, or double quotation marks.

![](https://i.imgur.com/BGoBtKs.png)

## Fataiamento de Strings

- No fatiamento de strings tendo uma variavel como string podemos desejar ver o que nos interessa no print fatiando como queremos: 
```python=
frase = 'Curso em video de python'
```

- Podemos fatiar de muitas formas como:
1. Como cada letra numa string é um caracter podemos buscar so um caracter da lista de caracteres:
```python=
frase[9]
```

2. Ira do 9 ao 12 (o ultimo eh sempre o anterior do limite estabelecido).
```python=
frase[9:13]
```

3. Ira do 9 ao 20 mas de 2 em 2.
```python=
frase[9:21:2]
```

4. Ira comecar no 9 e ira ate ao ultimo caracter pulando de 3 em 3.
```python=
frase[9::3]
```

5. Ira selecionar tudo o que vier antes ate ao 4.
```python=
frase[:5]
```

6. Ira comecar no 15 ate ao ultimo caracter.
```python=
frase[15:]
```

7. Ira buscar tudo a comecar pelo 1.
```python=
frase[1::] 
```

8. Para buscar o último caracter utiliza se o -1.
```python=
frase[-1] 
```

## Analise de Strings

- Temos varias funcoes que nos ajudam a analisar a string 'frase':
```python=
frase = 'Curso em video de Android'
```

1. Vai avaliar o comprimento da string.
```python=
len(frase)
```

2. Vai contar quantos Xs existem na string.
```python=
frase.count('x')
```

3. Vai contar quantos Xs existem na string de 0 a 12.
```python=
frase.count('x', 0, 13)
```

4. Vai procurar a string 'deo' e se encontrar ira indicar em que caracter comeca.
```python=
frase.find('deo')
```

5. Vai comecar a analisar do lado direito e indica o caracter onde está o 'A'.
```python=
frase.rfind('A')
```

6. Se a palavra 'Android' nao existir na frase ele ira retornar -1 se nao retorna o em que posicao esta o caracter 'A'.
```python=
frase.find('Android')
```

7. Ira validar se na string frase existe 'Curso' ira retornar True or False.
```python=
'Curso' in frase
```

## Transformacao de Strings

- Podemos alterar strings a partir de funcoes:
```python=
frase = 'Curso em video de Android'
```

1. Ira trocar a palavra 'Python' por 'Android'.
```python=
frase.replace('Python', 'Android')
```

2. Elimina espacos no meio da frase.
```python=
frase.replace(' ', '')
```

3. Tudo fica em maiusculas.
```python=
frase.upper()
```

4. Tudo fica em minusculas.
```python=
frase.lower()
```

5. Ira apenas tornar a primeira letra em maiuscula e tudo o resto em minusculas.
```python=
frase.capitalize()
```

6. Todas as palavras que estiverem separadas por espaco, a primeira letra ficara em maiuscula.
```python=
frase.title()
```

7. Ira remover todos os espacos inuteis no inicio e no fim.
```python=
frase.strip()
```

8. Ira remover apenas o espaco inutil do lado direito
```python=
frase.rstrip()
```

9. Ira remover apenas o espaco inutil do lado esquerdo
```python=
frase.lstrip()
```

## Divisao de String

- Ira dividir por espacos as palavras da string e separa las. Depois de divididas estarao individualmente separadas entre elas. Basicamente o split gera uma lista de todas as palavras com uma serie de caracteres.
```python=
frase.split()
```

## Juncao de String

- Ira juntar de novo o que o split dividiu.
```python=
''.join(frase)
```

# **Modulos**
- Consider a module to be the same as a code library. A file containing a set of functions you want to include in your application.

## Importar todo o modulo

 - Como importar todos os modulos de uma biblioteca:
```python=
import math
```

## Importar so o necessário

 - Importar um unico modulo de uma biblioteca:
```python=
from math import sqrt
```

## Alias

 - O 'Alias' renomeia o nome do modulo ou biblioteca.
```python=
from math import sqrt as raiz
```

# **Listas**
- List is a collection which is ordered and changeable. Allows duplicate members.

## Como criar listas
```python=
valores = list()
# or
valores = []
```

## Adicionar elementos
- Nas listas podemos adicionar elementos de várias formas na seguinte lista:
```python=
lanche = ['COCKIE', 'PUDIM', 'PIZZA', 'GOMAS']
print(lanche[0])  # COCKIE
```

1. Este permite adicionar novos elementos á lista lanche. Adicionará á última posicao da lista.
```python=
lanche.append('BOLACHA') 
```

2. Na posicao 0 vai inserir o 'HOT DOG' sem remover o que estiver na posicao 0.
```python=
lanche.insert(0, 'HOT DOG')
```

3. Adicionar valores a uma lista atraves do range.
```python=
valores = list(range(4,11))  # 4 5 6 7 8 9 10
```

## Alterar elmementos
- Nas listas podemos alterar elementos da seguinte maneira:

```python=
lanche = ['COCKIE', 'PUDIM', 'PIZZA', 'GOMAS']
```

1. Este comando permite trocar elementos sendo esta mutavel. Onde está 'GOMAS' ira ser mudado para 'PICOLE' pelo o facto das listas serem mutavéis.
```python=
lanche[3] = 'PICOLE' 
```

## Organizar elementos
- Para organizar a lista 'valores' podemos utilizar o 'sort' que ordena alfabéticamente ou do numero mais pequeno para o maior.
```python=
valores = (8, 2, 5, 4, 9, 3, 0)
valores.sort()  # 0 2 3 4 5 8 9
```

- Para organizar a lista 'valores' temporariamente podemos utilizar o 'sorted' que ordena alfabéticamente ou do numero mais pequeno para o maior.
```python=
print(sorted(valores))
```

- Se quisermos que ordena de forma reversa fazemos do seguinte jeito:
```python=
valores.sort(reverse = True)  # 9 8 5 4 3 2 0
```

## Eliminar elementos
- Existem várias maneiras de eliminar elementos numa lista:
```python=
lanche = ['COCKIE', 'PUDIM', 'PIZZA', 'GOMAS']
```

1. Remove o elemento indicando o caracter.
```python=
del lanche[3]
```

2. Por norma o 'pop' remove o ultimo elemento, mas se indicarmos o caracter que desejamos remover tambem remove.
```python=
lanche.pop(3)
lanche.pop()  # elimina o ultimo elemento
```

3. Remove o elemento por nome e nao por caracter.
```python=
lanche.remove('PIZZA')
```

## Copiar listas
- Para copiarmos uma lista sem fazer uma ligacao a outra lista fazemos:
```python=
a = [2, 3, 4, 7]
# b = a Faz a ligacao
b = a[:]  # faz a copia
```

## Colocar uma lista dentro de outra
- E o mesmo conceito que copiar lista, mas como queremos adicionar dados numa lista utilizamos o 'append'.
```python=
dados = ['Pedro', 25]

#colocar uma lista dentro de outra
pessoas = list()
pessoas.append(dados[:])
```

# **Tuplas**
- A tuple is a collection which is ordered and unchangeable. In Python tuples are written with round brackets.
```python=
screen = (1200, 800)
print(screen[0])  # 1200
```

# **Dicionários**
- A dictionary is a collection which is unordered, changeable and indexed. In Python dictionaries are written with curly brackets, and they have keys and values.
```python=
dados = {'NOME': 'Pedro', 'IDADE': 25}
print(dados['NOME'])  # Pedro
```

## Como criar dicionarios
```python=
dados = {}
# or
dados = dict()
```

## Adicionar/Alterar novos elementos
```python=
dados['SEXO'] = 'M'
```

## Eliminar elementos
```python=
del dados['IDADE']
```

## Mostrar elementos
```python=
filme = {'TITULO': 'Star Wars',
         'ANO': 1977,
         'DIRECTOR': 'George Lucas'}
print(filme.values())  # IRA RETORNAR APENAS OS VALORES DO DICIONARIO
print(filme.keys())  # SAO OS CAMPOS DE BAIXO
print(filme.items())  # MOSTRA TUDO DENTRO DO DICIONARIO
```

## Copiar dicionarios
```python=
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
mydict = thisdict.copy()
print(mydict)
```

## Adicionar dicionarios dentro de listas
```python=
jogos = []
jogo1 = {'nome': 'Overwatch', 'genero': 'Shooter'}
jogos.append(jogo1)
print(jogos[0]['nome'])  # Overwatch
```

## Adicionar listas dentro de dicionarios
```python=
pizza = {'crust': 'thick', 'toppings': ['mushrooms', 'extra cheese']}
print(f'Order toppings:')
for topping in pizza['toppings']:
    print(f'\t> {topping}')
```

## Adicionar dicionarios dentro de dicionarios
```python=
users = {
    'aeinstein': {
        'first': 'albert',
        'last': 'einstein',
        'location': 'princeton'
    },
    'mcurie': {
        'first': 'marie',
        'last': 'curie',
        'location': 'paris'
    }
}
for username, data in users.items():
    print(f'Username: {username.title()}')
    print(f"\tFull name: {data['first'].title()} {data['last'].title()}")
    print(f"\tLocation: {data['location'].title()}")
    print()
```

## Metodo get()
Para recuperar um valor no dicionário podemos usar o método get passando como argumento a chave do valor que queremos recuperar:
1. exemplo:
```python=
alien_0 = {'color': 'green'}
point_value = alien_0.get('points')  # opcional colocar um segundo argumento
print(point_value)
>>> None
```
2. exemplo:
```python=
alien_0 = {'color': 'green'}
point_value = alien_0.get('color')  # opcional colocar um segundo argumento
print(point_value)
>>> green
```
## Metodo set()
Remove os elementos repetidos num dicionário:
```python=
favorite_languages = {
    'jen': 'python',
    'sarah': 'c',
    'edward': 'ruby',
    'phil': 'python'}
print(set(favorite_languages.values()))
>>> {'ruby', 'python', 'c'}
```

# **If**
```python=
nome = str(input('Digite o seu nome: '))
if nome in 'Diana Alina Marisa Joana':
    print('Que nome incrivel para mulher. <3')
elif nome == 'Duarte' or nome == 'Daniel' or nome == 'Diogo':
    print('Que nomes incriveis para homem.')
else:
    print('Que nome vulgar.')
print('Tenha um bom dia, {}!'.format(nome))
```

# **Ciclos**

## For
O laço **for** nos permite percorrer os itens de uma coleção e, para cada um deles, executar o bloco de código declarado no loop. Sua sintaxe é a seguinte:
1. exemplo:
```python=
nomes = ['Pedro', 'João', 'Leticia']
for n in nomes:
    print(n)

>>> Pedro
>>> João
>>> Leticia
```
2. exemplo:
```python=
for x in "world":
  print(x)
  
>>> w
>>> o
>>> r
>>> l
>>> d
```

### Break
Com a declaracao 'break' podemos parar o ciclo antes de percorrer todos os itens:
```python=
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  if x == "banana":
    break
  print(x)

>>> apple
>>> banana
```

### Continue
Com a declaracao 'continue' podemos parar a iteracao, e continuar com o proximo:
```python=
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  if x == "banana":
    continue
  print(x)

>>> apple
>>> cherry
```

### Range
Para dar um ciclo no nosso codigo um numero de vezes,podemos usar a funcao ==range()==:
```python=
for x in range(2, 6):
  print(x)

>>> 2
>>> 3
>>> 4
>>> 5
```

## While
O while é mais utilizado quando nao temos a certeza quando o programa vai terminar, mas claro podemos arranjar maneiras de saber o fim:
```python=
c = 1
while c < 11:
    print(c)
    c = c + 1
print('FIM')
```

### Flags
```python=
active = True
while active:
    msg = input('prompt> ')
    if msg == 'quit':
        active = False
    else:
        print(msg)
```

### Continue
```python=
number = 0
while number < 10:
    number += 1
    if number % 2 == 0:
        continue
    print(number)
```

### Encher um dicionário
```python=
respostas = {}
pooling_active = True
while pooling_active:
    name = input("What's your name? ")
    game = input("What's your favourite game? ")
    respostas[name] = game  # add info to a dictionary
    repeat = input('Continue? [y/n]? ')
    if repeat == 'n':
        pooling_active = False
print('--Status--')
for key, value in respostas.items():
    print(f"{key.title()} loves {value.title()}")
```

# **Funcoes**
Uma funcao é um bloco de codigo na qual corre quando chamada.
```python=
def greeting(name='unknown'):
    print(f'Hello, {name.title()}!')  # name é o parametro da funcao

greeting('elliot')  # argumento
```

## Varios Argumentos
Para colocar um numero de parametros que nos quisermos utilizamos =='* valores'==.
```python=
def soma(* valores):
    s = 0
    for num in valores:
        s += num
    print(f'Os valores digitados foram {valores} e a soma deu {s}')

soma(2, 2)
soma(2, 5, 2)
```

## Keywords
Quando chamamos uma function podemos podemos identicar os seus parametros e os seus respetivos argumentos.
```python=
def describe_pet(animal_type, pet_name):
    print(f'I have a {animal_type.title()}.')
    print(f'My {animal_type.title()} calls {pet_name.title()}.')

describe_pet(animal_type='hamster', pet_name='joseph')
```

## Return
O ==return== retorna algo da function.
```python=
def get_name(first_name, last_name, middle_name=''):
    if middle_name:
        name = f'{first_name} {middle_name} {last_name}'
    else:
        name = f'{first_name} {last_name}'
    return name


print(get_name('Duarte', 'Matos'))
print(get_name('Duarte', 'Matos', 'Nuno'))
```

### Return Dicionários
```python=
def get_name_dictionary(first_name, last_name, age=None):
    person = {'first': first_name, 'last': last_name}
    if age:
        person['age'] = age
    return person

print(get_name_dictionary('Duarte', 'Matos', 20))
```

## Listas em Dicionários
```python=
def greetings(usernames):
    for username in usernames:
        msg = f'Hello, {username}'
        print(msg)

lista = ['elliot', 'margaret']
greetings(lista)
```

## Interactive Help
A funcao ==help()== retorna a documentacao de algum comando/funcao, ou de origem do python ou funcoes criadas por nos.
```python=
help(input)
print(len.__doc__)  # Com o __doc__ é possivel ver a funcao do len
```

## Docstrings
A docstring is a string literal that occurs as the first statement in a module, function, class, or method definition. Such a docstring becomes the ==doc== special attribute of that object.
Uma docstring é uma string que ocorre como primeiro argumento em um modulo, funcao, classe ou uma definicao de um metodo. Esta docstring torna se o atributo especial de ==doc=='.
```python=
def contagem(i, f, p):
    """
    -> Faz uma contagem e mostra na tela
    :param i: inicio da contagem
    :param f: fim da contagem
    :param p: passo da contagem
    :return: sem retorno
    Funcao criada por Duarte Matos. Nao roubar!
    """
    c = i
    while c <= f:
        print(c, end=' ')
        c += p
    print('FIM!')

contagem(2, 10, 2)
help(contagem)
```

## Variaveis globais e locais
```python=
def teste(b):
    global a  # vaiavel global
    a = 8
    print(f'O A local vale {a}')
    print(f'O B local vale {b}')

a = 5
teste(a)
print(f'O A vale global {a}')

def teste2(a):
    b = 5  # variavel local
    print(a + b)
```

# **Classes**
Python é uma linguagem de programacao orientada a objetos. Basicamente tudo em Python é um objeto, com suas propriedades e metodos.==Uma classe é como um construtor de objetos.==

==As classes comecam sempre por uma letra maiuscula.==
```python=
class Dog:
    """"Model of dog"""  # docstring

    # todos os metodos / funcoes dentro de uma classe deve se definir
    # como primeiro parametro o SELF
    def __init__(self, name, age):  # inicializador da instancia
        self.name = name
        self.age = age

    def roll_over(self):
        print(f'Yo, {self.name} rolled over!')

    def sit_down(self):
        print(f'Yo, {self.name} sit down!')

matosCao = Dog('opus', 7)  # instancia da classe Dog
print(f'O cao dos Matos se chama {matosCao.name}.')
print(f'A sua idade é de {matosCao.age} anos.')
matosCao.roll_over()
matosCao.sit_down()
```

## Funcao init()
Todas as classes teem uma funcao chamada __init__(), na qual é sempre executada quando a classe é iniciada.
Usa a funcao __init__() para atribuir valores as propriedades do objeto, ou outras opcoes necessarias para criar esse objeto.
```python=
class Car:  # main class PARENT
    """Represent a car"""

    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0  # podemos adicionar mais atributos ao nosso objecto

    def get_descriptive_name(self):
        """Description of the car"""
        long_name = f'{self.make} {self.model} {self.year}'
        return long_name

    def read_odometer(self):
        print(f'This car has {self.odometer_reading} miles on it.')

    def update_odometer(self, miles):
        if miles >= self.odometer_reading:
            self.odometer_reading = miles
        else:
            print('Valor introduzido é mais baixo que o atual!')

    def increment_odometer(self, more_miles):
        self.odometer_reading += more_miles

    def fill_gas_tank(self):
        print(f'The cars needs a gas tank')

# testes da class main Car
my_new_car = Car('audi', 'a4', 2019)
print(my_new_car.get_descriptive_name())
# 1 solucao para alterar um atributo da classe
# my_new_car.odometer_reading = 20  # podemos alterar o valor dos atributos diretamente desta forma
my_new_car.update_odometer(20)  # antes
my_new_car.read_odometer()
my_new_car.increment_odometer(10)  # depois
my_new_car.read_odometer()
```

## Parametro Self
O parametro 'self' é uma referencia á atual instancia da class, e é usada para aceder variavéis que pertencam á classe. O nome nao precisa de ser 'self', pode ser o nome que nós quisermos, mas precisa de ser o primeiro parametro de qualquer metodo na classe.
```python=
class Battery:
    def __init__(self, battery_size=75):
        self.battery_size = battery_size
        self.range = 0

    def describe_battery(self):
        """Describe the battery size."""
        print(f'This car has a {self.battery_size}-KWH battery.')

    def get_range(self):
        if self.battery_size == 75:
            self.range = 260
        elif self.battery_size == 100:
            self.range = 315
        print(f'Battery size is {self.battery_size}-KWH.')
        print(f'This car can go about {self.range} miles on a full charge.')

    def upgrade_battery(self):
        print(f'Checking if battery has 100-KWH...')
        self.battery_size = 100
        print(f'The battery has {self.battery_size}-KWH! Checked!')
```

## Funcao super()
A funcao 'super()' é usada para dar acesso aos metodos e propriedades da class pai.
A funcao 'super()' retorna um objeto que representa a classe pai.

```python=
class ElectricCar(Car):  # sub class CHILD
    """Represent aspects of a car, specific to electric vehicles"""

    def __init__(self, make, model, year):
        """Initialize attributes specific to an electric car
        Then initialize attributes of the parent class"""
        super().__init__(make, model, year)
        self.battery = Battery()  # chama mos a classe Batery

    def fill_gas_tank(self):
        print(f'The electric cars doenst need a gas tank')
```

# **Ficheiros**

## Funcao open()
Para trabalhar com um ficheiro, primeiro temos de usar a funcao open() para podermos aceder ao ficheiro. A funcao open() retorna um objeto representando o ficheiro.

## Keyword with
A keyword 'with' fecha o ficheiro uma vez que nao seja mais preciso. Automaticamente o Python irá fecha-lo. Poderas utilizar 'close()' mas é mais fácil isar 'with'.

## Metodo read()
Mostra data de um ficheiro.
```python=
with open('pi_digits', 'r') as file_object:
    content = file_object.read()
print(content)
```

Le cada linha do ficheiro uma por uma.
```python=
with open('pi_digits') as file_object:
    for line in file_object:
        print(line.rstrip())
```

## Caminho Relativo
Se nos quisermos chamar o ficheiro dentro duma pasta.
```python=
with open('pasta/filename.txt') as file_object:
```

## Caminho Absoluto
Se nos quisermos o caminho todo.
```python=
file_path = '/home/duarte/other_files/text_files/filename.txt'
with open(file_path) as file_object:
```

## Metodo readlines()
Recolhe cada linha do ficheiro e guarda as numa linha. No qual podemos continuar a trabalhar depois do bloco 'with' acabar.

```python=
with open('pi_digits') as file_object:
    lines = file_object.readlines()
for line in lines:
    print(line.rstrip())
    pi_string = ''
for line in lines:
    # pi_string += line.rstrip()
    pi_string += line.strip()
print(pi_string)
print(len(pi_string))
```

## Modos de Ficheiro
'r' read mode
'w' write mode
'a' append mode (adiciona texto no fim)
'r+' read and write mode

## Write Mode
Escreve por cima do que estiver escrito.
```python=
with open('programming', 'w') as file_object:
    file_object.write('I like Python!\n')
    # file_object.write('I like Java!\n')
```

## Append Mode
Adiciona linhas no final do ficheiro e se nao existir o ficheiro este cria o.
```python=
with open('programming', 'a') as file_object:
    file_object.write('I like C!')
```

# **Try Except**
O bloco ==try== permite testar um bloco de codigo para verificar erros.
O bloco ==except== permite nos lidar com os erros.
O bloco ==else== é executado senao existir erros.
O bloco ==finally==, se especificado, ira ser executado independentemente se o bloco **try** apresentar um erro ou nao.
```python=
print("Give me two numbers, and I'll divide them.")
print("Enter 'q' to quit.\n")
try:
    first_number = int(input('First number: '))
    second_number = int(input('Second number: '))
    answer = first_number / second_number
except ZeroDivisionError:
    print('Nenhum numero pode ser divisivel por 0.')
else:
    print(f'Resultado: {answer}')
```

## Excecao FileNotFoundError
O 'encoding' é necessário quando o 'encoding(codificacao)' do sistema padrao nao vai de encontro com o ficheiro. 
```python=
filename = 'alice.txt'
try:
    with open(filename, encoding='utf-8') as f:
        content = f.read()
except FileNotFoundError:
    print(f'Sorry, the file {filename} does not exist.')
```

# **JSON**
==JSON: JavaScript Object Notation.==
Uma outra maneira de guardarmos informacao é atraves do modulo JSON.    Permite nos guardar simples estruturas de dados em Python em um ficheiro e aceder mais tarde esses dados.
JSON é uma sintaxe para guardar e trocar dados.
```python=
import json
json.dump() store data
json.dump('piece of data to store', 'file object it can use to store data')
```

## Escrever em ficheiros JSON
Para escrever no documento utilizamos 'w'.
```python=
numbers = [2, 3, 5, 7, 11, 13]
filename = 'numbers.json'
with open(filename, 'w') as f:  
    json.dump(numbers, f)
```

## Ler em ficheiros JSON
Para lermos o ficheiro utilizamos o load e o print para mostrar na tela.
```python=
filename = 'numbers.json'
with open(filename) as f:
    print(json.load(f))
```

# **Testar codigo**

## Modulo unittest
Dispoe de ferramentas para testar o codigo.

==unit test== verifica se um aspeto especifico de uma funcao se comporta corretamente.

==test case== é uma colecao de unit tests que juntas provam que uma funcao comporta se corretamente, sem a toda a gama de situações que espera que ele lide.
 
## Importar modulo
Importamos o modulo interno de testes
```python=
import unittest 
from Fundamentos.TestingCode.name import get_formatted_name
```

## Criar classe
Esta classe deve herditar do modulo unitterst.TestCase para o python saber como correr os testes.
```
class NamesTestCase(unittest.TestCase):
    """Esta classe faz testes da funcao get_formatted_name"""
```

Nos chamamos a funcao get_formatted_name() para verificarmos se o 'first' e o 'last' name serao formatados corretamente. 
Qualquer metodo que comeca com 'test_' ira correr automaticamente quando corrermos este ficheiro.
```
    def test_first_last_name(self):
        formatted_name = get_formatted_name('duarte', 'matos')
        self.assertEqual(formatted_name, 'Duarte Matos')

    # segundo teste agora com middle_name
    def test_first_middle_last_name(self):
        formatted_name = get_formatted_name(first_name='duarte', 
                                            middle_name='nuno', last_name='matos')
        self.assertEqual(formatted_name, 'Duarte Nuno Matos')
```

Este tipo de condicao da jeito devido a frameworks que importam seus ficheiros primeiro.
se o nome deste modulo se chamar '__main__' ira fazer todos os testes correrem que estiverem na classe 'NamesTestCase'
```
if __name__ == '__main__': 
    unittest.main()  
```

## Variedade de modulos assert
Metodos assert disponiveis do unittest.Modulo TestCase:

==assertEqual(a, b)==                   verify that a == b

==assertNotEqual(a, b)==                verify that a != b

==assertTrue(x)==                       verify that x is True

==assertFalse(x)==                      verify that x is False

==assertIn(item, list)==                verify that item is list

==assertNotIn(item, list)==             verify that item is not in list

# Recursos
==Sites:==
- Basicos de Python mais detalhado
https://www.w3schools.com/python/default.asp

- Conteudo de frontend/backend/devOps/fullstack
https://free-for.dev/#/

# Desafios
==Sites:==
http://www.projecteuler.net
http://www.pythonchallenge.com
http://www.hackerrank.com
http://www.practicepython.org
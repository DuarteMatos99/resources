**Author:** Duarte Matos
###### tags: `Web`, `CSS`

# CSS

![](https://i.imgur.com/uVVW5EN.png)


## @charset
No inicio do ficheiro CSS podemos indicar que tipo de charset queremos:
```
@charset "UTF-8";
```

## @font-face
No inicio do ficheiro CSS podemos indicar que tipo de caracteres queremos. Depois para utilizar essa letra chamamos 'FontLogo' no font-family.
```
@font-face {
    font-family: 'FontLogo';
    src: url('../_fonts/bubblegum-sans-regular.otf');
}
```

## Comentarios em CSS
```
/* */
```

## Alterar cursor
Com esta propriedade alteramos o cursor para o pointer
```
cursor: pointer
```

# Box model
![](https://i.imgur.com/oHgwJWy.png)

**Padding** cria espaco a volta do content(==o padding nao permite valores negativos==)
**Margin** cria espaco a volta da borda. Se quisermos que a margem da nossa paginaseja 0 devido aos browsers nao estarem ao 0 fazemos
```
body {
    margin: 0px;
}
```

# Margin
![](https://i.imgur.com/KUYImM2.png)


# Importar fonts
No site do google fonts(https://fonts.google.com/) importamos um estilo que gostamos.
```
@import url('https://fonts.googleapis.com/css?family=Titillium+Web&display=swap');
```

E para aplicarmos fazemos o mesmo.
```
font-family: 'Titillium Web', sans-serif;
```

Ou no **HTML**:
```
<link href="https://fonts.googleapis.com/css?family=Roboto&display=swap" rel="stylesheet">
```

E para aplicarmos fazemos o mesmo.
```
font-family: 'Titillium Web', sans-serif;
```
# Unidades
## px vs em vs rem
**px** - tamanho normal

**em** - aumenta o numero de px consoante o numero de **em**(10px, 2em o resultado sera 20px )

**rem** - Relativo ao tamanho da letra do elemento root 

## ViewPort height(vh)
Relativo a 1% da altura do viewport.
```
// ira cobrir toda a view do chrome 
height: 100vh;
```

# Regras de ordem CSS
Cascading Style Sheets at the most basic level it indicates that the order of CSS rules matter. 

1. Uma class define a formatacao de varios objetos
==.class==

2. Apenas pode ser aplicado apenas para um objeto e nao para varios
==#id==

3. Simboliza todos os elementos
==*==

4. Chamamos um elemento tipo 'p'
==element==

5. Aplicamos as mesmas propriedades a dois elementos ao mesmo tempo
==element, element==

6. É utilizado para chamar objectos dentro de um objeto maior. ex: h2 p
==element element==

7. Apenas executara(ex: h2 > p) o 'p' se for filho de h2 
==element > element==

8. Apenas executara(ex: h2 + p) apenas se o p estiver a seguir de h2
==element + element==

9. Se passarmos por cima ele aplicara as modificacoes
==:hover==

10. Por exemplo numa lista ele apenas alterar o ultimo elemento
==:last-child==

11. Por exemplo numa lista ele apenas alterar o primeiro elemento
==:first-child==

12. Tornara o elemento importante e passara por cima da ordem de precedencia
==!important (not recommended)==

What seletors win out in the cascade depends on:
-**Specificity**, quanto mais especificidade um seletor tiver teem mais hipoteses de vencer

-**Importance**, dependo o que estiver na cascata(!important)

-**Source Order**, ordem do codigo

# Imagens
## Imagens Flexbox
É um layout CSS para organizar elementos. Cria se por exemplo uma div com imagens
```
.container {
    display: flex;  //ativa o flexbox
    flex-wrap: wrap;  //adpta se ao ecra
    
    // alinhar os itens ao centro
    align-items: center;
    
    //ira centar no ecra consoante a largura da tela
    justify-content: center;  
}
```

## Resources
Flexbox:
https://css-tricks.com/snippets/css/a-guide-to-flexbox/

# Butoes
## Propriedades
```
// cor da borda
border-color: #F05F44;

// grossura da borda
border-width: 3px;

// raios da borda
border-radius: 300px;

//transformar texto
text-transform: uppercase;
```
# Linhas
## Propriedades
Apos clicarmos um 'hr'
```
hr {
    border-color: #F05F44;
    border-width: 3px;
    
    //largura maxima
    max-width: 65px;  
}
```

# CSS Grid
The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

![](https://i.imgur.com/xFBc8qr.png)

Criamos um container como o Flexbox com imagens dentro deste por exemplo. No CSS para dizermos que queremos utilizar esta tecnologia:
```
.container {
    
    // dizer ao container que seja grid
    display: grid;
    
    // folga entre os objetos dentro do container
    grid-gap: 10px;
    
    // como sera apresentado por colunas
    grid-template-columns: 1fr;
    
    // repete 3 vezes o 2fr
    grid-template-columns: repeat(3, 2fr);
    
    // ele preenche com o espaco disponivel que existir na tela
    grid-template-columns: auto;
    
    // este comando faz com que o nosso container seja adapativo ao ecra
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
}
```

==Nota:== A melhor medida para o grid é o **fr** fraction dizendo que tem um numero de fractions por coluna

Alterando objetos especificos no container
```
.green {
    // ira ocupar 4 colunas e para as rows é o mesma sintaxe
    grid-column: 1/4;
    
    // ira do inicio ate ao fim do ecra
    grid-column: 1/-1;
    
    // ira ocupar o numero de colunas que desejarmos
    grid-column: span 3;
}
```

## Resources
Site ajuda
http://grid.malven.co/


# Resources
CSS biblioteca, muito util:
https://css-tricks.com/almanac/

Biblioteca de cores:
http://paletton.com/#uid=1000u0kllllaFw0g0qFqFg0w0aF

Transicoes:
https://thoughtbot.com/blog/transitions-and-transforms

Animacoes:
https://daneden.github.io/animate.css/
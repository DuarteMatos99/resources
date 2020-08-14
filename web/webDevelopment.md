**Author:** Duarte Matos

###### tags: `Web`, `Web Development`

# Web Development

![](https://i.imgur.com/YKHqCXt.png)

## History
- How The Internet Works
- History Of The Web
    - WWW vs Internet
    - HTML, CSS, Javascript
    - Developer History


## Google Chrome's Developer Tools
**Elements** tab is for the HTML
**Style** tab is for the CSS
**Console** tab is to enter javascript

## Mailchimp
![](https://i.imgur.com/8g5TOp1.png)

Mailchimp é uma plataforma americana de automação de marketing e um serviço de email marketing.

# HTML 5
## Resources
Extension for HTML 5:
https://hackmd.io/XTo8k3aER6CmM6h8xJYtBg

W3schools:
https://www.w3schools.com/html/

Templates HTML/REACT:
https://cruip.com/

# CSS
## Resources
Extension for CSS:
https://hackmd.io/UzLLYysHQOOBxfSpltTAyQ

CSS biblioteca, muito util:
https://css-tricks.com/almanac/

# Bootstrap
![](https://i.imgur.com/Ub0pMwN.png)
## What is?
Bootstrap is a free and open-source CSS framework directed at responsive, mobile-first front-end web development. It contains CSS- and JavaScript-based design templates for typography, forms, buttons, navigation, and other interface components.

## How to use it?
Podemos fazer o download para o nosso projeto ou podemos chamar os links atraves do bootstrap.

==Nota:== Quando importarmos os links de Js colocamos no final do body para otimizacao do site.

## Utilities
### Text
Podemos alterar o nosso texto via Bootstrap utilizando classes.
```
<h1 class="text-uppercase">Texto</h1>
```

## Layout
### Containers
Containers are the most basic layout element in Bootstrap and are required when using our default grid system.

Vamos utilizar o flexbox(**d-flex** no bootstrap) para centrarmos o nosso container no centro da tela. Os parametros necessarios sao **align-items-center** e **h-100**. O **h-100** diz ao container para usar a altura maxima da pagina.
```
<body>
    <div class="container d-flex align-items-center h-100">
        <div class="row">
        
            // centramos o titulo e que use toda a coluna
            <header class="text-center col-12">>
                <h1 class="text-uppercase">The biggest startup event of the year</h1>
            </header>
            
            // criamos um espaco vazio utilizando o buffer
            <section class="buffer col-12"></section>
            <section class="text-center col-12">
                <hr>
                <button class="btn btn-primary btn-xl">Find out more</button>
            </section>
        </div>
    </div>
</body>
```

## Resources
Free resources that you can use to build your own website here(including Logo Makers):
https://zerotomastery.io/resources/

Templates:
https://mdbootstrap.com/freebies/
http://www.mashup-template.com/templates.html
https://www.creative-tim.com/bootstrap-themes/ui-kit?direction=asc&sort=price
https://startbootstrap.com/templates/

# JavaScript
## Resources
Extension for Js:
https://hackmd.io/zD3DaJNjTsiu0kfPnyBSBw


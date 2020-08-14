**Author:** Duarte Matos

###### tags: `Web`, `React`

# React

![](https://i.imgur.com/BHxq7C7.png)

## What is?
React is a popular library used to create user interfaces. It was built at Facebook to address some of the challenges associated with large-scale, data-driven websites.
When React was released in 2013, the project was initially viewed with some skepticism because the conventions of React are quite unique.

## Page Setup
In order to work with React in the browser, we need to include two libraries: React and ReactDOM. React is the library for creating views. ReactDOM is the library used to actually render the UI in the browser.
```
Example 4-1. HTML document setup with React
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Pure React Samples</title>
</head>
<body>
<!-- Target container -->
<div class="react-container"></div>
<!-- React library & ReactDOM-->
<script src="https://unpkg.com/react@15.4.2/dist/react.js"></script>
<script src="https://unpkg.com/react-dom@15.4.2/dist/react-dom.js"></script>
<script>
// Pure React and JavaScript code
</script>
</body>
</html>
```
These are the minimum requirements for working with React in the browser. You can place your JavaScript in a separate file, but it must be loaded somewhere in the page after React has been loaded.

## The Virtual DOM
HTML is simply a set of instructions that a browser follows when constructing the document object model, or DOM. The elements that make up an HTML document become DOM elements when the browser loads HTML and renders the user interface.

Let’s say that you have to construct an HTML hierarchy for a recipe. A possible solution for such a task might look something like this:
```
<section id="baked-salmon">
<h1>Baked Salmon</h1>
<ul class="ingredients">
<li>1 lb Salmon</li>
<li>1 cup Pine Nuts</li>
<li>2 cups Butter Lettuce</li>
<li>1 Yellow Squash</li>
<li>1/2 cup Olive Oil</li>
<li>3 cloves of Garlic</li>
</ul>
<section class="instructions">
<h2>Cooking Instructions</h2>
<p>Preheat the oven to 350 degrees.</p>
<p>Spread the olive oil around a glass baking dish.</p>
<p>Add the salmon, garlic, and pine nuts to the dish.</p>
<p>Bake for 15 minutes.</p>
<p>Add the yellow squash and put back in the oven for 30 mins.</p>
<p>Remove from oven and let cool for 15 minutes.
Add the lettuce and serve.</p>
</section>
</section>
```
In HTML, elements relate to each other in a hierarchy that resembles a family tree.
We could say that the root element has three children: a heading, an unordered list of ingredients, and a section for the instructions.

The DOM API is a collection of objects that JavaScript can use to interact with the browser to modify the DOM. If you have used document.createElement or
document.appendChild, you have worked with the DOM API. Updating or changing rendered DOM elements in JavaScript is relatively easy. However, the process of inserting new elements is painfully slow. This means if web developers are meticulous about how they make changes to UI, they can improve the performance of their applications.

Managing DOM changes with JavaScript efficiently can become very complicated and time-consuming. From a coding perspective, it is easier to clear all the children of a particular element and reconstruct them than it would be to leave those child elements in place and attempt to efficiently update them. The problem is that we may not have the time or the advanced knowledge of JavaScript to work efficiently with the DOM API every time we build a new application. The solution is React.

React is a library that is designed to update the browser DOM for us. We no longer have to be concerned with the complexities associated with building performant SPAs because React can do that for us. With React, we do not interact with the DOM API directly. Instead, we interact with a virtual DOM, or set of instructions that React will use to construct the UI and interact with the browser.

The virtual DOM is made up of React elements, which conceptually seem similar to HTML elements, but are actually JavaScript objects. It is much faster to work directly with JavaScript objects than it is to work with the DOM API. We make changes to a JavaScript object, the virtual DOM, and React renders those changes for us using the DOM API as efficiently as possible.

## React Elements
The browser DOM is made up of DOM elements. Similarly, the React DOM is made up of React elements. DOM elements and React elements may look the same, but they are actually quite different. A React element is a description of what the actual DOM element should look like. In other words, ==React elements are the instructions for how the browser DOM should be created==.

We can create a React element to represent an h1 using React.createElement:
```
React.createElement("h1", null, "Baked Salmon")
```
The first argument defines the type of element that we wish to create. In this case, we want to create a heading-one element. The third argument represents the element’s children, any nodes that are inserted between the opening and closing tag. The second argument represents the element’s properties. This h1 currently does not have any properties.

During rendering, React will convert this element to an actual DOM element:
```
<h1>Baked Salmon</h1>
```
When an element has attributes, they can be described with properties. Here is a sample of an HTML h1 tag that has id and data-type attributes:
```
React.createElement("h1",
        {id: "recipe-0", 'data-type': "title"},
        "Baked Salmon")
        
<h1 data-reactroot id="recipe-0" data-type="title">Baked Salmon</h1>
```
The properties are similarly applied to the new DOM element: the properties are added to the tag as attributes, and the child text is added as text within the element.
You’ll also notice data-reactroot, which identifies that this is the root element of your React component.

![](https://i.imgur.com/zhvhjfq.png)

So, a React element is just a JavaScript literal that tells React how to construct the     DOM element. Example 4-2 shows the element that createElement call actually creates.
```
Example 4-2. Logging the title element

{
$$typeof: Symbol(React.element),
"type": "h1",
"key": null,
"ref": null,
"props": {"children": "Baked Salmon"},
"_owner": null,
"_store": {}
}
```
This is a React element. There are fields that are used by React: **_owner, _store, $$typeof**. The key and ref fields are important to React elements, but we’ll introduce those later, in Chapter 5. For now, let’s take a closer look at the type and props fields in Example 4-2.
The **type** property of the React element tells React what type of HTML or SVG element to create. ==The **props** property represents the data and child elements required to construct a DOM element==. The children property is for displaying other nested elements as text.

![](https://i.imgur.com/ju0ZusZ.png)

## ReactDOM
**ReactDOM** ==contains the tools necessary to render React elements in the browser==.
**ReactDOM** is where we will find the render method as well as the *renderToString* and *renderToStaticMarkup* methods that are used on the server. These will be discussed in greater detail in Chapter 12. All the tools necessary to generate HTML from the virtual DOM are found in this library.

We can render a React element, including its children, to the DOM with
*ReactDOM.render*. The element that we wish to render is passed as the first argument
and the second argument is the target node, where we should render the element:
```
var dish = React.createElement("h1", null, "Baked Salmon")

ReactDOM.render(dish, document.getElementById('react-
container'))
```
Rendering the title element to the DOM would add a heading-one element to the div with the id of react-container, which we would already have defined in our HTML.
In Example 4-3, we build this div inside the body tag.
```
<body>
    <div id="react-container">
        <h1>Baked Salmon</h1>
    </div>
</body>
```
All of the DOM rendering functionality in React has been moved to ReactDOM because we can use React to build native applications as well. The browser is just one target for React.
That’s all you need to do. You create an element, and then you render it to the DOM.
In the next section, we’ll get an understanding of how to use **props.children**.

## Children
ReactDOM allows you to render a single element to the DOM. React tags this as data-reactroot. All other React elements are composed into a single element using
nesting.
React renders child elements using **props.children**. In the previous section, we rendered a text element as a child of the h1 element, and thus props.children was set to "Baked Salmon". We could render other React elements as children too, creating a tree of elements. This is why we use the term component tree. The tree has one root component from which many branches grow.
Let’s consider the unordered list that contains ingredients in Example 4-4.
```
Example 4-4. Ingredients list

<ul>
    <li>1 lb Salmon</li>
    <li>1 cup Pine Nuts</li>
    <li>2 cups Butter Lettuce</li>
    <li>1 Yellow Squash</li>
    <li>1/2 cup Olive Oil</li>
    <li>3 cloves of Garlic</li>
</ul>
```
In this sample, the unordered list is the root element, and it has six children. We can represent this ul and its children with React.createElement (Example 4-5).
```
Example 4-5. Unordered list as React elements

React.createElement(
    "ul",
    null,
    React.createElement("li", null, "1 lb Salmon"),
    React.createElement("li", null, "1 cup Pine Nuts"),
    React.createElement("li", null, "2 cups Butter Lettuce"),
    React.createElement("li", null, "1 Yellow Squash"),
    React.createElement("li", null, "1/2 cup Olive Oil"),
    React.createElement("li", null, "3 cloves of Garlic")
)
```
Every additional argument sent to the createElement function is another child element.
React creates an array of these child elements and sets the value of props.children to that array.
If we were to inspect the resulting React element, we would see each list item represented by a React element and added to an array called props.children. Let’s do that now (Example 4-6).
```
{
"type": "ul",
"props": {
"children": [
    { "type": "li", "props": { "children": "1 lb Salmon" } … },
    { "type": "li", "props": { "children": "1 cup Pine Nuts"} … },
    { "type": "li", "props": { "children": "2 cups Butter Lettuce" } … },
    { "type": "li", "props": { "children": "1 Yellow Squash"} … },
    { "type": "li", "props": { "children": "1/2 cup Olive Oil"} … },
    { "type": "li", "props": { "children": "3 cloves of Garlic"} … }
]
...
}
}
```
We can now see that each list item is a child. Earlier in this chapter, we introduced HTML for an entire recipe rooted in a section element. To create this using React,
we’ll use a series of createElement calls, as in Example 4-7.
```
Example 4-7. React Element tree

React.createElement("section", {id: "baked-salmon"},
    React.createElement("h1", null, "Baked Salmon"),
    React.createElement("ul", {"className": "ingredients"},
        React.createElement("li", null, "1 lb Salmon"),
        React.createElement("li", null, "1 cup Pine Nuts"),
        React.createElement("li", null, "2 cups Butter Lettuce"),
        React.createElement("li", null, "1 Yellow Squash"),
        React.createElement("li", null, "1/2 cup Olive Oil"),
        React.createElement("li", null, "3 cloves of Garlic")
    ),
    React.createElement("section", {"className": "instructions"},
        React.createElement("h2", null, "Cooking Instructions"),
        React.createElement("p", null, "Preheat the oven to 350 degrees."),
        React.createElement("p", null,
"Spread the olive oil around a glass baking dish."),
        React.createElement("p", null, "Add the salmon, garlic, and pine..."),
        React.createElement("p", null, "Bake for 15 minutes."),
        React.createElement("p", null, "Add the yellow squash and put..."),
        React.createElement("p", null, "Remove from oven and let cool for 15 ....")
    )
)
```

![](https://i.imgur.com/SSxH74x.png)

==This sample is what pure React looks like. Pure React is ultimately what runs in the browser. The virtual DOM is a tree of React elements all stemming from a single root element. React elements are the instructions that React will use to build a UI in the browser.==

## Constructing Elements with Data
The major advantage of using React is its ability to separate data from UI elements.
Since React is just JavaScript, we can add JavaScript logic to help us build the React component tree. For example, ingredients can be stored in an array, and we can map that array to the React elements.
Let’s go back and think about the unordered list in Example 4-8 for a moment.
```
Example 4-8. Unordered list

React.createElement("ul", {"className": "ingredients"},
    React.createElement("li", null, "1 lb Salmon"),
    React.createElement("li", null, "1 cup Pine Nuts"),
    React.createElement("li", null, "2 cups Butter Lettuce"),
    React.createElement("li", null, "1 Yellow Squash"),
    React.createElement("li", null, "1/2 cup Olive Oil"),
    React.createElement("li", null, "3 cloves of Garlic")
);
```
The data used in this list of ingredients can be easily represented using a JavaScript array (Example 4-9).
```
Example 4-9. items array
var items = [
"1 lb Salmon",
"1 cup Pine Nuts",
"2 cups Butter Lettuce",
"1 Yellow Squash",
"1/2 cup Olive Oil",
"3 cloves of Garlic"
]
```
We could construct a virtual DOM around this data using the Array.map function, as in Example 4-10.
```
Example 4-10. Mapping an array to li elements

React.createElement(
    "ul",
    { className: "ingredients" },
    items.map(ingredient =>
        React.createElement("li", null, ingredient)
)
```
This syntax creates a React element for each ingredient in the array. Each string is displayed in the list item’s children as text. The value for each ingredient is displayed as the list item.
When running this code, you’ll see a console error, as shown in Figure 4-2.

![](https://i.imgur.com/BEsmwqq.png)

When we build a list of child elements by iterating through an array, React likes each of those elements to have a key property. The key property is used by React to help it update the DOM efficiently. We will be discussing keys and why we need them in Chapter 5, but for now you can make this warning go away by adding a unique key property to each of the list item elements (Example 4-11). We can use the array index for each ingredient as that unique value.
```
Example 4-11. Adding a key property

React.createElement("ul", {className: "ingredients"},
    items.map((ingredient, i) =>
        React.createElement("li", { key: i }, ingredient)
)
```

## React Components
Every user interface is made up of parts. The recipe example we’ll use here has a few recipes, each made up of parts.

![](https://i.imgur.com/mx3ZSLR.png)

In React, we describe each of these parts as a component. Components allow us to reuse the same DOM structure for different recipes or different sets of data.
When considering a user interface that you want to build with React, look for opportunities to break down your elements into reusable pieces. For example, the recipes in Figure each have a title, ingredients list, and instructions. All are part of a larger recipe or app component. We could create a component for each of the highlighted parts: ingredients, instructions, and so on.

![](https://i.imgur.com/PdBQIOt.png)

Think about how scalable this is. If we want to display one recipe, our component structure will support this. If we want to display 10,000 recipes, we’ll just create new instances of that component.
Let’s investigate the three different ways to create components: createClass, ES6 classes, and stateless functional components.

## Classes and Functions

==A class component must include render(), and the return can only return one parent element.==

**Simple Component**
```
const SimpleComponent = () => {
  return <div>Example</div>
}
```
**Class Component**
```
class ClassComponent extends Component {
  render() {
    return <div>Example</div>
  }
}
```

## Props
One of the big deals about React is how it handles data, and it does so with properties, referred to as props, and with state. Now, we'll focus on handling data with props.

## State
You can think of state as any data that should be saved and modified without necessarily being added to a database - for example, adding and removing items from a shopping cart before confirming your purchase.

```
import React, { Component } from 'react'
import api from '../../services/api'

class Main extends Component {
    
    // new - 
    state = {
        products: [],
    }
    
    componentDidMount() {
        this.loadProducts()
    }

    loadProducts = async () => {
        const response = await api.get('/products')
        
        // new - 
        this.setState({products: response.data.docs})
    }

    render() {
        return (
            // new - 
            <div className="product-list">
                {this.state.products.map((product, index) => (
                    <h2 key={index}>{product.title}</h2>
                ))}
            </div>
        )
    }
} 

export default Main
```

# JSX: JavaScript + XML
JSX is actually closer to JavaScript, not HTML, so there are a few key differences to note when writing it.

- **className** is used instead of **class** for adding CSS classes, as class is a reserved keyword in JavaScript.
- **Properties** and **methods** in JSX are **camelCase** - ==onclick== will become ==onClick==.
- Self-closing tags must end in a slash - e.g. <img />

JavaScript expressions can also be embedded inside JSX using curly braces, including variables, functions, and properties.

# API's
## Axios
Para acessar aos dados de ma API utilizamos AXIOS 
```
import axios from 'axios'

const api = axios.create({
    baseURL:'https://rocketseat-node.herokuapp.com/api'
})

export default api
```

## Conceitos Importantes 
### async/await
The ==async== before a function means one simple thing: a function always returns a promise.

The ==await== makes JavaScript wait until that promise settles and returns its result.

### componentDidMount
The ==componentDidMount()== method is called after the component is rendered.

This is where you run statements that requires that the component is already placed in the DOM.

# New Project

## Install React
````
npm install -g create-react-app
````

## Create an App
==Note:== robofriends is the name of the app
````
create-react-app robofriends
````

## Start a Server
````
npm start
````

## Update the Version of React
1. We update the **react-script** on ==package.json==.
2. **npm install** on terminal
3. **npm start** on terminal

## React imports
**react** - Is the core package that does the DOM manipulation for us
**react-dom** - Is used for DOM web sites
**tachyons** - CSS Toolkit
**axios** - Para acessar aos dados de ma API utilizamos AXIOS 

# RoboFriends
## index.js
```
version 0

import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import Card from './Card';
import * as serviceWorker from './serviceWorker';
import 'tachyons';

// neste import chamamos uma lista(robots) por isso utilizamos {robots}
import {robots} from './robots'

ReactDOM.render(
  <React.StrictMode>
    
    // Colocamos o elemento Card e seus props
    <Card id={robots[0].id} name={robots[0].name} email={robots[0].email} />
  </React.StrictMode>,
  document.getElementById('root')
);
```

```
v 1

import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import * as serviceWorker from './serviceWorker';
import 'tachyons';
import {robots} from './robots'
import CardList from './CardList'

ReactDOM.render(
  <React.StrictMode>
    <CardList robots={robots}/>
  </React.StrictMode>,
  document.getElementById('root')
);

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();
```

## Card.js
Existem varias maneiras de utilizar os props do Card
1. Forma
```
import React from 'react'

const Card = (props) => {
    return (
        <div className="tc bg-light-green dib br3 pa3 ma2 grow bw2 shadow-5">
            
            // como queremos utilizar o parametro id fazemos da seguinte maneira
            <img alt="photo" src={`https://robohash.org/${props.id}?200x200`}></img>
            <div>
                <h2>{props.name}</h2>
                <p>{props.email}</p>
            </div>
        </div>
    )
}

export default Card
```

2. Forma
```
import React from 'react'

const Card = ({id, name, email}) => {
    return (
        <div className="tc bg-light-green dib br3 pa3 ma2 grow bw2 shadow-5">
            <img alt="photo" src={`https://robohash.org/${id}?200x200`}></img>
            <div>
                <h2>{name}</h2>
                <p>{email}</p>
            </div>
        </div>
    )
}

export default Card
```

3. Forma
```
import React from 'react'

const Card = (props) => {
    const {id, name, email} = props
    return (
        <div className="tc bg-light-green dib br3 pa3 ma2 grow bw2 shadow-5">
            <img alt="photo" src={`https://robohash.org/${props.id}?200x200`}></img>
            <div>
                <h2>{props.name}</h2>
                <p>{props.email}</p>
            </div>
        </div>
    )
}

export default Card
```

## CardList
1. Forma
```
import React from 'react'
import Card from './Card'

const CardList = ({ robots }) => {
    
    // A keyword map significa um loop
    const cardList = robots.map((user, i) => {
        return (
        <Card 
        
        // Each child in a list should have a unique "key" prop
        key={i} 
        id={robots[i].id} 
        name={robots[i].name} 
        email={robots[i].email} 
        />
        )
    })
    return (
        <div>
            {cardList}
        </div>
    )
}

export default CardList
```

2. Forma
```
import React from 'react'
import Card from './Card'

const CardList = ({ robots }) => {
    return (
        <div>
            {
            robots.map((user, i) => {
                return (
                    <Card 
                    key={i} 
                    id={robots[i].id} 
                    name={robots[i].name} 
                    email={robots[i].email} 
                    />
                )
            })
            }
        </div>
    )
}

export default CardList
```
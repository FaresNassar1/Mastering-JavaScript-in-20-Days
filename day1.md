# JavaScript 1# Day Training
---
Note: Download the file for a better view

Welcome to the first day of JavaScript training! In this training session, we will introduce you to the fundamentals of JavaScript, a popular programming language used for web development. This README file will provide you with an overview of what will be covered during the training and some essential information to get started.

## Table of Contents
- [JavaScript!What? Why? How?](#what-is-javascript)
- [Document Object Model](#dom)
- [Values & Data Types](#values-datatypes)

## What is JavaScript?
javaScript is a high-level programming language that is primarily used for developing dynamic and interactive web content. It allows you to add functionality and interactivity to websites, making them more engaging for users. JavaScript can be used to create features such as form validation, interactive maps, sliders, animations, and much more.
##why?
JavaScript is widely adopted and supported by all modern web browsers, making it an essential language for web development. It is the standard client-side scripting language for web browsers and provides the ability to create dynamic web pages that can respond to user actions in real-time. Additionally, JavaScript can also be used on the server-side (Node.js) to build scalable and efficient web applications.

**HTML versus CSS versus Javascript** :
Together, HTML, CSS, and JavaScript form the foundation for building modern, responsive, and interactive websites. HTML provides the structure, CSS defines the visual presentation, and JavaScript adds the necessary interaction and dynamic behavior.

---

## DOM
In JavaScript, the DOM (Document Object Model) is an interface that allows you to interact with and manipulate the content of a web page dynamically. It provides methods to access elements, modify content, change styles, handle events, and create or modify elements in a hierarchical structure.
When a web page is loaded in a browser, the browser creates a DOM representation of the page. The DOM consists of various objects, where each object represents an element in the document, such as a paragraph, heading, image, or form. These objects are organized in a hierarchical structure, with the document object at the top and child objects representing nested elements.

## Reading the DOM with JS
**document.title**--->the page (document) title
**document.body**--->the body element
**document.body.children**-->all the elements within the body
**document.getElementById("board") OR document.querySelector("#board")**-->the (first) element with id="board"
**document.getElementsByTagName("h1") OR document.querySelectorAll("h1")**--->all the h1 elements
**document.getElementsByClassName("player") OR document.querySelectorAll(".player")**--->all the elements with class="player"
**document.getElementsByClassName("player").length OR document.querySelectorAll(".player").length**--->the number of elements with class="player"
**document.getElementById("p1-name").textContent**--->the text inside the element with id="p1-name"

####==MDN(https://developer.mozilla.org/)==

#[Tic Tac Toe web site](https://anjana.dev/javascript-first-steps/1-tictactoe.html)
![alt text](./ex1.png)   
 Exercise
Type commands in the console to retrieve:
- all the p elements
- the text "X"
- the number of squares in the board
- the text "A game you know"
#### 1. `document.getElementsByTagName("p") OR document.querySelectorAll("p")`
#### 2. `document.getElementById("p1-symbol").textContent OR document.querySelector("#p1-symbol").textContent`
#### 3. `document.querySelectorAll(".square").length    `
#### 4. `document.querySelector("h2").textContent`
---
####DOM Editing
==EXAMPLE==
change page title
`document.title="My page"`

replace the text of the #p1-name element
`document.getElementById("p1-name").textContent = "fares"
`
add to the end of the element's current text
`document.getElementById("p1-name").append(" & friends")`


## Values-DataTypes
####==44 != "44"==
####==typeof==:
#####tells you the type of a value
EX: `typeof "44"`=>string
EX: `typeof 44`=>number
###Data
- Primitive types 
str,num,boo.... + undefined,null
==undefined != null==
==typeof true != typeof "true"==
`typeof "some string".length`==>Number
`typeof null`=>==object==
- What are strings made of?
==characters==.
`"myname is fares nassar".length`==>22 char ==with space==.
`"fares nassar"[1]`= =>a
`"nassar".indexOf("r")`= =>5
if ("g") not found ==> ==-1==
==includes, startswith===> to check = ==>boolean.==
####Connecting strings together
`"fares "+"nassar"`==>"fares nassar"

---
Exercise
Use our new string superpowers to:

Add your last name in the players listing
Retrieve the first "T" in the page title
Answer whether the page title contains the string "JavaScript"
Capitalize the heading "Tic Tac Toe"

**solutions**
1. `document.getElementById("p1-name").append("nassar")`
- we can use this to editing `document.querySelector("#p1-name").textContent ="Fares" + " Rafat"+" Nassar"`

2. `document.title.indexOf("T")==>9 then document.title[9]==>"T" `
3. `document.title.includes("JavaScript")`==>false ==case sensitive== 
4. `document.querySelector("header h1").style.textTransform="uppercase"
document.querySelector("header h1").textContent.toUppercase() `

---
## Coding Exercises


### [Compound Assignment With Augmented Multiplication](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)
```javascript
let a = 5;
let b = 12;
let c = 4.6;
a *= 5;
b *= 3 ;
c *= 10;
```

### [Concatenating Strings with the Plus Equals Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)

```javascript
let myStr="This is the first sentence.";
myStr +=" This is the second sentence.";

```
### [Use Bracket Notation to Find the First Character in a String](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-bracket-notation-to-find-the-first-character-in-a-string)

```javascript
let firstLetterOfLastName = "";
const lastName = "Lovelace";
firstLetterOfLastName = lastName[0];

```





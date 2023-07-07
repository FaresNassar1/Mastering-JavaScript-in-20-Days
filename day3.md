# 3# Day Training Js
---

### Table of Contents
- [Object](#object)
- [Quiz Project](#quiz-project)
- [Quiz Project Functions](#function)

---
##Object

Objects collect multiple values together to describe more complex data


**note** `typeof ["fares"]`=>object
`typeof{snack:"chips"}`=>object

`const fares= {
name:"Fares",
home:"Hebron",
languages:["English","Arabic"],
pet:null,
vehicle:"vespa",
hobbies:["travel","climbing","gaming","lindy hop"]
};`

objects let us point at related values using properties in the object.

`info={name:"fares"};`

`info.speak = function () {
    console.log("Hi my name is", this.name);
}
info.speak();`
 
**output: Hi my name is fares**
- [x] Nested objects

``` js
const menu = {
    lunch: {
        appetizer: "salad",
        main: "spaghetti",
        dessert: "tiramisu"
    },
    dinner: {
        appetizer: "samosa",
        main: "saag paneer",
        dessert: "gulab jamun"
    }
};
```

```js
const tiramisu = menu.lunch.dessert;
```

- [x] Objects in Arrays & Objects
```js 
const spices = [
    {name: "Emma", nickname: "Baby"},
    {name: "Geri", nickname: "Ginger"},
    {name: "Mel B", nickname: "Scary"},
    {name: "Mel C", nickname: "Sporty"},
    {name: "Victoria", nickname: "Posh"}
];
const spiceGirls = {
    albums: ["Spice", "Spiceworld", "Forever"],
    motto: "Girl Power",
    members: spices
};
```
**hint**
```
.warn,.error
```
**Math**
```
Math.random();
Math.PI;
Math.abs(-5);

```

---
##Quiz Project

#### [Part one (Quiz.js)](https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html)


```javascript
 
<script type="text/javascript">
      // TODO 1: Declare & assign variables pointing to the corresponding element(s)
      // statement should be the "statement" div
      const statement = document.getElementById("statement");
      // optionButtons should be all the elements within the "options" div
      // ####const optionButtons = document.querySelectorAll("button")
      const optionButtons = document.querySelector("#options").children;
      // explanation should be the "explanation" div[]
      const explanation = document.getElementById("explanation");
      // TODO 2: Declare & assign a variable called fact
      // Its value should be an object with a statement, true/false answer, and explanation
      const fact = {
        statement: "Arrays are like objects",
        answer: true,
        explanation: "Arrays are a kind of object ",
      };
      // TODO 3: Set the text of the statement element to the fact's statement
      statement.textContent = fact.statement;

```
---

###Function
Parameters & Arguments
```javascript
function add(x, y) {
    return x + y;
}
add(2,3);

//note
function sum(x){
console.log(x+x);
return x+x
} 
const sumx=sum(3);
//sumx without return give undefine
//with give ==>9

```
###Arrow functions

```javascript
function square(x) {
    return x*x;
}
//vs

const square = (x) => x*x; 
```
###Scope

Scopes are nested within the program
The widest scope is the global scope
Each function gets its own new scope within the scope where it was declared
```javascript
let planet = "Jupiter";
function scopeOut() {
    let planet = "Mars";
    console.log("Inner planet:", planet);
}
scopeOut();//===>Mars
console.log("Outer planet:", planet);//==>Jupiter
```
- [x] Let vs const vs var

#### [Part 2 (Quiz.js)](https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html)


```javascript
 // TODO 4: Declare disable & enable functions to set or remove the "disabled" attribute from a given button element
      // disable(button) should set the button element's attribute "disabled" to the value ""
      const disable = (button) => button.setAttribute("disabled", "");

      // enable(button) should remove the attribute "disabled" from the button element
      const enable = (button) => button.removeAttribute("disabled");
      // TODO 5: Declare an isCorrect function that compares a guess to the right answer
      // isCorrect(guess) should return true if the guess matches the fact's answer
      function isCorrect(guessString) {
        return guessString === fact.answer.toString();
```

---

## Coding Exercises

### [Return a Value from a Function with Return](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return)

#### My Solution


```javascript

function timesFive(num){
return num*5
}
timesFive(6);
```
---

### [Global Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions)

#### My Solution


```javascript

let myGlobal=10;

function fun1() {
oopsGlobal=5
}

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
```
---
### [Local Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)

#### My Solution


```javascript
function myLocalScope() {
 let myVar;

  console.log('inside myLocalScope', myVar);
}
myLocalScope();
console.log('outside myLocalScope', myVar);
```
---
### [Global vs. Local Scope in Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-vs--local-scope-in-functions)

#### My Solution


```javascript
let outerWear = "T-Shirt";

function myOutfit() {
  let outerWear = "sweater";
  return outerWear;
}
myOutfit();
```
---
### [Stand in Line](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)

#### My Solution


```javascript
function nextInLine(arr, item) {
  // Only change code below this line
  arr.push(item)
const removed=  arr.shift();
  return removed;
 // Only change code above this line
}
// Setup
let testArr = [1, 2, 3, 4, 5];
// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```
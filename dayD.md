## JavaScript DEEP JS FOUNDATIONS

# 3-4# Day Training

---

### Table of Contents

- [Advanced Scope](#)
- [Closure](#)

---

## Advanced Scope

### explicit let block
#### The "explicit let block" in JavaScript allows you to define variables with the "let" keyword within a specific block scope. It restricts the variable's accessibility to only that block and any nested blocks inside it, improving code organization and preventing conflicts with variables in other parts of the code.

```javascript
let x = 1;
if (x === 1) {
  let x = 2;
  console.log(x);
  // Expected output: 2
}
console.log(x);
// Expected output: 1

```

### Block Scoping: const(antly confusing)
```javascript
** their values cannot be reassigned**
function exampleFunction() {
  const pi = 3.14; 
  if (true) {
    const pi = 3.14159; 
    console.log(pi); //3.14159
  }
  console.log(pi);//3.14
}

exampleFunction();

```

### Hosting
 "hoisting" in JavaScript refers to a behavior during the code execution phase where variable and function declarations are moved (hoisted) to the top of their respective scope, whether it's inside a function or a script file. This means that we can use variables and call functions before they are actually defined in the code.

Let's understand this with a more illustrative example:
```javascript
console.log(x); // This will print "undefined"
var x = 5;

hello(); // This will call the function "hello"
function hello() {
  console.log("Hello, world!");
}

```
**In JavaScript, variable assignments are part of the execution phase, not the compilation phase**

---

# TDZ
The "Temporal Dead Zone" (TDZ) in JavaScript refers to a temporary period before variables declared with "let" and "const" are initialized. During this time, accessing the variables will result in a "ReferenceError." The TDZ starts when the scope begins and ends when the variable is defined. It promotes safer code by preventing access to variables before they are defined, helping catch errors and enforcing better coding practices. Always make sure to define variables before using them in your code.

---

## Closure

Closure is when a function “remembers” its
lexical scope even when the function is
executed outside that lexical scope.

```javascript
function init() {
  var name = "Mozilla"; // name is a local variable created by init
  function displayName() {
    // displayName() is the inner function, that forms the closure
    console.log(name); // use variable declared in the parent function
  }
  displayName();
}
init();

```

## Closure: NOT capturing a value

- [x] Closure: loops

## Modules

* Namespace, NOT a module
* Modules encapsulate data and behavior
(methods) together. The state (data) of a
module is held by its methods via closure.

## [Tasks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day4-tasks/tasks.md)

### Question 1:

### My Solution
```javascript 

for (let i = 0; i < 5; i++) {
  setTimeout(function() {
    console.log("value of [i] is: ", i);
  }, 100);
}
////Without changing anything in the for loop's code itself, provide a solution to fix it.
for (var i = 0; i < 5; i++) {
  setTimeout(() => {
    console.log("value of [i] is: ", i);
  }, 100);
}

```
### Question 2:

```javascript

let array = [];
for (let i = 0; i < 5; i++) {
   array.push(i);
}
console.log("Current array is: ", array);

```
### Question 3:

```javascript
let functions = [];

for (var i = 0; i < 5; i++) {
  (function(i) {
    functions.push(() => {
      console.log("Current value of i is:", i);
    });
  })(i);
}

functions.forEach((func) => func());


```
## CLOSURE:
### QUESTION #1
```javascript
function privateCounter() {
  let count = 0; 
  function increment() {
    count++;
  }

  function getCount() {
    return count;
  }

  return {
    increment: increment,
    getCount: getCount
  };
}
const counter = privateCounter();
counter.increment();
counter.increment();
counter.increment();

console.log(counter.getCount());


```
### QUESTION #2
```javascript
function generateFibonacci(count) {
  let currentCount = 0;
  let prevNumber = 0;
  let currentNumber = 1;
  function fibonacci() {
    if (currentCount >= count) {
      return null; 
    }
    currentCount++;
    let nextNumber = prevNumber + currentNumber;
    prevNumber = currentNumber;
    currentNumber = nextNumber;
    return prevNumber;
  }
  return fibonacci;
}
const fibonacciClosure = generateFibonacci(10);
for (let i = 0; i < 10; i++) {
  console.log(fibonacciClosure());
}


```

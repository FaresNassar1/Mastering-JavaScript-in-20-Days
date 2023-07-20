## JavaScript DEEP JS FOUNDATIONS

# 4-3# Day Training

---

### Table of Contents

- [Scope & Function Expressions](#)
- [Advanced Scope ](#)

---
## Scope & Function Expressions

* ### Named Function Expressions
**Benefits**:
  
1. Reliable function self-reference (recursion, etc)
2. More debuggable stack traces
3. More self-documenting code
   
 EX:  `var key =function key(){};`

* ### Anonymous Arrow Functions
  `var key=()=>{};`
  #### (Named) Function Declaration > Named Function Expression > Anonymous Function Expression

- [x] lexical scope
- [x] dynamic scope

---

In dynamic scope, the scope of a variable is determined based on the calling sequence of functions during runtime rather than the program's source code structure. This means that when a variable is referenced, the interpreter looks for its value in the function that was most recently called, regardless of where the variable was defined.

Let's illustrate dynamic scoping with a simple example in a fictional programming language:
```javascript 
var x = 10;

function outer_function() {
    var x = 20;
    inner_function();
}

function inner_function() {
    print(x); // Accesses the variable 'x' from the most recent calling function (outer_function)
}

outer_function(); // Output: 20

```

---

- [x] Function Scoping
- [x] Function Scoping: IIFE
- [x] Block Scoping
var function scope
let const block scope
Done....etc

## [Tasks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)

### Question 1:


### My Solution
```javascript

const exampleNormalFunc1 = (a, b, c) => {
  return a * (b + c);
}

const exampleNormalFunc2 = (x, y) => {
  return x * y;
}

const exampleNormalFunc3 = (string) => {
  return string + " " + string + " " + string + "!";
} 


const arrowHOF = (normalFunc) => {
  return (...args) => {
    return (...extraArgs) => {
      const result = normalFunc(...args);
      const times = extraArgs.length === 0 ? 1 : extraArgs[0];
      return Array.from({ length: times }, () => result);
    };
  };
};

const hofNormalFunc1 = arrowHOF(exampleNormalFunc1);
const hofNormalFunc2 = arrowHOF(exampleNormalFunc2);
const hofNormalFunc3 = arrowHOF(exampleNormalFunc3);

console.log(hofNormalFunc1(3, 4, 5)(2)); // logs 60 twice
console.log(hofNormalFunc2(20, 35)(4)); // logs 700 four times
console.log(hofNormalFunc3("Meow")()); // logs "Meow Meow Meow!" once
```

### Question 2:

```javascript
const obj = {
  name: 'John',
  greet: function (greeting) {
    console.log(`${greeting}, ${this.name}!`);
  }
};

const preserveThis = (func) => {
  return (...args) => {
    return func.apply(func, args);
  };
};

// Wrap the greet function using preserveThis
const preservedGreet = preserveThis(obj.greet);

// Call the wrapped function as a method of the object
preservedGreet('Hello'); // Output: "Hello, John!"


```

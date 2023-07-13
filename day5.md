## JavaScript the Hard Parts

# 2-1# Day Training

### Table of Contents

- [Introduction](#)
- [JavaScript Principles](#javaScript-principles)
- [Functions & Callbacks](#)


---
## Introduction

- Analytical problem
  solving
- Engineering
  approach
- JavaScript and programming
  experience
- Non-technical
  communication
- Technical
  communication

---

JavaScript Principles

- thread of execution :Goes through the code
  line-by-line and runs/ ’executes’ each line

- Saves ‘data’ like strings and
  arrays so we can use that data
  later - in its memory
  **We can even save code
  (‘functions’)**

* [x] **Execution context**
      Created to run the code of a
      function - has 2 parts (we’ve
      already seen them!)
* Thread of execution
* Memory

* [x] **Call stack**
* JavaScript keeps track of what
  function is currently running
  (where’s the thread of execution)
* Run a function - add to call stack
* Finish running the function - JS
  removes it from call stack
* Whatever is top of the call stack
* that’s the function we’re
  currently running

## Functions & Callbacks

- Enables powerful pro-level functions like map, filter, reduce (a core aspect of
  functional programming)
- Makes our code more declarative and readable
- Forms the backbone of the Codesmith technical interview

---

- [x] **Generalizing functions**

#### Pair programming

- **The most effective way to grow as a software engineer**

- Tackle blocks with a partner
- Stay focused on the problem
- Refine technical communication
- Collaborate to solve problem

---

**example** Callback function

```javascript
function copyArrayAndManipulate(array, instructions) {
  const output = [];
  for (let i = 0; i < array.length; i++) {
    output.push(instructions(array[i]));
  }
  return output;
}
function multiplyBy2(input) {
  return input * 2;
}
const result = copyArrayAndManipulate([1, 2, 3], multiplyBy2);
```

**Updating our callback function as an arrow function**

```javascript
function copyArrayAndManipulate(array, instructions) {
  const output = [];
  for (let i = 0; i < array.length; i++) {
    output.push(instructions(array[i]));
  }
  return output;
}
const multiplyBy2 = (input) => input * 2;
const result = copyArrayAndManipulate([1, 2, 3], (input) => input * 2);
```

---

## Coding Exercises

### [Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)

#### My Solution

```javascript
const squareList = (arr) => {
  return arr
    .filter((num) => num > 0 && num % parseInt(num) === 0)
    .map((num) => Math.pow(num, 2));
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```

### [Apply Functional Programming to Convert Strings to URL Slugs](freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)

#### My Solution

```javascript

function urlSlug(title) {
return  title.toLowerCase()
    .trim()
    .split(/\s+/)
    .join("-");
}
let x= urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");
console.log(x)
```


### [TASKS](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)

#### My Solution

```javascript


```

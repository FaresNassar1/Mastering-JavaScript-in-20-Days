
# 2-2# Day Training

---
## Closures

- Closure is the most esoteric of JavaScript concepts
- Enables powerful pro-level functions like ‘once’ and ‘memoize’
- Many JavaScript design patterns including the module pattern use closure
- Build iterators, handle partial application and maintain state in an
asynchronous world
---

* ####  Functions get a new memory every run/invocation

```javascript
function multiplyBy2 (inputNumber){
const result = inputNumber*2;
return result;
}
const output = multiplyBy2(7);
const newOutput = multiplyBy2(10);

```
---
* #### Functions can be returned from other functions in JavaScript

```javascript
function createFunction() {
 function multiplyBy2 (num){
 return num*2;
 }
 return multiplyBy2;
}
const generatedFunc = createFunction();
const result = generatedFunc(3); //6

```
---
* #### Calling a function in the same function call as it was
defined
```javascript

function outer (){
 let counter = 0;
 function incrementCounter (){
 counter ++;
 }
 incrementCounter();
}
outer();
```
---
 * #### Calling a function outside of the function call in which it was defined

```javascript
function outer (){
 let counter = 0;
 function incrementCounter (){ counter ++; }
 return incrementCounter;
}
const myNewFunction = outer();
myNewFunction();
myNewFunction();
``````

#### The bond
When a function is defined, it gets a bond to the surrounding Local Memory
(“Variable Environment”) in which it has been defined

#### The ‘backpack’
- We return incrementCounter’s code (function definition) out of outer into
global and give it a new name - myNewFunction
```javascript
function outer (){
 let counter = 0;
 function incrementCounter (){
 counter ++;
 }
 return incrementCounter;
}
const myNewFunction = outer();
myNewFunction();
myNewFunction();
const anotherFunction = outer();
anotherFunction();
anotherFunction();

```
---

## [Tasks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md)

 ### Question 1:
Write a closure named createCounter that takes an initial value start and returns a function. The returned function, when invoked, should increment the counter by 1 and return the updated value.

```javascript
function createCounter(start) {
  let counter = start;

  return function() {
    counter++;
    return counter;
  };
}
const myCounter = createCounter(9);
console.log(myCounter()); // Output: 10
console.log(myCounter()); // Output: 11

```

---

### Question 2:
Write a closure named calculateAverage that takes an array of numbers, nums, and returns a function. The returned function, when invoked, should calculate and return the average of the numbers in the array.

```javascript
function calculateAverage(nums) 
{

  return function() {
let sum =0;
    for (let index = 0; index < nums.length; index++) {
       sum =sum+ nums[index];
    }
return sum/nums.length
  };
}
const averageFunc = calculateAverage([1,3,8]);
console.log(averageFunc()); // Output: 4

```
### Question 3:
Write a closure named powerOf that takes a base number base and returns a function. The returned function, when invoked with an exponent exp, should calculate and return the result of base raised to the power of exp.

```javascript
function powerOf(base) {
  return function(exp) {
    return Math.pow(base, exp);
  };
}
const baseSquare=powerOf(2)
console.log(baseSquare(3));//8

const baseCube=powerOf(3)
console.log(baseCube(2))//9


```
### Question 4:
Write a closure named compose that takes multiple functions as arguments and returns a new function. The returned function should apply the provided functions in reverse order, passing the result of each function as an argument to the next function.

```javascript
function compose(...functions) {
  return function(arg) {
    let result = arg;
    for (let i = functions.length - 1; i >= 0; i--) {
      result = functions[i](result);
    }
    return result;
  };
}
function addOne(x) {
  return x + 1;
}
function square(x) {
  return x ** 2;
}
function double(x) {
  return x * 2;
}
const composedFunction = compose(double, square, addOne);

const result = composedFunction(3);
console.log(result); 



```

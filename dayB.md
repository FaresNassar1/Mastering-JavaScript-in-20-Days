## JavaScript DEEP JS FOUNDATIONS

# 3-2# Day Training

---

### Table of Contents

- [Static Typing](#)
- [Scope](#)

---

### TypeScript, Flow, and type-aware linting

### Benefits:
1. Catch type-related mistakes
2. Communicate type intent
3. Provide IDE feedback

### Caveats:

1. Inferencing is best-guess, not a
guarantee
2. Annotations are optional
3. Any part of the application that
isn't typed introduces uncertainty

### Example
` var x="fares";`
`x={name:nassar};`
**Error:can't assign object to string**
and the same if 
`var x:string="fares";  x={name:"nassar"};//error ca....`
**note**: can't subtract string 🔨

## Pros
1. They make types more obvious in code
2. Familiarity: they look like other language's type systems
3. Extremely popular these days
## corns 
1. They require* a build process, which raises the barrier to entry
2. Their sophistication can be intimidating to those without prior formal types experience
   etc....

   ---

   ## Scope

* Scope: where to look for things

     **JavaScript organizes scopes with functions and blocks**
  - [x] scope
  - [x] use strict
  - [x] undefined vs undeclared

  ---
  ## [Tasks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)

### Question 1:


### My Solution
```javascript
interface HelloWorldResponse {
  message: string;
}

interface CheckBooleanResponse {
  boolean: boolean;
}

interface ReturnObjResponse {
  x: string;
  y: number;
}

// Define the promises with appropriate types
const sayHelloWorld: Promise<HelloWorldResponse> = new Promise((resolve, reject) => {
  resolve({ message: "Hello world!" });
});

const checkBoolean = (boolean: boolean): Promise<CheckBooleanResponse> => new Promise((resolve, reject) => {
  if (boolean) {
    resolve({ boolean });
  } else {
    reject(`Input is false :(`);
  }
});

const returnObj: Promise<ReturnObjResponse> = new Promise((resolve, reject) => {
  resolve({
    x: "meow",
    y: 45,
  });
});

const promisesArray = [sayHelloWorld, checkBoolean(true), returnObj];

// Define the return type for convertToObj
interface ConvertedObject {
  [key: string]: HelloWorldResponse | CheckBooleanResponse | ReturnObjResponse;
}

const convertToObj = (array: Promise<any>[]): Promise<ConvertedObject> => {
  return Promise.all(array).then((results) => {
    const keys = ['sayHelloWorld', 'checkBoolean', 'returnObj'];
    const obj: ConvertedObject = {};

    results.forEach((result, index) => {
      obj[keys[index]] = result;
    });

    return obj;
  });
};

// Usage
convertToObj(promisesArray).then((result) => {
  console.log(result);
});

```
 ### SCOPE & HOISTING QUESTIONS:
 #### QUESTION #1:

**C) 1, ReferenceError, ReferenceError**.

`a` is declared with var, making it function-scoped. It is accessible throughout the whole function, but its value will be undefined if the if condition is false.
`b` and `c` are declared with let and const, respectively, making them block-scoped. They are only accessible within the if block and cannot be accessed outside of it.

### QUESTION #2:

`A) undefined, b&c ReferenceError`
In the testScope2 function, the variables a, b, and c are accessed before they are declared and initialized. This results in the following behavior:

a is declared using var, so it is hoisted to the top of the function and has an initial value of undefined. The console.log(a) statement logs undefined.
b and c are declared using let and const, respectively, making them block-scoped. They are not hoisted and cannot be accessed before their declarations. The console.log(b) and console.log(c) statements encounter a ReferenceError because b and c are not defined in this scope.

QUESTION #3:

`[36, 100, 45] [1, 2, 3] [1, 100, 45]`


The first console.log() outputs [36, 100, 45], showing the initial values of variables a, b, and c.
The second console.log() inside the if block outputs [1, 2, 3], reflecting the updated values of variables a, b, and c inside the block.
The third console.log() outside the if block outputs [1, 100, 45], showing that the outer variable a was updated by the if block, but the values of b and c remain the same.

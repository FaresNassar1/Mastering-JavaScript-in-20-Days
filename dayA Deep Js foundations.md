
## JavaScript DEEP JS FOUNDATIONS

# 3-1# Day Training

---

### Table of Contents

- [Introduction](#)
- [Types](#)

---

#### **You must read the JavaScript specification** 👨‍⚖️

---

## Types:

### • Primitive Types 

* **"In JavaScript, everything is an object." ===>false**

###  Primitive Types:
• undefined
• string
• number
• boolean
• object
• symbol

### objects
1. function
2. object
3. array

### Not

• undefined • string • number • boolean • object • symbol • null • bigint (future) 


##  **In JavaScript, variables don't have types, values do.**
use `typeof`
 
 ---
 
## undefined vs. undeclared vs. uninitialized (aka TDZ)

####  Undefined: In JavaScript, "undefined" is a primitive data type that represents the absence of a value. When you declare a variable without assigning a value to it, the variable's initial value will be "undefined." For example:
`let x;
console.log(x); // Output: undefined
`
#### Undeclared: An undeclared variable is a variable that has not been declared using the "var," "let," or "const" keywords. Attempting to use an undeclared variable will result in a reference error. For example:
`console.log(y); // Output: ReferenceError: y is not defined
`

#### Uninitialized (Temporal Dead Zone - TDZ):The Temporal Dead Zone (TDZ) is a concept in JavaScript associated with the "let" and "const" declarations. When you declare a variable using "let" or "const," the variable exists in a temporal dead zone from the start of the block until the actual declaration is encountered. Trying to access the variable during this period will result in a ReferenceError. For example:
`console.log(z); // Output: ReferenceError: Cannot access 'z' before initialization
let z = 10;
`
---

## Special Values

**NaN (“not a number”) incorrect** 😂

**NaN: Invalid Number**
`don't: undefined
don't: null
don't: false
don't: -1
don't: 0`

---

## Negative Zero

note **object.is()**

---
## [Tasks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day1-tasks/tasks.md)

### Question 1:


### My Solution

```javascript
function convertStringToNumber(input) {
  if (typeof input === 'string') {
    const number = +input;
    if (!isNaN(number)) {
      return number;
    }
  }

  return { value: input, type: typeof input };
}
```
### Question 2:

```javascript

function checkNaN(value) {
  return isNaN(value);
}

```

### Question 3:

```javascript
function isEmptyValue(input) {
  return input === undefined || input === null || input === '';
}


```

### Question 4:
```javascript

function compareObjects(obj1, obj2) {
  if (typeof obj1 === 'object' && typeof obj2 === 'object' && obj1 !== null && obj2 !== null) {
    const keys1 = Object.keys(obj1);
    const keys2 = Object.keys(obj2);

    if (keys1.length !== keys2.length) {
      return false;
    }

    for (const key of keys1) {
      if (!obj2.hasOwnProperty(key) || obj1[key] !== obj2[key]) {
        return false;
      }
    }

    return true;
  }

  return [obj1, obj2];
}

```

### Question 5:

```javascript

function complexCoercion(input) {
  if (typeof input === 'number') {
    return Boolean(input.toString());
  } else if (typeof input === 'string') {
    return Boolean(input);
  } else if (input === null || input === undefined) {
    return false;
  } else {
    return input;
  }
}

```

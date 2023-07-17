
## JavaScript DEEP JS FOUNDATIONS

# 4-1# Day Training

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

###  Undefined: In JavaScript, "undefined" is a primitive data type that represents the absence of a value. When you declare a variable without assigning a value to it, the variable's initial value will be "undefined." For example:
`let x;
console.log(x); // Output: undefined
`
### Undeclared: An undeclared variable is a variable that has not been declared using the "var," "let," or "const" keywords. Attempting to use an undeclared variable will result in a reference error. For example:
`console.log(y); // Output: ReferenceError: y is not defined
`

### Uninitialized (Temporal Dead Zone - TDZ):The Temporal Dead Zone (TDZ) is a concept in JavaScript associated with the "let" and "const" declarations. When you declare a variable using "let" or "const," the variable exists in a temporal dead zone from the start of the block until the actual declaration is encountered. Trying to access the variable during this period will result in a ReferenceError. For example:
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

note **object.is**

---




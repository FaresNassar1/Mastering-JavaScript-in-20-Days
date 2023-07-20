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

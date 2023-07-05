# 2# Day Training Js
---
### Table of Contents
- [Operators
](#operators)
- [Variables](#variables)
- [Arrays](#arrays)




##Operators

####A_O
###`+ - * /`
- `"fares"+"!"`
- `44+22`
- `((4 + 1) * 2 * 4) + 2`==>42

####C_O
###`> , < , >= , <= `

####E_O
###`=== , ==, !== ,!=`
####`1=="1"`=>true!  `1==="1"`=>false
###.....etc

---
##Variables
####`let text;` text==>undefined
- [x] Declaring a variable `let bankruptcy;`
 - [x] Assigning a variable `let myDeclaredVariable;
myDeclaredVariable = "so value, much wow";`
 - [x] Declaring & assigning at once `let myAssignedVariable = "such efficient, amaze";`
 - [x] Declaring & assigning forever `const myUnchangeableVariable = "Never gonna give you up";`
  - [x] Using a variable `answerToLife - 10
`
- [x] Variable names
---
`let scrub = "guy that thinks he's fly";`

`let busta = scrub;`

`scrub = "guy that can't get no love from me";`

**the result**
==scrub=guy that can't get no love from me==
==busta=guy that thinks he's fly==

---
#Arrays

Arrays let us keep multiple values together in a single collection

**example**
`let synonyms=["fares","rafat","nassar"];`
arrays have a length And each value has an index and check if an array contains a certain value
`synonyms.length`
`synonyms[1]`
`synonyms.includes("rafat")
`
- [x] we can modify arrays
by index[]=newvalue
**.pop && .push**
- [x] Arrays can be empty, or hold a single item
` let emptyArray = [];`
`let oneItemArray = ["lonely"];`
- [x] Arrays can hold any type of items, or mix and match!
 `let mixedArray = ["pop", 6, "squish", false, document];`
`.sort()` for sorting the elements in the array
`.join()` 
==ex==: `synonyms.join(" ");`
the result **fares rafat nassar** 
`.concat()`
==ex==: [1, 2, 3].concat([4, 5, 6])
the result **[1,2,3,4,5,6]**

**mutable vs. immutable
"Mutable" data can be edited (e.g. Arrays)    
"Immutable" data always stays the same (e.g. strings & other primitives)**
`let letVariable = "original value";
letVariable = "new value";`Yes 
`const constVariable = "original value";
constVariable = "new Value";` No, **constant**

#....
---

####**object The next step**...........
# 2# Day Training Js
---
### Table of Contents
- [Operators
](#operators)
- [Variables](#variables)
- [Arrays](#arrays)




## Operators

### A_O

#### `+ - * /`
- `"fares"+"!"`
- `44+22`
- `((4 + 1) * 2 * 4) + 2`==>42

### C_O

#### `> , < , >= , <= `

### E_O

####  `=== , ==, !== ,!=`
#### `1=="1"`=>true!  `1==="1"`=>false
### .....etc

---
## Variables
#### `let text;` text==>undefined
- [x] Declaring a variable `let bankruptcy;`
- [x] Assigning a variable `let myDeclaredVariable;
myDeclaredVariable = "so value, much wow";`
- [x] Declaring & assigning at once `let myAssignedVariable = "such efficient, amaze";`
- [x] Declaring & assigning forever `const myUnchangeableVariable = "Never gonna give you up";`
- [x] Using a variable `answerToLife - 10
- [x] Variable names
---
`let scrub = "guy that thinks he's fly";`

`let busta = scrub;`

`scrub = "guy that can't get no love from me";`

**the result**
==scrub=guy that can't get no love from me==
==busta=guy that thinks he's fly==

---
# Arrays

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
**ex** : `synonyms.join(" ");`
the result **fares rafat nassar** 
`.concat()`
**ex** [1, 2, 3].concat([4, 5, 6])
the result **[1,2,3,4,5,6]**

**mutable vs. immutable
"Mutable" data can be edited (e.g. Arrays)    
"Immutable" data always stays the same (e.g. strings & other primitives)**
`let letVariable = "original value";

letVariable = "new value";`Yes 

`const constVariable = "original value";

constVariable = "new Value";` No, **constant**

####`let arr=[1,2,3]`

`let arr2=arr`=>arr2=[1,2,3]

`arr[1]=4`then `arr=[1,4,3]`

what do you think about arr2 ???

it will be take the new value 😹

`arr2=[1,4,3]`

# ....
---

## Coding Exercises

### [Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)

#### My Solution


```javascript
const contacts = [
  {
    firstName: "Akira",
    lastName: "Laine",
    number: "0543236543",
    likes: ["Pizza", "Coding", "Brownie Points"],
  },
  {
    firstName: "Harry",
    lastName: "Potter",
    number: "0994372684",
    likes: ["Hogwarts", "Magic", "Hagrid"],
  },
  {
    firstName: "Sherlock",
    lastName: "Holmes",
    number: "0487345643",
    likes: ["Intriguing Cases", "Violin"],
  },
  {
    firstName: "Kristian",
    lastName: "Vos",
    number: "unknown",
    likes: ["JavaScript", "Gaming", "Foxes"],
  },
];

function lookUpProfile(name, prop) {

  for (let x = 0; x < contacts.length; x++) {
    if (contacts[x].firstName === name) {
      if (contacts[x].hasOwnProperty(prop)) {
        return contacts[x][prop];
      } else {
        return "No such property";
      }
    }
  }
  return "No such contact";
}


lookUpProfile("Akira", "likes");
}

```

### [Copy Array Items Using slice()](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice)

#### My Solution


```javascript
function forecast(arr) {
  return arr.slice(2,4);
}

console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));

```

### [Combine Arrays with the Spread Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/combine-arrays-with-the-spread-operator)

#### My Solution


```javascript
function spreadOut() {
  let fragment = ['to', 'code'];
  let sentence=['learning',...fragment,'is','fun'];
  return sentence;
}
console.log(spreadOut());

```


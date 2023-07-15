# 2-4# Day Training Js

---
### Table of Contents

- [Classes & Prototypes-OOP](#)
- [Wrapping up](#)

---

## Classes & Prototypes-OOP

#### Core of development (and running code)
1. Save data (e.g. in a quiz game the scores of user1 and user2)
2. Run code (functions) using that data (e.g. increase user 2’s score)

 #### I want my code to be:
 
 1. Easy to reason about But also
2. Easy to add features to (new functionality)
3. Nevertheless efficient and performant
The Object-oriented paradigm aims is to let us achieve these three goals

**Objects - store functions with their associated data!**
```javascript
const user1 = {
 name: "Will",
 score: 3,
 increment: function() { user1.score++; }
};
user1.increment(); //user1.score -> 4

```
**Creating user2 user dot notation**
```javascript
const user2 = {}; //create an empty object
//assign properties to that object
user2.name = "Tim";
user2.score = 6;
user2.increment = function() {
 user2.score++;
};

```
**Creating user3 using Object.create**
`const user3 = Object.create(null);`

---

### Solution 1. Generate objects using a function

```javascript
function userCreator(name, score) {
 const newUser = {};
 newUser.name = name;
 newUser.score = score;
 newUser.increment = function() {
 newUser.score++;
 };
 return newUser;
};
const user1 = userCreator("Will", 3);
const user2 = userCreator("Tim", 5);
user1.increment()
```
* Problems: Each time we create a new user we make space in our computer's memory for all our data and functions. But our functions are just copiesIs there a better way?
#### Solution 2: Using the prototype chain
```javascript
function userCreator (name, score) {
 const newUser = Object.create(userFunctionStore);
 newUser.name = name;
 newUser.score = score;
 return newUser;
};
const userFunctionStore = {
 increment: function(){this.score++;},
 login: function(){console.log("Logged in");}
};
const user1 = userCreator("Will", 3);
const user2 = userCreator("Tim", 5);
user1.increment();
  ```

### if we want to confirm our user1 has the property score

```javascript
function userCreator (name, score) {
 const newUser = Object.create(userFunctionStore);
 newUser.name = name;
 newUser.score = score;
 return newUser;
};
const userFunctionStore = {
 increment: function(){this.score++;},
 login: function(){console.log("Logged in");}
};
const user1 = userCreator("Will", 3);
const user2 = userCreator("Tim", 5);
user1.hasOwnProperty('score')
```


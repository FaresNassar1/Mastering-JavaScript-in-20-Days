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


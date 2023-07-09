# 4# Day Training Js

---

### Table of Contents

- [Events & handlers](#events-&-handlers)
- [Conditionals](#)
- [Map & filter](#map-&-filter)
- [Doggos Quiz Game](#Doggos-Quiz-Game)

---

## Events & handlers

The web browser fires events when certain things happen on the page

For example, when the user clicks somewhere on the page, a click event is fired

```javascript
document.addEventListener("click", () => {
  console.log("clicked");
});
```

event.target is the element the event fired on

(in this case, which element was clicked)

```javascript
document.addEventListener("click", (event) => {
  console.log(event.target);
});
```

**"dblclick"
"mouseover"
"mouseout"**

---

## Quiz Project with Events & handlers

### [Quiz.js ](https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html)

```javascript
let trueButton = optionButtons[0];
trueButton.addEventListener("click", (event) => {
  trueButton.textContent = trueButton.textContent.toLocaleUpperCase();
});

let h1 = document.getElementsByTagName("h1");
h1 = h1[0];
h1.addEventListener("mouseover", () => {
  h1.textContent = "hovering";
});
h1.addEventListener("mouseout", () => {
  h1.textContent = "Quiz.js";
});
```

## Conditionals

- [x] if statements let us execute code under a certain condition

#### Example

```javascript
function compare(x, y) {
  if (x > y) {
    console.log(x, "is greater than", y);
  } else if (x < y) {
    console.log(x, "is less than", y);
  } else {
    console.log(x, "is equal to", y);
  }
}
```

- [x] Boolean (logical) operators

```javascript
let someoneIsAroundYou = false;
if (!someoneIsAroundYou) {
  console.log("baby I love you");
}
//===> baby I love you
```

- [x] more than one value

```javascript
if (you.happy && you.knowIt) {
  you.clapHands();
}
```

**shortcut" operator for writing quick conditionals**

`condition ? valueIfTrue : valueIfFalse;`

## Loops

Loops let us run the same chunk of code multiple times

```javascript
for (let rep = 0; rep < 10; rep += 1) {
  console.log("now doing rep", rep);
}
console.log("do you even lift bro");
```

**for vs of**

```javascript
const numbers = [1, 2, 3];
for (let i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
}
for (let n of numbers) {
  console.log(n);
}

//the same answer
```

---

## Quiz Project (Last part)

### [Quiz.js ](https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html)

```javascript
for (let button of optionButtons) {
  button.addEventListener("click", (event) => {
    explanation.textContent = fact.explanation;

    for (let obu of optionButtons) {
      disable(obu);
    }

    if (isCorrect(button.value)) {
      button.classList.add("correct");
    } else {
      button.classList.add("incorrect");
    }
  });
}
```

## Map & filter

---

**Map** calls a function on each item in an array to create a new array

```javascript
const spices = [
  { name: "Emma", nickname: "Baby" },
  { name: "Geri", nickname: "Ginger" },
  { name: "Mel B", nickname: "Scary" },
  { name: "Mel C", nickname: "Sporty" },
  { name: "Victoria", nickname: "Posh" },
];
const nicknames = spices.map(s => s.nickname + " Spice");
//===> Baby spice
     //Gingre spice
//....etc
```

#### hint 
 ``` `string to insert ${variable} into``` `

**Filter** calls a true/false function on each item

and creates a new array with only the items where the function returns true

`const mels = spices.filter(s => s.name.includes("Mel"));`


- [x] Spread (...)
```javascript
const skills = ["HTML", "CSS", "JS"];
const newSkills = ["React", "TypeScript", "Node"]
skills.push(...newSkills);
console.log(...skills);
``` 
---
- [x] **Doggos Quiz Game**

---
## Coding Exercises

### [Use Multiple Conditional (Ternary) Operators](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-multiple-conditional-ternary-operators)

#### My Solution
```javascript
function checkSign(num) {
  return num > 0 ? "positive"
    : num < 0 ? "negative"
      : "zero";
}
checkSign(10);
```

### [Golf Code](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/golf-code)

#### My Solution

```javascript
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  if (strokes == 1) {
    return names[0];
  } else if (strokes <= par - 2) {
    return names[1];
  } else if (strokes === par - 1) {
    return names[2];
  } else if (strokes === par) {
    return names[3];
  } else if (strokes === par + 1) {
    return names[4];
  } else if (strokes === par + 2) {
    return names[5];
  } else {
    return names[6];
  }

}
golfScore(5, 4);
```
### [Use the map Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-map-method-to-extract-data-from-an-array)
#### My Solution

```javascript
const ratings = watchList.map(item => ({
  title: item["Title"],
  rating: item["imdbRating"]
}));
```

### [Use the filter Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-filter-method-to-extract-data-from-an-array)
#### My Solution

```javascript
const filteredList = watchList
  .filter(movie => {
    return parseFloat(movie.imdbRating) >= 8.0;
  })
  .map(movie => {
    return {
      title: movie.Title,
      rating: movie.imdbRating
    };
  });
```


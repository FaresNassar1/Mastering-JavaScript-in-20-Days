# 5# Day Training


### Table of Contents
- [Data Fetching & Promises](#)
- [Destructuring Data](#)
- [Async](#)
- [Modules](#)
- [Wrapping up](#)

---
## Data Fetching & Promises

`fetch("https://dog.ceo/api/breed/hound/list")
//==>Promise {<pending>}`
It takes time to fetch data from the network  

### **Promises**

**Promises can be in 3 possible states:**

1. pending: still waiting for the value, hang tight
2. fulfilled (aka "resolved"): finally got the value, all done
3. rejected: sorry couldn't get the value, all done
It takes time for Promises to resolve, so they are "asynchronous"

### **await**
**await** lets us tell JS to stop and wait for an asynchronous operation to finish

`let response = await fetch("https://dog.ceo/api/breed/hound/list");
console.log(response);`

In the case of a Promise, it waits for it to resolve before continuing with our code

* Calling the .json() method on the response parses its body as a JSON object
` let body = await response.json()`

--- 
## Destructuring

* Destructuring is a fancy way of declaring multiple variables at once
`let {name, nickname} = spices[0];`
`let {nickname} = spices[2];`
`const [baby, ginger, scary, sporty, posh] = spices;`
`const [,,melB] = spices;`

**We can use ... to collect remaining values**
`const [babySpice, ...adultSpices] = spices;`

## Async functions

```javascript
async function fetchResponse(url) {
    const response = await fetch(url);
    return response;
}
```
**This tells JS to expect to await async operations inside the function**

---
## Modules
* Modules let us split big codebases across multiple files

`<script type="module">
    //...
</script>`

- [x] **import && export**
 `// myModule.js
const veryUsefulFunction = () => "I came from a module";
export { veryUsefulFunction };`
### Debugging

* console.log() (or .warn() or .error()) is one way to understand what's happening when your program runs

```javascript
function whyIsntThisWorking(input) {
    console.log("Well at least we got this far");
    console.log(input);
    return thingThatDoesntWork(input);}
```


* You can also use the browser's debugger to pause JS and inspect what's happening
JAVA

---

## [Task requirements ](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week1-day5-task/task.md)

### My Solution 

```javascript 
const getElements = document.getElementById("characterList");
const fetchCharacters = async () => { 

    try {
    const url = "https://rickandmortyapi.com/api/character?status=alive";
    const response = await fetch(url);
    const data = await response.json();
    const characters = data.results.filter(
      (character) => (character.status = "Alive")
    );
    const slicedData = characters.slice(0, 50);


    slicedData.forEach((elemen) => {
      const { name, image, location, species, gender } = elemen;
      const li = document.createElement("li");
      const n = document.createElement("p");
      n.textContent = `Name : ${name}`;
      const i = document.createElement("img");
      i.setAttribute("src", image);
      const l = document.createElement("p");
      l.textContent = `From:${location.name}`;
      const s = document.createElement("p");
      s.textContent = `species:${species}`;
      const g = document.createElement("p");
      g.textContent = `gender :${gender}`;
      li.appendChild(i);
      li.appendChild(n);
      li.appendChild(l);
      li.appendChild(s);
      li.appendChild(g);

      getElements.appendChild(li);
   
    });
  
} catch (error) {
  console.log('There was an error', error);
}
}

fetchCharacters();


```

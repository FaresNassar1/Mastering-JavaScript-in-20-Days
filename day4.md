# 4# Day Training Js
---
### Table of Contents
- [Events & handlers](#events-&-handlers)
- [Conditionals](#conditionals)
- [Map & filter](#map-&-filter)
- [Doggos Quiz Game](#Doggos-Quiz-Game)

---

## Events & handlers
The web browser fires events when certain things happen on the page

For example, when the user clicks somewhere on the page, a click event is fired

```javascript
document.addEventListener("click", () => {
    console.log("clicked")
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
##Quiz Project with Events & handlers

### [Quiz.js ](https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html)
```javascript
 let trueButton= optionButtons[0];
            trueButton.addEventListener("click",(event)=>
            {
                  trueButton.textContent=trueButton.textContent.toLocaleUpperCase();

            });

            let h1=document.getElementsByTagName("h1");
            h1=h1[0];
            h1.addEventListener("mouseover",()=>{
              h1.textContent="hovering";

            });
            h1.addEventListener("mouseout",()=>{
              h1.textContent='Quiz.js';


            })
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
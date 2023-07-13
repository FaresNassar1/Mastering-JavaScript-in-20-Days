# 2-3# Day Training Js
---
### Table of Contents
- [Async JavaScript](#)
- [Promises](#)

---

## Async JavaScript

- Promises - the most signficant ES6 feature
- Asynchronicity - the feature that makes dynamic web applications possible
- The event loop - JavaScript’s triage
- Microtask queue, Callback queue and Web Browser features (APIs)

 **JavaScript is:**
- Single threaded (one command runs at a time)
- Synchronously executed (each line is run in order the code appears)

  #### note - Accessing Twitter’s server to get new tweets that takes a long time !!!

Slow function blocks further code running
  ```javascript
const tweets = getTweets("http://twitter.com/will/1")
// ⛔350ms wait while a request is sent to Twitter HQ
displayTweets(tweets)
// more code to run
console.log("I want to runnnn!")

  ```
```javascript
function printHello(){
 console.log("Hello");
}
setTimeout(printHello,1000);
console.log("Me first!");
//it will be print Me first and after 1000ms Hello
```
**note:setTimeout is a Browser feature called Timer** 🪕

So what about a delay of 0ms!!

`//Me first! and then Hello`

---

Our core JavaScript engine has 3 main parts:
- Thread of execution
- Memory/variable environment
- Call stack


  We need to add some new components:
- Web Browser APIs/Node background APIs
- Promises
- Event loop, Callback/Task queue and micro task queue 

```javascript
function printHello(){ console.log("Hello"); }
setTimeout(printHello,1000);
console.log("Me first!");
/// 0ms printHello x not complete . ==>
 1ms Me first! then after 1000ms  Hello
note: call stack prinHello()
```


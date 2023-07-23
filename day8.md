
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
// 0ms printHello x not complete . ==>
// 1ms Me first! then after 1000ms  Hello
//note: call stack prinHello()
```

ES6+ Promises

```javascript
function display(data){
 console.log(data)
}
const futureData = fetch('https://twitter.com/will/tweets/1')
futureData.then(display);

console.log("Me first!");
```
### ES6+ Solution (Promises)

**Special objects built into JavaScript that get returned immediately when we make
a call to a web browser API/feature (e.g. fetch) that’s set up to return promises
(not all are)
Promises act as a placeholder for the data we expect to get back from the web
browser feature’s background work**

how our promise-deferred functionality
example
```javascript
function display(data){console.log(data)}
function printHello(){console.log("Hello");}
function blockFor300ms(){/* blocks js thread for 300ms }
setTimeout(printHello, 0);
const futureData = fetch('https://twitter.com/will/tweets/1')
futureData.then(display)
blockFor300ms()
console.log("Me first!");
```
--- 

## [Tasks](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day3-tasks/tasks.md)
### Question 1:


### My Solution

```javascript
const task1 = (cb) => setTimeout(() => {
  const message = "Task 1 has executed successfully!";
  cb(message);
}, 3000);

const task2 = (cb) => setTimeout(() => {
  const message = "Task 2 has executed successfully!";
  cb(message);
}, 0);

const task3 = (cb) => setTimeout(() => {
  const message = "Task 3 has executed successfully!";
  cb(message);
}, 1000);

const task4 = (cb) => setTimeout(() => {
  const message = "Task 4 has executed successfully!";
  cb(message);
}, 2000);

const task5 = (cb) => setTimeout(() => {
  const message = "Task 5 has executed successfully!";
  cb(message);
}, 4000);

const asyncTasks = [task1, task2, task3, task4, task5];

const executeInSequenceWithCBs = (tasks, callback) => {
  const results = [];

  const executeTask = (index) => {
    if (index >= tasks.length) {
      callback(results);
      return;
    }

    const cb = (message) => {
      results.push(message);
      executeTask(index + 1);
    };

    tasks[index](cb);
  };

  executeTask(0);
};

executeInSequenceWithCBs(asyncTasks, (messages) => {
  console.log(messages); 
});

```
### Question 2:
```javascript 

const apis = [
  {
    apiName: "products", 
    apiUrl: "https://dummyjson.com/products",
  }, 
  {
    apiName: "users", 
    apiUrl: "https://dummyjson.com/users",
  }, 
  {
    apiName: "posts", 
    apiUrl: "https://dummyjson.com/posts",
  }, 
  {
    apiName: "comments", 
    apiUrl: "https://dummyjson.com/comments",
  }
];

const executeInParallelWithPromises = (apis) => {
  const apiPromises = apis.map(api => {
    return fetch(api.apiUrl)
      .then(response => response.json())
      .then(apiData => ({
        apiName: api.apiName,
        apiUrl: api.apiUrl,
        apiData: apiData,
      }))
      .catch(error => ({
        apiName: api.apiName,
        apiUrl: api.apiUrl,
        apiData: null,
        error: error.message,
      }));
  });

  return Promise.all(apiPromises);
};

// Usage example
executeInParallelWithPromises(apis)
  .then(results => {
    console.log(results);
  })
  .catch(error => {
    console.error(error);
  });

```

### Question 3:

```javascript
const apis = [
  {
    apiName: "products", 
    apiUrl: "https://dummyjson.com/products",
  }, 
  {
    apiName: "users", 
    apiUrl: "https://dummyjson.com/users",
  }, 
  {
    apiName: "posts", 
    apiUrl: "https://dummyjson.com/posts",
  }, 
  {
    apiName: "comments", 
    apiUrl: "https://dummyjson.com/comments",
  }
];

const executeInSequenceWithPromises = async (apis) => {
  const results = [];

  for (const api of apis) {
    try {
      const response = await fetch(api.apiUrl);
      const apiData = await response.json();
      results.push({
        apiName: api.apiName,
        apiUrl: api.apiUrl,
        apiData: apiData,
      });
    } catch (error) {
      results.push({
        apiName: api.apiName,
        apiUrl: api.apiUrl,
        apiData: null,
        error: error.message,
      });
    }
  }

  return results;
};

// Usage example
executeInSequenceWithPromises(apis)
  .then(results => {
    console.log(results);
  })
  .catch(error => {
    console.error(error);
  });


```


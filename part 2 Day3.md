# #3 Day training
--- 
### Async JavaScript 

JavaScript is:
- Single threaded (one command runs at a time)
- Synchronously executed (each line is run in order the code appears)

 So what if we have a task:
- Accessing Twitter’s server to get new tweets that takes a long time
- Code we want to run using those tweets
What if we try to delay a function directly using setTimeout?

```javascript
function printHello(){
 console.log("Hello");
}
setTimeout(printHello,1000);
console.log("Me first!");
//Me first then Hello
```
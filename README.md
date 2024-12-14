# Node.js Interview Questions - Day 1

## Q1. What is Node.js?
**1** -- node is a JavaScript runtime environment that allow run the code.
**2** -- Its build on Chrome V8 JavaScript engine. 
**3**-- nodejs used server-side programming languages.

## Q2. What is the event loop in Node.js?
The event loop in Nodejs that handles asynchronous operations.The event loop continuously checks for tasks like timer, ensuring smooth execution of asynchronous code.

## Q3. What are the core modules in Node.js?
Core modules in Node.js are provide essential functionalities without needing external libraries.
fs,http,path,os,event,url

## Q4. What is the purpose of the require() function in Node.js?
The require() function is used to load modules in Nodejs. It allows you to include third-party modules in application.
**ex**
const fs = require('fs');

## Q5. What is the difference between require and import in Node.js?

**import**  -- it is es6 part that define the (type: module) use Asynchronous task .
**require** -- it use js import Synchronous task by default (type :CommonJS).


## Q6. What are callbacks in Node.js?
A callback is a function passed as an argument to another function which is execute after the completion of that function. callback enables asynch execution doesnot have to wait for an operation to complete and can move the next task .


setTimeout(() => { 
    console.log('Callback Function in node here'); 
}, 1000);

## Q7. What is npm in Node.js?
npm (Node Package Manager) is the default package manager for Node.js. It is used to-
1. Install, update, or uninstall packages.
2. Manage dependencies in a project.

**Ex**
Initialize project: `npm i `

## Q8. What is the difference between process.nextTick(), setImmediate(), and setTimeout() in Node.js?

 **`process.nextTick()`**  It Executes a callback immediately after the current operation,before I/O events.
 **Ex:**   process.nextTick(() => console.log('Next Tick'));

 **`setImmediate()`**  Executes a callback after I/O events in the event loop.
**Ex:** setImmediate(() => console.log('Immediate'));
 **`setTimeout()`**  Executes a callback after a specified delay.
 **Ex:** setTimeout(() => console.log('Timeout'), 0);


## Q9. How do you handle errors in Node.js?
Error handling in Nodejs are--
1. **Callbacks**: Pass an error object as the first parameter.

2. **Promises**: Use `.catch()` for error handling.

3. **Async/Await**: Wrap the code in a `try-catch` block.

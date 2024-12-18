# Node.js Interview Questions - Day 1

## Q1. What is Node.js?
1. node is a JavaScript runtime environment that allow run the code.
2. It is built on Chrome's V8 JavaScript engine.
3. Node.js is used for server-side programming.

## Q2. What is the event loop in Node.js?
1.The event loop in Node.js handles asynchronous operations. 
2. It continuously checks for tasks like timers, I/O operations, and other callbacks, ensuring smooth execution of asynchronous code.

## Q3. What are the core modules in Node.js?
Core modules in Node.js provide essential functionalities without needing external libraries.
- `fs` (File System)
- `http` (HTTP Server and Client)
- `path` (File and Directory Paths)
- `os` (Operating System Information)
- `events` (Event Handling)
- `url` (URL Parsing)

## Q4. What is the purpose of the require() function in Node.js?
The `require()` function is used to load modules in Node.js. It allows you to include core, local, or third-party modules in your application.

**Ex**
```
const fs = require('fs');
```

## Q5. What is the difference between require and import in Node.js?
- **`import`**: Part of ES6, used for asynchronous module loading, and requires `"type": "module"` in `package.json` or `.mjs` file extension.
- **`require`**: CommonJS syntax, used for synchronous module loading by default in Node.js.

## Q6. What are callbacks in Node.js?
A callback is a function passed as an argument to another function, which is executed after the completion of that function. Callbacks enable asynchronous execution, allowing Node.js to move to the next task without waiting for the previous one to complete.

**Ex**
```
setTimeout(() => {
    console.log('Callback Function in Node.js');
}, 1000);
```

## Q7. What is npm in Node.js?
**npm (Node Package Manager)** is the default package manager for Node.js. It is used to:
1. Install, update, or uninstall packages.
2. Manage dependencies in a project.

**Example:**
```bash
npm i 
```

## Q8. What is the difference between process.nextTick(), setImmediate(), and setTimeout() in Node.js?
- **`process.nextTick()`**: Executes a callback immediately after the current operation, before I/O events.
  **Ex**
  ```
  process.nextTick(() => console.log('Next Tick'));
  ```

- **`setImmediate()`**: Executes a callback after I/O events in the event loop.
  **Ex**
  ```
  setImmediate(() => console.log('Immediate'));
  ```

- **`setTimeout()`**: Executes a callback after a specified delay.
  **Ex**
  ```
  setTimeout(() => console.log('Timeout'), 0);
  ```

## Q9. How do you handle errors in Node.js?
Error handling in Nodejs are ---

1. **Callbacks**: Pass an error object as the first parameter.
   ```
   const fs = require('fs');
   fs.readFile('nonexistent.txt', 'utf8', (err, data) => {
     if (err) {
       console.log(err.message);
       return;
     }
     console.log(data);
   });
   ```

2. **Promises**: Use `.catch()` for error handling.
   ```
   const fs = require('fs').promises;
   fs.readFile('nonexistent.txt', 'utf8')
     .then(data => console.log(data))
     .catch(err => console.log(err.message));
   ```

3. **Async/Await**: Wrap the code in a `try-catch` block.
   ```
   const fs = require('fs').promises;
   async function readFile() {
     try {
       const data = await fs.readFile('nonexistent.txt', 'utf8');
       console.log(data);
     } catch (err) {
       console.log(err.message);
     }
   }

   readFile();
   ```

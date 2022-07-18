# Introduction to Node.JS
 
## Introduction
  - For longest time, JavaScript could only be run in web browser
  - Node.js is a JavaScript runtime, or an environment that allows us to execute JavaScript code outside of the browser
  - A runtime converts high-level code and compiles it down to code the computer can execute, aka machine language
  - Node was created with the goal of building web servers and web applications in JavaScript
  - Can also be used for creating command-line applications or desktop applications
  
## The Node REPL
  - REPL = Read Eval Print Loop
  - Program that loops through 3 different states
    - Read state  
    - Eval state
    - Print state
  - Node.Js comes with built in repl (type 'node' into cli)
  - Will evaluate input line by line
  
  - By hitting 'enter', you indicate the input is ready for eval
  - If you want multiple lines evaluated at once, you can type '.editor'
    - hit 'control' + 'd' when you are ready for input to be evaluated

## Running a Program with Node
  - Node has ability to run JS programs locally instead of just in browser console or embedded HTML
  - The file to be run needs a '.js' extension
  - To execute a program, we use 'node example.js'

## Core Modules
  - Node.js has several built-in modules to perform common tasks efficiently (called *core modules*)
  - Located in the **/lib** folder in the source code
  - Modules can be required by passing string name into require function
  ```JavaScript
    node
    const events = require('events')
    require('module').builtinModules  // all modules
  ```
  
## The Console Module
  - Terminal is used to send/receive text feedback to/from a program 
  - The built-in console module exports a global console object that gives the terminal similar functionality to console in web browser
  - Since console is a global module, it does not need to be required and its methods can be accessed anywhere
  ```JavaScript
    let arr = [1,2,3,4];
    console.log(arr);
    console.table(arr);
    console.assert(arr.length === 3); //assertion failed
  ```
  
## The Process Module
  - A process is an instance of computer program that is being executed
  - Node has a global process object with useful methods and properties about current process
  - 'process.env' stores and controls information about the environment the current process is running in
  ```
    node
    process.env.PATH // string with path to process
  ```
  - 'process.memoryUsage()' returns info on CPU demands of current process
  ``` JavaScript
  {
    rss: 38432768,
    heapTotal: 5316608, //bytes
    heapUsed: 3719208,
    external: 1718910,
    arrayBuffers: 9922
  }
 ```
 - 'process.argv' is an array of values provided when current process was started
 ```Js
   node example.js one two three
   console.log(process.argv) // ['node', 'example.js', 'one', 'two', 'three']
 ```
 - [Process Documentation](https://nodejs.org/api/process.html)

## The OS Module
  - Not global, needs to be included (required)
  - Some methods include
    - os.type() -> return computer's os 
    - os.arch() -> return the cpu architecture
    - os.networkInterfaces -> return info such as IP or MAC address
    - os.homedir() -> return current user's home directory
    - os.hostname() -> return hostname of os
    - os.uptime() -> return system uptime in seconds
  
  ```Js
    const os = require('os');
    let osInfo = {
      type: os.type(),
      architecture: os.architecture(),
      uptime: os.uptime()
    };
    console.log(osInfo);
  ```
  
## The Util Module
  - Must be required
  - Provides useful methods to help maintain and debug code
  - One useful/important object is 'type' (provides methods for runtime type checking)
  ```Js
    const util = require('util');
    let todaysDate = new Date();
    let tomorrow = 'July 19, 2022';
    console.log(util.types.isDate(todaysDate)); // true
    console.log(util.types.isDate(tomorrow));   // false
  ```
  - Another useful method is '.promisify()'
    - Turns callback functions into promises  

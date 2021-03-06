# [Node.js](https://nodejs.org/en/docs/) Essentials

## The Event Module
  - Node is described as having an "event-driven architecture"
  - The 'event' module has an 'EventEmitter' class
  - Each instance has an ```.on()``` method which adds a listener callback function to a named event
    - 1st arg = name of event as string
    - 2nd arg = the listener callback function
  - Each instance also has an ```.emit()``` method that announces a named event has occured
    - 1st arg = name of event as string
    - 2nd arg = data that should be passed into listener callback function

  ```Js
    const events = require('events');
    let listenerCallBack = data => {
      console.log(`Congradulations ${data}!`);
    }
    
    let myEmitter = events.EventEmitter();
    myEmitter.on('congradulate', listenerCallBack);
    myEmitter.emit('congradulate', 'Sam');
    
    // Congradulations Sam!
  ```
  
## User Input/Output
  - ```console.log()``` is a thin wrapper around the ```.stdout.write()``` method on the process object
  - Can also receive input through terminal using the ```.stdin.on()``` method on the process object
  ```Js
    process.stdin.on('data', (userInput) => {
      let input = userInput.toString();
      console.log(input);
    }
  ```
  - Under the hood, ```process.stdin``` is an instance of 'EventEmitter'
  - 'data' event is triggered when user enters text into terminal and hits enter
  - Data entered is an instance of 'Buffer' class... convert to string

## The Error Module
  - Global; no need to require it
  - Node's error module has all the JavaScript errors as well as its Error class (for creating new ones)
    - EvalError, SyntaxError, RangeError, ReferenceError, TypeError, and URIError
  - Can generate errors and throw them, and (w/ synchronus code) can use error handling like ```try...catch```
  - Many asych Node APIs use *Error-first callback functions*
    - Error is first arg, data is second arg
    - If the asych task results in an error, it will be passed as first arg
    - Else first arg will be 'undefined'
  ```Js
    const errorFirstCallBack = (error, data) => {
      if (err) {
        console.log('There was an error: ' + error);
      } else {
        console.log('There was no error: ' + data);
      }
    }
  ```
  - **Return to this module**
  
## The Buffer Module
  - Used to handle binary data
  - In the global scope
  - 'Buffer' object represents a fixed amount of memory that cannot be resized
  - Similar to array of integers, but each element is a *byte* of data
  - Buffer object will have range of 0 - 255 (inclusive)
  - The ```.alloc(size, fill, encoding)``` allocates space for new Buffer object
    - size: the size of the buffer, *required*
    - fill: value to fill buffer with (default is 0), *optional*
    - encoding: (default is UTF-8), *optional*
  ```Js
    const buff = Buffer.alloc(5);
    console.log(buff); // [0,0,0,0,0]
  ```
  
  - The ```.toString(encoding, start, end)``` translates buffer object into humand readable string
    - encoding: default is UTF-8, *optional*
    - start: byte offset to begin translating, *optional*
    - end: byte offset to end translating, *optional*
  ```Js
    const buff = Buffer.alloc(5, 'a');
    console.log(buff.toString());       //aaaaa
  ```
  
  - The ```.from(object, encoding)``` method creates new buffer from specificed string, array, or buffer
    - object: an object to fill the buffer with, *required*
    - encoding: default is utf-8, *optional*
    ```Js
      const buff = Buffer.from('hello');
      console.log(buffer);              // [104, 101, 108, 108, 111]
    ```
    
  - The ```.concat(array, length)``` method joins all Buffer objects in an array into one Buffer object
    - array: array containing Buffer objects , *required*
    - length: specify length of concatenated buffer , *optional*
  ```Js
    const buff1 = Buffer.from('hello');
    const buff2 = Buffer.from('world');
    const buff = Buffer.concat([buff1, buff2]);
    console.log(buff);  // [104, 101, 108, 108, 111, 119, 111, 114, 108, 100]
  ```

## The FS Module
  - All data on computer is organized in a *file system*
  - Important to have limited access to a user's filesystem when running JS on a browser (*sandboxing*)
  - Sandboxing protects users from malicious programs and invasion of privacy
  - Important to have less restricted access when working in backend
  - The ```fs``` core module is an API modeled after POSIX standard for interacting with the **f**ile **s**ystem
  - Each method has one synchronus and one asynchronus version
  ```Js
    const fs = require('fs');
    let readDataCallback = (err, data) => {
      if (err) {
        console.log(`There was an error: ${err}`);
      } else {
        console.log(`Data was found: ${data}`);
      }
    fs.readFile('./example.txt', 'utf-8', readDataCallback);
  ```
  - The ```fs.readFile(path, encoding, callback)``` is invoked with 3 arguments
    - path: string with path to file
    - encoding: character encoding 
    - callback: callback fxn to be invoked when asynchronus task of reading from filesystem is complete. *Node passes file contents as second argument to callback fxn*


## Readable Streams
  - In a more realistic scenario, data is not processed all at once
  - It is processed sequentially, piece by piece, this is known as a *stream*
  - Preferable, do not need all the necessary ram to process at once, don't need all the data on hand to begin processing
  - Simple example: reading and writing to files line by line
  ```Js
    const fs = require('fs');
    const readline = require('readline');
    
    // myInterface is an EventEmitter object, setup to emit 'line' events
    // 'line' event is emitted after each line is read from the file
    let myInterface = readline.createInterface({
      // create stream from example.txt file:
      input: fs.createReadStream('example.txt');
    });
    
    // assign listener callback that fires when 'line' events are executed
    myInterface.on('line', (fileLine) => {
      console.log(`This line read: ${fileLine}`);
    });
  ```
  
## Writeable Streams
  - Can also write data to streams
  - Can create write streams with ```fs.createWriteStream('example.txt')```
  - Unlike read streams, write streams can remain open forever, must close (end) them when done
  ```Js
    const fs = require('fs');
    let fileStream = fs.createWriteStream('example.txt');
    
    fileStream.write('Writing to the first line');
    fileStream.write('Writing to the second line');
    fileStream.end();
  ```
  
  ### Combine the Two
  ```Js
    const rl = require('readline');
    const fs = require('fs');

    let myInterface = rl.createInterface({
      input: fs.createReadStream('input.txt');
    });

    let fileStream = fs.createWriteStream('output.txt');

    const listenerCallback = line => {
      fileStream.write(`Writing from input.txt: ${line}`);
    }

    myInterface.on('line', listenerCallback);
    fileStream.end();
  ```
  
## The Timers Module
  - The ```timer``` module is global
  - When we want some code to be executed at a specific point in time
  - Time functions are added to the Node.js event loop
    - Timer functions are scheduled and put into a queue
    - Queue is processed at every iteration of the event loop
  - ```setImmediate()``` can be compared with ```setTimeout()``` function
  - ```setImmediate()``` executes specified callback fxn after the current [poll phase](https://nodejs.org/en/docs/guides/event-loop-timers-and-nexttick/#setimmediate-vs-settimeout) is completed
    - 1st arg: call back function, *required*
    - 2nd arg: arguments for callback function, *optional*
  - With many ```setImmediate()``` fxns, they will be executed in order of creation

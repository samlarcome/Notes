# Implementing [Modules](https://nodejs.org/docs/latest-v14.x/api/modules.html) in Node

## Module.exports
  - To create a new module, simply create a file where functions can be declared
  - To make fxns available to other files, add them as properties to ```modules.export``` object
    - Built in object to the node runtime environment  
  ```Js
    // test.js
    let foo = () => {
      // do something
    };
    module.exports.foo = foo;
    // OR
    module.exports.bar = function() {
      // do something
    };
  ```

## require()
  - ```require()``` fxn takes a file path (as string) to module
  ```Js
    const examples = require('./test.js');
    
    const fooCall = examples.foo();
    const barCall = examples.bar();
  ```
  
## Using Object Destructing to be more Selective with require()
  - Sometimes only want one or two functions from a module with many functions
  ```Js
    const {foo} = require('./test.js');
    
    const fooCall = foo();
  ```
  

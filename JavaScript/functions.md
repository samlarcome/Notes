# Functions

## Function Declaration
  ```javascript
  function fnName() {
    //Body of function
  }
  ```
  
## Parameters and Arguments
  - Pretty standard
  ```javascript
  function test(arg1, arg2) {
    return arg1 * arg2
  }
  
  test(2, 3)
  ```
  
## Default Parameters
  - Pretty standard
  ```javascript
  function testing(arg1, arg2 = 'default') {
    // function body
  }
  ```
  
## Function Expressions
  - Unlike function declarations, function expressions are not hoisted so they cannot be called before they are defined
  ```javascript
  const identifier = function(parameters) {
    // do something
  }
  ```
  
## Arrow Functions
  -  Shorter way to write functions
  -  Remove the need to type out the keyword function

  ```javascript
  // different number of parameters
  const testing = () => {}
  const testing = param1 => {}
  const testing = (param1, param2) => {}

  //single line block
  const add = number => num + num
  
  //multi line block
  const add = number => {
    return number + number
  }
  ```
  
  
  
  
  
  

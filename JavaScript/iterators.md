# Higher-Order Functions

## Functions as Data
  - Functions behave like any other data type 
  - We can assign functions to variables, and reassign them to new variables

  ```JavaScript
    const thisIsAReallyLongFunctionName = () => {
      // do something
    };
    const fxn = thisIsAReallyLongFunctionName;
    fxn();
  ```
  - fxn is a variable that holds the reference to the original function (they share the same memory address)
  - Notice we don't use parenthesis when assigning the variable, but we do when calling the function
    - When we assign the variable, we want the value of the function, not the value it returns
  - Functions are first-class objects
    - Means functions can have properties and methods (.length, .name, .toString(), etc)

  ```JavaScript
    console.log(fxn.name) // thisIsAReallyLongFunctionName
  ```
  
## Functions as Parameters
  - Higher-order functions are functions that accept functions as parameters, returns a function, or both
  - Functions that get passed in as parameters are callback functions
  - Invoked during the execution of the higher-order function
  - Pass in the function itself by typing the function name without the parentheses

  ```JavaScript
    const addFour = num => {
      return num+4;
    }
    // higher order function
    const checkConsistency = (fxn, value) {
      if ((value+4) === fxn(value)) {
        return true;
      } else {
        return false;
      }
    }
    console.log(checkConsistency(addFour, 4));
  ```
  
# Iterators
  - Built-in array methods that help iterate are called iterators. 
  - Iterators are methods called on arrays to manipulate elements and return values

## .forEach() Method
  - Executes the same code for each element in array
  - Takes a callback function for an argument
  - Return value is always undefined

  ```JavaScript
    let fruits = ['apples', 'oranges', 'bananas'];
    // a few ways to pass functions
    fruits.forEach(function(fruit) {
      console.log(`I like to eat ${fruit}`);
    }
    
    // arrow functions*
    fruits.forEach(fruit => console.log(`I like to eat ${fruit}`));
    
    // define function before
    functon logFruits(fruit) {
      console.log(`I like to eat ${fruit}`);
    }
    fruits.forEach(logFruits);
  ```

## .map() Method
  -  Takes a callback function as an argument and returns a new array

  ```JavaScript
    let nums = [1,2,3,4,5]
    let largeNums = nums.map(num => {
      return num * 100;
    }
    console.log(largeNums); // [100,200,300,400,500]
  ```

## .filter() Method
  - Returns a new array like .map()
  - Returns an array of elements that filters out certain elements from the original array
  - The callback function should return true or false depending on element passed to it
  
  ```JavaScript 
    let nums = [74,23,5,34,1034];
    const bigNums = nums.filter(num => {
      return num > 30;
    }
    console.log(bigNums); // [74, 34, 1034]
  ```
  
## .findIndex() Method
  - Returns the index of the first element that evaluates to true in the callback function
  - Will return -1 if there is no element that satisfies the callback function
  
  ```JavaScript 
    const names = ['Sam', 'Bob', 'Billy', 'Max'];
    const startsWithB = names.findIndex(name => {
      return name[0] === 'B';
    }
    console.log(startsWithB); // 1
  ```
  
## .reduce() Method
  - Returns a single value after iterating through the elements of an array, thereby reducing the array
  - Can take an optional second argument that is the intial value of the accumulator below
  - This is best shown by an example 

  ```JavaScript
    const nums = [1, 3, 5, 7];

    const sum = nums.reduce((accumulator, currentValue) => {
      return accumulator + currentValue;
    }, 10) // 10 is the initial value for accumulator
  
    console.log(newSum); // 16
  ```






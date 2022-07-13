# Error Handling

## Runtime Errors
  - ReferenceError: when a variable or function cannot be found
  - TypeError: when a value is not a valid type

## Constructing an Error
  - JavaScript errors are objects that have a name and message property
  - What if we want to throw an error that is not covered by the built in errors?
  - Can use the "Error()" function to make our own error object
  - *Creating an error is not the same as throwing an error*
  - Throwing an error will cause the program to stop

  ```JavaScript
    // Both work the same
    console.log(new Error('Created an error'));
    console.log(Error('Created an error'));
  ```
  
## The Throw Keyword
  - An error must be thrown to stop program, which can be done w/ the "throw" keyword

  ```JavaScript
    throw Error('This causes program to stop');
  ```
  
## Try Catch Statement
  - Have the ability to anticipate and handle errors
  - Have the 'try...catch' statement

  ```JavaScript
    try {
      throw Error('error');
    catch (e) {
      console.log(e); // 'error'
    {
  ```

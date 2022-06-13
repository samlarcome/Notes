# Loops

## For Loops
  ```JavaScript
    for(let i = 0; i < 10; i++) {
      console.log(i)
    }
    
    // loop through an array
    for(let i = 0; i < array.length; i++) {
      console.log(array[i])
    }
    
    // nested loops
    for(let i = 0; i < array.length; i++) {
      for(let j = 0; j < array2.length; j++) {
        //do something
      }
    }
  ```
  
## While Loops
  ```JavaScript
    let i = 0
    while (i < array.length) {
      // do something
    }
  ```
    
## Do While Loops
  - Allows you to perform a task once before entering a loop
  - Task in the loops is always performed at least once
  ```JavaScript
    do {
      // do something
    } while (condition)
  ```
    
  

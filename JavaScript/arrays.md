# Arrays

## Create an Array
  - Pretty standard
  - One way we can create an array is to use an array literal 
  - An array literal creates an array by wrapping items in square brackets []
  
  ```JavaScript
    let arrayName = ['hi', 'my name', 'is Sam']
  ```
 
## Accessing an Array
  - Arrays are zero-indexed
  - Use bracket notation to index an array (same for a string)
  
  ```JavaScript
    let cities = ['Atkinson', 'Windham', 'Concord']
    console.log(cities[0])
  ```
  
## Updating Elements
  ```JavaScript
    cities[2] = 'Boston'
    // cities = ['Atkinson', 'Windham', 'Boston']
  ```
  
## Arrays with Const
  - Variables assigned with const cannot be reassigned
  - An array declared with const does remain mutable
  - However, cannot reassign a new array or variable
  
## Basic Properties and Methods
  - '.length' property returns number of elements in an array
  ```JavaScript
    console.log(cities.length)
    // 3
  ```

  - '.push()' method allows us to append items to end of an array
  - Can take a single argument, or many separated by commas
  - Referred to as a destructive method as it changes initial array
  ```JavaScript
    cities.push('New York', 'York')
    // cities = ['Atkinson', 'Windham', 'Boston', 'New York', 'York']
  ```
  
  - '.pop()' method removes and returns the last item in an array
  ```JavaScript
    let city = cities.pop()
    // city = York
    // cities = ['Atkinson', 'Windham', 'Boston', 'New York']
  ```
    
  - '.shift()' removes and returns the first item from an array
  ```JavaScript
    console.log(cities.shift())
    // cities = ['Windham', 'Boston', 'New York']
  ```
  
  - '.unshift()' adds one or more elements to start of array and returns updated length
  ```JavaScript
    console.log(cities.unshift('Atkinson', 'Haverhill'))
    // cities = ['Atkinson', 'Haverhill', 'Windham', 'Boston', 'New York']
    
  - '.slice(inclusive, exclusive)' returns a shallow copy (same reference) 
  ```JavaScript
    console.log(cities.slice(2, 4))
    // ['Windham', 'Boston']
  ```
  
  - '.indexOf(arg)' returns the index of argument in the array (-1 if not present)
  ```JavaScript
    console.log(cities.indexOf('Haverhill')
    // 1
  ```
  
## Functions and Arrays
  - Arguments that are arrays are passed by reference
  - Passing the function a reference to where the variable memory is stored and changing the memory
  
## Nested Arrays
  ```JavaScript
    let nums = [[1,2], [3,4], [5,6]]
    console.log(nums[1][0])
    // 3
  ```

# Objects

## Creating Object Literals
  - Objects can be assigned to variables
  - We use curly braces {} to designate an object literal
  ```JavaScript
    let spaceship = {}
  ```
  - Fill an object with unordered data that is organized into key-value pairs.
  - Make a key-value pair by writing the key’s name(identifiers) followed by a colon and the value
  - We separate each key-value pair in an object literal with a comma (,)
  - Keys are strings, but when it doesn't have any special characters, omit the quotation marks
  ```JavaScript
    let spaceship = {
      'Fuel type': 'diesel',
      color: 'silver'
      'Active Mission': true,
      homePlanet: 'Earth',
      numCrew: 5
    }
```

## Accessing Properties
  - Two ways to access properties
 
  - Dot notation (1)
  - Name of object followed by a . and then property name (key)
  
  - Bracket notation (2)
  - Pass in the property name (key) as a string
  - Must use bracket notation when accessing keys that have numbers, spaces, or special characters

  ```JavaScript
    spaceship.color //returns 'silver'
    let propName = 'Active Mission'
    spaceship[propName] // returns true
  ```
  
## Property Assignment
  - Objects are mutable
  - Can use dot or bracket notation and = to add new key-value pairs
  - If the property already exists, the new value will override the existing one
  - If the property does not exist, it will be added with the new value

  ```JavaScript
    spaceship.color = 'purple'
    spaceship.numEngines = 3
    delete spaceship['Active Mission']
  ```
  
## Methods
  - A function stored in an object is called a method
  - For example, .log() is a method for the console object
  - Two ways to create methods
  
  ```JavaScript
    const alienShip = {
      // 1: key value pair
      invade: function() {
        console.log('Take me to your leader!')
      },
      // Can omit the function keyword and the semi colon
      invade () {
        console.log('Take me to your leader!')
      }
  ```
  
## Nested Objects 
  ```JavaScript
    const spaceship = {
      passengers: null,
      crew: {
        captain: {
          name: 'Sam', 
          degree: 'Computer Science', 
          encourageTeam() { console.log('We got this!') },
          'favorite foods': ['cookies', 'cakes', 'candy', 'spinach']
        }
      },
      engine: {
        model: 'Nimbus2000'
      },
      nanoelectronics: {
        computer: {
          terabytes: 100,
          monitors: 'HD'
        },
        'back-up': {
           battery: 'Lithium',
           terabytes: 50
         }
      }, 
      telescope: {
        yearBuilt: 2018,
        model: '91031-XLT',
        focalLength: 2032 
      }
    }    
    
    let capFave = spaceship.crew.captain['favorite foods'][0] //cookies
    spaceship.passengers = [{name: 'bob'}, {name: 'joe'}]
    let firstPassenger = spaceship.passengers[0] //{name: 'bob'}
  ```      

## Pass by Reference
  - Objects are passed by reference 
  - Points to the space in memory holding that object       

## Looping Through Objects
  - 'for...in' will execute a given block of code for each property in an object
  - In each iteration, the variable is set to one of the objects‘s keys

  ```JavaScript
    for(let member in spaceship.crew){
      console.log(`${member}: ${spaceship.crew[member].name}`) // captain: Sam
      console.log(`${spaceship.crew[member].name}: ${spaceship.crew[member].degree}`) // Sam: Computer Science
    }
  ```

# Advanced Objects 

## This Keyword
  - The 'this' keyword references the calling object which provides access to the calling object’s properties

  ```JavaScript
    const robot = {
      model: '1E78V2',
      energyLevel: 100,
      provideInfo() {
        return (`I am ${this.model} and my current energy level is ${this.energyLevel}`)
      }
    };
  ```
    
## Arrow Functions and this Keyword
  - Avoid using arrow functions with the 'this' keyword in objects
  - Arrow functions inherently bind an already defined 'this' value to the function itself that is NOT the calling object
  - The value of this is the global object that doesn’t have a getName property and returns undefined
    - A global object is an object that always exists in the global scope
    - Scripts running under Node.js have an object called 'global' as their global object. 

  ```JavaScript
    const obj = {
      name: 'Sam',
      getName: () => {
        console.log('Hello, my name is ' + this.name)
      }
    }
    // Hello, my name is undefined
  ```

## Privacy 
  - JavaScript does not have built in privacy for objects
  - Popular naming convention is to place an "_" before the name of a property
  - They can still be manipulated, even thought they are intended to not be      
    
  ```JavaScript
    const robot = {
      _energyLevel: 100
    }
    robot._energyLevel = 95 // not supposed to change, but technically still can
  ```
  
## Getters
  - Getters are methods that get and return the internal properties of an object
  - In a getter, we can access the properties of the calling object using 'this'
  - Getters can return different values using conditionals
  - Properties cannot share the same name as getters and setters

  ```JavaScript
    const robot = {
      _model: '325483',
      _energyLevel: 95,
      get energyLevel() {
        if (typeof(this._energyLevel) === 'number'){
          return `My current energy level is ${this._energyLevel}`
        } else {
          return 'System malfunction: cannot retrieve energy level'
        }
      }
    };
    console.log(robot.energyLevel) // notice we do not use parenthesis when calling getter
  ```

## Setters
  - Setter methods can reassign values of existing properties in an object
  - Setters don't need to be called parentheses. Looks like we’re reassigning the value of a property

  ```JavaScript
    const robot = {
      _model: '325483',
      _energyLevel: 95,
      get energyLevel() {
        if (typeof(this._energyLevel) === 'number'){
          return `My current energy level is ${this._energyLevel}`
        } else {
          return 'System malfunction: cannot retrieve energy level'
        }
      },
      set energyLevel(lvl) {
        if (typeof(lvl) === 'number' && lvl >= 0) {
          this._energyLevel = lvl
        } else {
          console.log('Enter a number greater than or equal to 0')
        }
      }
    };
    robot.energyLevel = 50  // notice we do not use parenthesis when calling getter
    console.log(robot.energyLevel) // 50
  ```

## Factory Functions


    
      

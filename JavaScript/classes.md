# Classes

## Constructor
  - JS calls the constructor() method every time it creates a new instance of a class
  
  ```JavaScript
    class intern {
      constructor(name, department) {
        this._name = name;
        this._department = department;
      }
    }
  ```
  
## Instance
  - An instance is an object that contains the property / methods of a class, but with unique property values
  
  ```JavaScript
    // creates an instance of 'intern' class
    const internSam = new intern('Sam', 'BI');
  ```
  
## Methods
  - Class method and getter syntax is the same as objects except you can not include commas between methods
  
  ```JavaScript
    class intern {
      constructor(name, department) {
        this._name = name;
        this._department = department;
        this._vacationDays = 10;
      }
      // notice no commans between methods
      get name() {
        return this._name;
      }
      
      get department() {
        return this._department;
      }
      
      get vacationDays() {
        return this._vacationDays;
      }
      
      takeDaysOff(days) {
        this._vacationDays -= days;
      }
    }
  ```
  
## Method Calls
  - Syntax for calling methods and getters on an instance is the same an object
  
  ```JavaScript 
    const internSam = new intern('Sam', 'IT');
    console.log(internSam.name); // 'Sam'
    internSam.takeDaysOff(3);
    console.log(internSam.vacationDays); // 7
  ```

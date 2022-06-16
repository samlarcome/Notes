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
  
## Inheritance
  - When multiple classes share properties or methods, they become candidates for inheritance
  - Create a parent class (aka superclass) w/ properties and methods that multiple child classes (aka subclasses) share
  - Child classes inherit properties and methods from their parent class

  ```JavaScript
    class HospitalEmployee {
      constructor(name){
        this._name = name;
        this._remainingVacationDays = 20;
      }
      get name() {
        return this._name;
      }
      get remainingVacationDays() {
        return this._remainingVacationDays;
      }
      takeVacationDays(daysOff){
        this._remainingVacationDays -= daysOff;
      }
    }
  ```
    
  - Now that we have parent class, we can extend them to the subclasses
  - 'extends' keyword makes the methods of parent class available inside the subclasses
  - 'super' keyword calls the constructor of the parent class
  - MUST always call super method before you can use the 'this' keyword (reference error if you don't)
  - Best practice to call super on the first line of subclass constructors
  
  ```JavaScript
    class Nurse extends HospitalEmployee {
      constructor(name, certifications) {
        super(name);
        this._certifications = certifications;
      }
    }
    const nurseSam = new Nurse('Sam', ['Trauma', 'Pediatrics']);
    console.log(nurseSam.name); //'Sam'
    console.log(nurseSam.remainingVacationDays); // 20
  ```

  - When we call extends in a class declaration, all of the parent methods are available to the child class

  ```JavaScript
    nurseSam.takeVacationDays(9);
    console.log(nurseSam.remainingVacationDays()); // 11
  ```
  
  - Child classes can also contain their own properties, getters, setters, and methods
  
  ```JavaScript
    class Nurse extends HospitalEmployee {
      constructor(name, certifications) {
        super(name);
        this._certifications = certifications;
      }
      get certifications() {
        return this._certifications;
      }
      addCertification(newCert) {
        this._certifications.push(newCert);
      }
    }
    const nurseSam = new Nurse('Sam', ['Trauma', 'Pediatrics']);
    nurseSam.addCertifications('Anx');
    console.log(nurseSam.certifications); // ['Trauma', 'Pediatrics', 'Anx']
  ```
  
## Static Methods
  - When we want a class to have methods that aren’t available in individual instances, but can be called directly from the class
  - The class itself must call static methods, not the instances of that class

  ```JavaScript
    class HospitalEmployee {
      constructor(name){
        this._name = name;
        this._remainingVacationDays = 20;
      }
      ...
      static generatePassword() {
        return Math.floor(Math.random() * 100001);
      }
    }
    console.log(HospitalEmployee.generatePassword()); // returns a random number
    console.log(nurseSam.generatePassword()); // TypeError
  ```




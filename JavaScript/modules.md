# Modules

## What are Modules?
  - Modules are reusable pieces of code in a file that can be exported and then imported for use in another file

## Node.js vs ES6
  - Two different runtime environments and each has their preferred module implementation
  - Node: module.exports and the require() syntax
  - ES6: import/export syntax

## ES6 Named Export Syntax
  - Name of each exported resource is listed between {} and separated by commas
  ```JavaScript
    //modules.js
    export { somethingToExport1, somethingToExport2, ...};
  ```
  - Individual resources can be exported by placing the keyword before the variable declaration
  ```JavaScript
    export const somethingToExport1 = (param) => {
      // does something
    }
  ```
  
## ES6 Import Syntax
  - Similar to export syntax
  ```JavaScript
    //testing.js
    import {somethingToExport1, somethingToExport2, ...} from './modules.js';
  ```
  - Must include 'type' attribute in script element if the script that is linked depends on modules
  ```HTML
    <script type="module" src="./testing.js"> </script>
  ```
  
## Renaming Imports to Avoid Collisions
  - Resource you import may have same name as some other variable in current code
  ```JavaScript
    import {doSomething as task1} from './modules1'
    import {doSomething as task2} from './modules2'
  ```
  
## Default Exports and Imports
  - Every module also has the option to export a single value to represent the entire module called the default export
  - Default export value is often an object containing the entire set of functions / data values of a module
  ```JavaScript
    const resources = {
      resource1,
      resource2
    }
    export {resources as default};
    // or shorthand syntax
    export default resources;
  ```
  
## Importing Default Values
  ```JavaScript
    import { default as resources } from 'module.js
    // or the shorthand
    import resources from './modules.js'
  ```
  - Important to note if the exported resource is an object, it needs to be imported before being extracted
  ```JavaScript
    // Works
    import resources from 'module.js'
    const { valueA, valueB } = resources;

    // Doesn't Work
    import { valueA, valueB } from 'module.js'
  ```
    
  

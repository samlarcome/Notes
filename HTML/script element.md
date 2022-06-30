# JavaScript and the DOM

# The <script> tag
  - The <script> tag allows you to add JavaScript inside an HTML file
  - Has an opening and closing tag (<script> </script>)
  - Use to embed valid JS code
  
  ```HTML
    <script>
      function example() {
        var image = document.getImageById('myImage');
        // do something
      }
    </script>
  ```
  
# The src attribute
  - We want to write code in a separate file, and reference it with a file path name
  - This is preferable
  - Done with the src attribute
  - Can link code that is hosted externally or in a Content Delivery Network
  
  ```html
    <script src="./example.js"></script>
  ```
  
# How scripts are loaded
  - Browsers are equipped with HTML parsers that render the elements
  - By default they are parsed in the order they appear in html 
  - When the parser finds a script tag, it loads and executes the code in the Js file
  
  - The parser does not process next element until it finishes loading and executing the script
    - Can lead to a delay time and poor experience
  - Scripts are also loaded sequentially (if one relies on another, that one should be loaded first)
 
  
# Defer attribute
  - Defer specifies scripts that should be executed after the HTML file is completely parsed
  - It will load the script, but defers the execution until it finishes parsing rest of html file
  
  ```html
    <script src="./example.js" defer></script>
  ```
  - It is useful when a script contains functionality that requires interaction with the DOM
  - Ensures entire files is parsed before executing script
  
# Async Attribute
  - Loads and executes the script asynchronously with the rest of the webpage
  - Parser will continue to parse rest of html file as the script is being downloaded in the background (similar to defer)
  - Script will run immediately after it is downloaded (unlike defer)
  
  ```html
    <script src="./example.js" async></script>
  ```
  - Useful for scripts that run independently of other scripts (does not matter when the script is run)
  - Most suitable option as it optimizes web page loading time
  

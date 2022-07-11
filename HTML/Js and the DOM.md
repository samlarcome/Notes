#  JavaScript and the DOM

## The Document Keyword
  - The 'document' object allows you to access the root node of the DOM tree
  - Before you can access any element, you must access the document structure itself
  - 'document' object allows you to access the children of the DOM as properties
    - ex: document.body 

## Tweaking Elements
  - When accessing an element through the DOM, you also have access to all of its properties
  - This means modifying the contents, as well as the attributes and properties
  ```JavaScript
    document.body.innerHTML = '<h1>Adding a heading</h1>'
  ```
  - The '.innerHTML' property allows you to access and set the contents of an element
  - Can also add any valid HTML elements

## Select and Modify Elements
  - The DOM allows us to select and edit elements with CSS selectors (tag name, class, id)
  - '.querySelector()' takes a CSS selector as a string and returns the first element with that selector
  - 'getElementById()' accesses an element directly by its id
  - 'getElementByClassName()' returns an array of elements
  - 'getElementByTagName()' returns an array of elements
  ```JavaScript
    document.getElementById('test').innerHTML = 'Hello World!';
    document.getElementsByClassName('tests')[0].innerHTML = 'foo bar';
  ```

## Style and Element
  - The '.style' property provides access to the element's inline style
  - element.style.property where the property = a CSS property
  ```JavaScript
    document.body.style.backgroundColor = 'blue';
  ```
  - Notice there is no hyphen (-) like there would be in CSS (background-color)
  
## Traversing the DOM
  - Each element has a '.parentNode' property and a '.children' property
    - The document element does not have a parent node (null)
  - '.children' will return an array of an elements children, if none it returns null
  ```JavaScript
    let one = document.body.children[0];
    one.parent.style.backgroundColor = blue;
  ```

## Create and Insert Elements
  - 'createElement()' method creates an element based on the tag that is passed to it
  - Creates an empty element with no inner HTML in it
  - Can assign values to properties of new HTML element
  - In order to add a new element to the webpage, you must assign it to be a child of an already existing element in DOM
  - Process is called appending which is done with '.appendChild()' method
  ```JavaScript
    let test = document.createElement('li');
    test.id = 'test';
    test.innerHTML = 'testing';
    document.querySelector('ul').appendChild(test);
  ```
  
## Remove an Element
  - '.removeChild()' removes a specified child from a parent
  ```JavaScript
    let par = document.querySelector('p');
    document.body.removeChild(par);
  ```
  - Can also hide an element rather than removing it by setting the hidden property to true
  ```JavaScript
    document.getElementById('test').hidden = true;
  ```

## Add Click Interactivity
  - Can interactivity to DOM elements by having a fxn run based on an event
  - An event can include anything from a click to a user hovering over something
  - The '.onclick' property allows you to assign a fxn to run when an element is clicked
  ```JavaScript
    element.onclick = function() {
      element.style.backgroundColor = 'red';
    };
  ```
  - Can also assign the onclick property to a fxn by name
  ```JavaScript
    function turnRed {
      element.style.backgroundColor = 'red';
    }
    element.onclick = turnRed;
  ```

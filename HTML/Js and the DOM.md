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

## Create and Insert Elements
  - 'createElement()' method creates an element based on the tag that is passed to it
  - Creates an empty element with no inner HTML in it
  - 

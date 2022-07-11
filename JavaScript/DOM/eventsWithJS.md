# DOM Events with JS

## What are Events?
  - User interactions and browser manipulations that you program to trigger functionality
  - When user performs action, they are causing event to be 'fired' or 'triggered'

## Firing Events
  - After a specific event fires on a specific element, an event handler function can be created as a response

## Event Handler Registration
  - '.addEventListener()' lets a DOM element *listen* for a specific event and execute a block of code when event is detected
  - *event target* = the DOM element that listens for an event
  - *event handler* = block of code that runs when the event fires

  ```JavaScript
    function eventHandlerFunction() {
      // executes when event is fired
    }
    
    eventTarget.addEventListener('click', eventHandlerFunction);
  ```
  
## Adding Event Handlers
  - Event handlers can also be created setting the 'onevent' property on a DOM element/event target
  - Append an element with '.on' followed by lowercase event type name:
  ```JavaScript
    eventTarget.onclick = eventHandlerFunction;
  ```
  - '.onevent' can only attach one event handler function to the event target
  - '.addEventListener()' allows for multiple event handlers

## Removing Event Handlers
  - '.removeEventHandler()' stops the event target from *listening* for an event to fire when it no longer needs to
  - Takes event as a string (1) and the event handler function (2) as parameters
  - If an anonymous fxn was used as an event handler fxn, it cannot be undone
  
  ```JavaScript
    button = document.findElementById('example'); // target element
    function eventHandlerFxn() {
      // does something
      button.removeEventListener('click', eventHandlerFxn);
    }
    button.addEventListener('click', eventHandlerFxn);
  ```
  
## Event Object Properties
  - JS stores events as objects, related data and functionalities as properties and methods
  - When triggered, an event object can be passed as an argument to the event handler function
  - A few predetermind properties:
      - '.target' = the element that the event is registered to
      - '.type' = the name of the event
      - '.timeStamp' = number of milliseconds that passed since the document loaded and the event was triggered
  ```JavaScript
    let btn = document.querySelector('button');
    function eventHandlerFxn(event){
      event.target.style.backgroundColor = 'red';
      console.log(event.timeStamp);
    }
    btn.addEventListener('click', eventHandlerFxn);
  ```
  
## Event Types
  - There are more than just 'click' events
  - Most events in the DOM take place without being noticed because there is no event handler connected to them
  - Some events do not rely on user interaction (ex. 'load')
  
  ```JavaScript
    let btn = document.querySelector('button');
    function eventHandlerFxn(event){
      event.target.style.backgroundColor = 'purple';
    }
    btn.onwheel = eventHandlerFxn;
  ```

## Mouse Events
  - 'click' and 'wheel' are both mouse events
  - 'mousedown' = fires when user presses mouse down (doesn't require release) 
  - 'mouseup' = fires when user releases mouse button
  - 'mouseover' = fires when mouse enters content of an element
  - 'mouseout' = fires when mouse leaves content of an element
  
## Keyboard Events
  - Keyboard events are triggered by user interaction with the keyboard (duh)
  - 'keydown' = fired when user presses down on a key
  - 'keyup' = is fired when user releases a key
  - 'keypress' = fired when user presses down on a key AND releases it
  - Keyboard events have unique properties like '.key' that stores value of key pressed

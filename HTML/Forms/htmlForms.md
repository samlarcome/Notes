# HTML Forms

## How a Form Works
  - Computers need HTTP request to know how to communicate
  - HTTP instructs computer how to handle incoming information
  - <form> element is a great tool for collecting information
  - Need to supply <form> with both the location of where the information is supposed to go, and what HTTP request to make
  
  ```html
    <form action = "./example.html" method = "POST">
      <h1>This is a form</h1>
    </form>
  ```
  - 'action' attribute determines where information is sent
  - 'method' attribute is assigned an HTTP verb that is included in the HTTP request
  
## Text Inputs
  - Use the '<input>' element to create an input field in form
  - '<input>' has an attribute 'type' that determines how it is rendered
  - The default for 'type' is 'text'
  - We also need to include the 'name' attribute or that information won't be sent when the form is submitted
  ```HTML
    <form action="./example.html" method="POST">
      <input type="text" name="text-field" value="default value">
    </form>
  ```
  - What the user enters becomes the value of the 'value' attribute
  - The value of the 'name' attribute gets paired with the value of 'value' attribute
  - Can include default value for 'value' so the user sees a pre-filled text
  
## Adding a Label
  - Use the '<label>' tag for a user to identify an input
  - To associate the label with the input, the input tag needs a 'id' attribute
  - We then give the label tag a 'for' attribute with the value of the id from the input
  ```HTML
    <form action="./somewhere.html" method="POST">
      <label for="username">Enter a username:</label>
      <input type="text" name="username" id="username">
    </form>
  ```
  
## Password Input
  - We have the type="password" attribute
  - Will replace the input with (*) or (.)
  ```HTML
    <form action="" method="">
      <label for="password">Enter Password:</label>
      <input type="password" id="password" name="user-password">
  </form>
  ```
  - When submitted, it will be submitted as "user-password=example"
  
## Number Input
  - We have type="number" attribute
  - Restricts the input to numbers (and a few special characters +,-,.)
  - Can add a 'step' attribute that adds arrows and increases/decreases input by value of attribute
  ```HTML
    <form action="" method="">
      <label for="num"></label>
      <input type="number" step="5" name="usr-num" id="num">
    </form>
  ```
  
## Range Input
  - Using type="range" creates a slider
  - To set a minimum and maximum, we assign values to 'min' and 'max' attributes
  - Can control how smooth the slider moves by assigning a value to 'step' attribute
  ```HTML
    <form action="" method="">
      <input type="range" name="example" id="example" step="0.5" min="0" max="5">
    </form>
  ```
  
## Checkbox Input
  - We have type="checkbox" attribute
  - Allows user to check multiple boxes
  ```HTML
    <form>
      <p>Burger Toppings</p>
      <label for="cheese">Cheese</label>
      <input type="checkbox" name="topping" id="cheese" value="cheese">
      <br>
      <label for="lettuce">Lettuce</label>
      <input type="checkbox" name="topping" id="lettuce" value="lettuce">
      <br>
      <label for="pickels">Pickels</label>
      <input type="checkbox" name="topping" id="pickels" value="pickels">
    </form>
  ```
  - Notice all inputs share the same name
  - They also all have the value attribute that is not visible on the page (that comes from the label)
  
## Radio Button Input
  - Present multiple options but only want the user to select on answer
  - 
  ```HTML
    <form action="" method="">
      <p>Select the right answer</p>
      <input type="radio" name="answer" id="a" value="a">
      <label for="a">A</label>
      <br>
      <input type="radio" name="answer" id="b" value="b">
      <label for="b">B</label>
    </form>
  ```
  
## Dropdown List
  - Allow users to choose one option out of a larger list of options
  ```HTML
    <form action="" method="">
      <label for="gamelist">Select a game</label>
      <select id="gamelist" name="game">
        <option value="cod">Call of Duty</option>
        <option value="eft">Escape from Tarkov</option>
        <option value="halo">Halo</option>
      </select>
    </form>
  ```
  - The value attribute is what is submitted, not the text that is rendered between the option tags
  
## Datalist Input
  - Datalist is similar to dropdown list, but the user can type into it inorder to filter the options
  - Used with an input type="text"
  - Input will now have a 'list' attribute
  - The value of the option selected, or the text the user types will be paired with the name and submitted
  ```HTML
    <form action="" method="">
      <label for="userSpot">Ideal Vacation Spot</label>
      <input type="text" name="spot" id="userSpot" list="spots">
      
      <datalist id="spots">
        <option value="Mexico"></option>
        <option value="France"></option>
        <option value="Bahamas"></option>
      </datalist>
    </form>
  ```

## Text Area Element
  - An input with type 'text' creates only a single row for user to enter input
  - <textarea> element is used to create a bigger text field that allows users to type more
  - Can add 'cols' and 'rows' attribute to determine size of text field
  ```HTML
    <form action="" method="">
      <label for="blogpost">New Post</label>
      <br>
      <textarea id="blogpost" name="blogpost" rows="5" cols="30">
        Can add default text area like such
      </textarea>
    </form>
  ```
  
## Submit Form
  - Need a button for user to submit information when they're done filling it out
  - Input type = "submit"
  - The value is what shows up as the text inside the button ('Submit' is the default text)
  
  ```HTML
    <form action="" method="">
      <input type="submit" value="send">
    </form>
  ```

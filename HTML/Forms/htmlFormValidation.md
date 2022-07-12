# Client Side Validation: HTML

## Requiring an Input
  - If we have a field that is not optional, we can add the 'required' attribute to an input
  
  ```HTML
    <form action="" method="">
      <label for="usersName"> Enter your name: </label>
      <input type="text" id="usersName" name="UsersName" required>
    </form>
  ```
  
## Set a Minimum and Maximum
  - Can check minimum and maximum for a number field (type = number or range)
  - Set the 'min' attribute and give it a value
  - Set the 'max' attribute and give it a value

  ```HTML
    <form action="/example.html" method="POST">
      <label for="age">Enter your age:</label>
      <input id="age" name="age" type="number" min="1" max="99">
      <input type="submit" value="Submit">
    </form>
  ```

## Checking Text Length
  - To set a minimum number of charcters, give the 'minlength' attribute a value
  - To set a maximmum number of characters, give the 'maxlength' attribute a value

  ```HTML
    <form action="" method="">
        <label for="pw">Password:</label>
        <br>
        <input id="pw" name="pw" type="password" required minlength="8" maxlength="15">
        <br>
        <input type="submit" value="Submit">
      </form>
  ```

## Matching a Pattern
  - Add validation to check how the text was provided
  - Use the 'pattern' attribute and assign it a regular expression (regex)
  - Regular expressions are a sequence of characters that make up a search pattern
  - If input matches the pattern, it can be submitted
  
  - pattern = "[0-9]{14,16}" would check that a min of 14 and max of 16 numbers are entered
  - pattern = "[a-zA-Z0-9]+" would check only letters and numbers are entered (no special characters)

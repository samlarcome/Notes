# Intro to Form Validation

## Introduction
  - User information (ie. usernames, passwords, credit card info, etc.) is traditionally collected through HTML forms
  - We need to make sure the information entered is valid *(form validation)*

## Why Validate Forms?
  - Most data is stored in a database on the server side
  - Repeated usernames, bad email addresses, making sure all data is collected is important
  - We also need to keep our forms protected (secure)
  - Don't want to expose someone's password or let hackers inject code

## Regular Expressions
  - Humans can easily recognize patterns/mistakes with addresses, zip codes, spelling 
  - To specify patterns for a computer, we use regex/regexp (regular expression)
  - A regular expression is a sequence of characters representing a pattern
  - Can use that pattern to match strings, parts of strings, confirm an acceptable format, or replace parts of a string

## Client Side Validation: HTML
  - Prevent problematic inputs from being inputted to begin with
  - Client = process interacting w/ server on user behalf (i.e. web browser)
  - No interaction with the backend required
  - Modern HTML provides some of these built in form validation:
    - Can make parts of form 'required' and some optional
    - Can set min and max values
    - Can set min and max lengths for text input
    - Can require an input match a particular pattern, specified by regex expression
  - If user doesn't meet the rules, they will receive a message explaining whu
  - Less likely that the database is sent incorrect information
  - Also providers the user with immediate feedback

## Client Side Validation: JavaScript
  - Catching mistakes earlier saves time and resources
  - Can validate with JS we write ourselves or with a JS library
  - Can use a simple library such as [Just Validate](https://www.npmjs.com/package/just-validate)
  - Could use [Formik](https://www.npmjs.com/package/formik) when working with React (that relies on virtual DOM)

## Back-end Validation
  - Validations must also be completed on the back end
  - Back-end validation has many advantages:
    - Use validation code that the user cannot see (and try to work around)
    - Validate data against info the front end does not have access to
  - Two main ways to validate on server side
  - (1) Takes place as the user is still inputting data
    - Make asynchronous requests to server with pieces of their data and send feedback directly to the user before they’ve submitted
    - This is slower than front end validation
  - (2) Once the form has been submitted
    - Last defense; verify the validity and safety of data before entering to database
    - Also allows us to sanitize the data (consistent formatting)     

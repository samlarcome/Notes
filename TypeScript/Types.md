# Typescript - Types

## From JavaScript to TypeScript
- Created by Microsoft, released in 2012
- TypeScript adds types to JavaScript
- Allows users to write JavaScript with a tool called *type stream*, which has advantages like
    - Spot bugs in code
    - Clarify the structure of code
    - Help refeactor our code
    

## What is TypeScript
- TypeScript files have a **.ts** extension
- Code gets run through the TypeScript transpiler
    - Checks that code adheres to TypeScript standards
    - Will display errors otherwise
- TypeScript transpiler will convert to working **.js** file, if possible

- TypeScript is a **superset** of JavaScript code
- The TypeScript compiler can be used by runnning the ```tsc``` command

## Type Interface
- JavaScript supports dynamic typing (like Python) which is nice for beginners
- TypeScript will not allow us to reassign a variable with a different type 
- *type interface*: TypeScript expects the data type of the variable to match the type we initially declared it to be
- TypeScript recognizes the primitive JS types:
    - **boolean, number, null, string, undefined**
```TypeScript
// type 'number' is not assignable to type 'string'
let order = 'first';
order = 1;

// fixed whenn new value is type 'string' as well
let order = 'first';
order = '1';
```

## Type Shapes
- As TypeScript knows what types objects are, it knows what shapes they adhere to
    - Shape of an object describes what methods and properties it contains, and some more
- The ```tsc``` command shows if your code accesses properties and methods that do not exist
```TypeScript
let name = 'Sam'
console.log(name.legnth)

// By running tsc in the terminal, we can see the property legnth does not exist for strings
// Property 'lenght' does not exist on type 'string'. Did you mean 'length'?
```

## Any
- When a variable is declared w/out an initial value, it is typically given a type of **any**
- Variables of type any can be assigned any value and TypeScript will not give an error if they are reassigned a different type
```TypeScript
let example;
example = 'string'csd
example = false;
// running the tsc command will not throw any errors
```

## Variable Type Annotations
- What if we want to declare something w/ initial value but not type of any?
- Using *type annotation*, we can tell TypeScript what type something is
- Add type annotations (or type declarations) after their names
```TypeScript
let phone: string;
if (true) {
    phone = '123-456-7890';
} else {
    phone = 1234567890;
}
// TS will throw an error, even though we never reach the else statemnet
```
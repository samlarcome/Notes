# Variables

## Declaring Variables
- Need two things to declare variables
    - Type
    - Name

```c++
#include <iostream>

int main() {
    int year;
    year = 2023;
    // or
    int year = 2023;

    std::cout << year << "\n";  // chaining
}
```

## User Input
- We can use `cin` to gather input (character input)
- Use the `>>` operator with character input
```c++
std::cout << "Enter your password:";
std::cin >> passowrd;
```

## Basic Data Types

```c++
int age = 21;
double price = 4.20;
char grade = 'A';
std::string name = "Sam Larcome";   // sequence of characters
bool tired = true;

const double quarter = 0.25; // constant that cannot be changed by program at execution
```

### Data Type Modifiers
- Used with built in data types to modify the length of data that a particular data type can hold
    - unsigned
    - signed
    - short
    - long

### Type Conversion
- A type cast converts from one type to another
```c++
double weight1 = 193.43;
int weight2;

weight2 = (int) weight1; // going from double to int simply remvoes decimal: 193
```
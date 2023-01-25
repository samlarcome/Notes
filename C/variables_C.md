# Variables
- The main datatypes in C are:
    - int
    - float
    - double
    - char

```C
#include <stdio.h>

int main() {
    int wholeNum = 3;       // whole number
    float decimal;      // a number with 6 possible decimals
    double decimal;     // a number with 15 possible decimal places
    char letter = 'a';        // stores one character (letter or number)
    char num = '7'          // '70' would not be a valid char
}
```

## Printing
- printf can take additional paramters to add values dynamically into the string
    - ``%d`` or ``%i`` for int
    - ``%f`` for double or float
    - ``%c`` for char
    - ``%s`` for string
```C
#include <stdio.h>

int main() {
   printf("I am %d years old today", 21);
}
```

## Float vs. Double
- ``Float`` (6 decimals) has less precision than a ``double`` (15 decimals)
    - Float takes up 4 bytes in memory
    - Double takes up 8 bytes in memory

## Constants
- Cases where you do not want to change the value of a variable
- Best practice to name constants with all capital letters
```
const type VARIABLE_NAME
```

## Casting types
- There are two types of conversions
    - explict
    - implicit

```C
int a;
double b = 3.0;
a = b;              // implicit: compiler will make a best guess

double d = 2.7;
int i = (int)d;     // explicit --- i = 2
```


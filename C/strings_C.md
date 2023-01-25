# Strings in C
- In C, a string is an ```array of chars``` and is subject to properties and methods associated with arrays

## Creating and Initializing Strings
Two ways to create an intialized string
```C
char string[] = {'H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd', '\0'};
```
- The very last character in the array is known as the ```null terminating character```  
    - Signifies the end of the string and must be included when creating a string as an initialized array
    - "Hello World" has **11 characters** but the **size of string[] is 12!**
        - Plus one for the null terminating character  
  

The second way to create a string:
```C
char string[] = "Hello World";

printf("%s\n", string);     // use %s to print strings
```
- The **null terminating character** is added implicitly
    - The size of the array is still 12

## Character Access and Modification
```C
char string[] = "Compoter";

printf("", string[4]); // accessing the 5th character

string[4] = 'u';    // modifying the 4th character
```

## Looping through Strings
```C
#include <string.h>     // library includes 'strlen()' function

char string[] = "Hello World";

for(int i = 0; i < strlen(string); i++) {
    printf("%c", string[i]);
}
```

## Concatenating Strings
- Can concatenate two strings with the **strcat()** in the **string.h** library

```C
#include <string.h>     // library includes the 'strcat' function

char string1[] = "abcd";
char string2[] = "efgh";
strcat(string1, string2);       // strcat(destination, source)

printf("%s", string1); 
// output will be 'abcdefgh'
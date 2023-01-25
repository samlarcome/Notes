# Hello World
```C
#include <stdio.h>  // standard input and ouput library

int main() {
    printf("Hello World!\n")
}
```

## Comments
```C
// single line comments

/*
Multi
Line
Comment
*/
```

## Compiling
- Widely used C compiler is ```gcc``` which stands for GNU Compiler Collection

- The ```-o``` flag allows you to name executable
- If not executable name provided, default is ```a.out```
```
gcc helloWorld.c -o helloWorld
./helloWorld
```
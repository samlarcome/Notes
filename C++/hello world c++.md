# Introduction to C++
- Created in 1979 to add object oriented programming to C language
- It is fast and flexible
- It is well-supported

# Hello World!
```c++
#include <iostream> // include libraries

int main() {
    std::cout << "Hello World!";
    return 0;
}
```
- `#include` is a preprocessor directive. It instructs compiler to locate the file that contains that code
- `std::cout` is the character output stream, sends the output to the terminal
- `<<` is an operator 
- Every c++ program must have a function called `main`

# Compile
- There are usually 4 steps with C++
    - Code -> Save -> Compile -> Execute

- Compiler will translate C++ code into machine code
- Compile by using the `g++` command, followed by file name
    - An executable named `a.out` will be produced
- To execute the machine code file, use `./a.out`

- There is an option to naming executables as well, instead of a.out
- The `-o` flag, followed by a name, allows us to name executable files
    - `g++ helloworld.cpp -o hw`
    - `./hw` can then be used to execute machine code
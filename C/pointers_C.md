# Pointers
- In C, a byte of memory can be accessed using a **pointer**
- A pointer containing the address of a variale is said to "**point**" to that variable

- When you create a variable, a **contiguous block of bytes is reserved in memory**
- A pointer to a variable is the **address of the first of these bytes**
- Pointer is created for both primitive data types and custom data types
    - Primitive
        - int, char, double
    - Custom
        - structs
  
Syntax:  
- dataType* nameOfPointer;  
    OR  
- dataType *nameOfPointer;

```C
int* ptr;   // pointer to an int
int *ptr;   // same as above
```
- **ptr** stores the addres of the first byte of block of memory containing an int

```C
int x;  
int* ptr = &x;  //pointer to that int

printf("%p\n", ptr) // use %p to print something of type pointer... outputs hexidecimal address (or (nil))
```

## The Reference Operator
- We can obtain the address of a variable with **reference** operator  
- ```&variable```
```C
int x = 12;
printf("%p", &x);   // prints address

int y = 100;
int* ptr = &y;  // declare a pointer to an int variable and assign address of int y
```

## The Dereference Operator
- We eventually need access data contained in the address of a variable
- Use the * as the dereference operator

```C
int x = 4;
int* ptr = &x;

int y = *ptr;
printf("%d", y)   // prints 4
```

- If the value of the dereferenced pointer is changed, the value of the corresponding variable will change in the same way

```C
int x = 4;
int* ptr = &x;

*ptr = 200; // the data in the memory address pointed to ptr now contains the value 200

printf("%d", x);    // prints 200
```

## Pointer Arithmetic
- The only arithmetic operations allowed for pointers are **addition and subtraction**
- Adding/subtracting to a pointer means the pointer will point to some new memory address
- You can only add an **integer** to a pointer
    - You cannot add two pointers together

```C
pointer = pointer + n;
pointer += n;
```

- Adding **n** to a pointer does NOT increment to an address **n bytes** away
- Moves the pointer by **n x (size of the data type in bytes)**
    - We have a pointer that points to an int (4 bytes) at memory address 100 
    - If we add 3 to the pointer, it now points to memory address 112 
        - 100 + (3 * 4 bytes)

```C
int* ptr;
ptr += 3;
```

## Pointers and Arrays
- If we have an integer array, we can use pointers and pointers arithmetic to iterate through array to access or manipulate its values
- Pointers are contiguous blocks of memory
    - we can use pointer arithmetic to access the rest of the array
    - unsafe but valid

```C
int arr[5] = {1,2,3,4,5};
int* ptr = &arr[0];         // poinis to first element in array

// prints all elements of arrays
for(int i = 0; i < sizeof(arr)/sizeof(int); i++) {
    printf("%i\n", *ptr);
    ptr += 1;
}

// how to change the values of of an array
for(int i = 0; i < sizeof(arr)/sizeof(int); i++) {
    *ptr = 3;
    ptr += 1;
}
```
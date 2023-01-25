# Structs
## Defining Structures
- **struct** keyword initiates the structure type definition
- Person is the name of the structure type
- Inside the braces are the member variables that are packaged together
    - can be any basic types
    - can also be derived types (arrays, pointers, structures)
```C
struct Person {
    char firstName[25];
    int age;
}
```

## Initializing Structures

```C
struct Bottle {
  char* name;
  int maxCapacity;
  int currentCapacity;
};
 
struct Bottle bottle1 = {"superBottle", 24, 0};     // initializes a struct in ordered notation

// use dot notation if we do not want to initialize in order
struct Bottle bottle2 = {
    .naxCapacity = 24,
    .name = "superBottle",
    .currentCapacity = 0
};
```

## Structure Dot Notation
- How we can access each member variable individually using dot notation
- Allows access and modify a member variable of a structure
```C
struct Bottle {
  char* name;
  int maxCapacity;
  int currentCapacity;
};
 
struct Bottle myBottle = {"Medium Bottle", 24, 0};
 
// Fill some of myBottle
myBottle.currentCapacity = 10;
printf("The bottle is now filled to %d", myBottle.currentCapacity);
```
- Can also use the dot structure to initialize a structure if you'd like to declare it with out initializing it right away
```C
struct Bottle myBottle;
myBottle.name = "Medium Bottle";
myBottle.maxCapacity = 24;
myBottle.currentCapacity = 0;
```

## Structure Pointers
- Structures can use a lot of memory
- Can use pointers to manage memory
    - holds memeory address to another variable
- Accomplished by defining the structure variable and then defining a pointer and assigning it the address to the structure variable
```C
struct Person person1 = {"Bob Smith", 21};
struct Person* personPointer = &person1;
```
- personPointer holds the memory address pointing to person1
- To access member variables we can use the following dot operator syntax
    - Use * to dereference the address to access the variable it points to
    - Make sure to wrap in parenthesis ()
```C
(*personPointer).name;
(*personPointer).age;
```
- Could also use arrow notation can be used with pointers to structures
    - it implicitly does the dereferencing
```C
personPointer->name;
personPointer->age;
```

## Structures in Functions
- Can specify structures and pointers to structures as parameters to functions
```C
void myFunction(struct Person p, struct Person* pPointer){};
```

- When passing a structure to a function
    - A copy of the structure is made so memory usage is a concern
    - any modifications made to the structures will not affect the original struct, only the copy

- When passing a pointer to a structure
    - because the pointer is the address of the original structure any modifications to the member variables will affect the original structure

```C
void personFunction(struct Person p, struct Person* pPointer){
  p.name = "Bob Smith";
  p.age = 21;
  pPointer->name = "Smith Bob";
  bPointer->maxCapacity = 22;    
}
 
int main(){
  struct Person p1 = {"Bob Jones", 24};
  struct Person p2 = {"Jone Bobs", 35};
 
  personFunction(b1, &b2);
}
```
# Functions

## Functions with Pointers
- Up to now, when a function receives an argument, the function makes a copy of the argument's value and stores it in the parameter variable
- What if we want to alter the variable inside the function?
    - We can pass a pointer to the variable that holds the memory address of the variable we want to modify
- Need to make sure the parameter type matches the type of pointer we are passing

```C
void myFunc(int* a){
  *a = *a+2;
  printf("a inside myFunc(): %d\n", *a);
}
 
int main(){
  int a = 10;
  int* aPointer = &a;
  myFunc(aPointer);
  printf("a in main(): %d\n", a);
}
 
//OUTPUT:
// a inside myFunc(): 12;
// a in main(): 12;
```

```C
void incrementAge(int* agePointer) {
  *agePointer += 1;
}

int main(void) {
  int age = 21;
  incrementAge(&age);
  printf("%d", age);
}
```
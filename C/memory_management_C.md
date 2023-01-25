# Memory Management
- Memory is used to store relevant variables and other data
- C offers a programmer access to memory with little restrictions


## Memory Allocation
- A **stack** is a section of memory that is highly ordered and data stored on the stack are only available within a certain scope
- The **heap** is not as orderd as the stack

- When creating a variable, you are statically allocation memory and it is stored on the stack
    - memory released when variable is no longer needed

- The heap allows you to reserve as much memory as you want and it will remain available until you **explicity** release it
    - Known as **dynamically** allocation memory
    - Forgetting to release dynamically allocated memory will cause a **memory-leak**

- C provides 4 special functions
    - malloc()
        - use this function to reserve as many bytes as you want on the heap
    - calloc()
        - Use this function to reserve memory for some number of ints, doubles, or any other data types
    - realloc()
        - use this function to expand or contrast a block of reserved memory (reserved by either mallac() or calloc())
    - free()
        - release previously allocated mempory
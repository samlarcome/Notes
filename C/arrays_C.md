# Arrays

## Creating and Initializing Arrays
- Can create an initialized and unititalized array

```C
int age[4]; // uninitialized array of 4 integers

int age[] = {1, 2, 3, 4};   // intialized array [1, 2, 3, 4]
```

## Accessing and Modifying Array Elements
```C
int arr[] = {1, 2, 3, 4};

int three = arr[2];     // accessing array element
arr[2] = 3;             // modifying an element
```

## Looping through Arrays
```C
int arr[100];

for(int i = 0; i < 100; i++) {
    arr[i] = i + 2;
}
```

## Length of Array Using sizeof()
- The ```sizeof()``` function returns the size of the array in ```bytes```
```C
int bytes = sizeof(arr);
```
- To find size of array, we must divide size of array by size of data type stored in array
```C
double arr[] = {1.0, 2.0, 3.0};
int length = sizeof(arr)/sizeof(double);

for(int i = 0; i < length; i ++) {
    printf("%f\n", arr[i]);
}
```

## Multi-dimensional Array
- Can create an initialized and unititalized multi-dimensional array similar to normal array

```C
int arr[4][4];  // unintialized 4x4 array  of integers

int matrix[][3] = {{1,2,3}, {1,2,3}, {1,2,3}};  // initialized 3x3 array

printf("%d\n", matrix[2][1]);   // print element in 3rd row and 2nd column

// iterating over a matrix
for(int i = 0; i < sizeof(matrix)/sizeof(matrix[0]); i++) {
    for(int j = 0; sizeof(matrix[0])/sizeof(int); j++) {

    }
}

```
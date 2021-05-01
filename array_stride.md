## STRIDING AN ARRAY
To avoid using an array of arrays
(or a vector of vectors, or a pointer to an array of pointers)

You can use a 1d array as if it were a 2d array.

This creates a single, contiguous block of memory which is much less taxing computationally. This allows us to properly affect subsets of the array.

This is especially useful when allocating memory to the heap.

## PROGRAMMING LANGUAGES

### C
```c
#include <stdlib.h>
#include <stdio.h>

void arr_print(int* arr, int rows, int cols, int stride){
  for(size_t i = 0; i < rows; i++){
    for(size_t j = 0; j < cols; j++){
      printf("%d, ", arr[i * stride + j]);
    }
    printf("\n");
  }
  printf("\n");
}

int main(int argc, char** argv){
#define ROWS 4
#define COLS 5

  //allocate an array on the heap
  int* arr = (int*) malloc(sizeof(int) * ROWS * COLS);

  //fill the array with increasing numbers from 0
  for(int i = 0; i < ROWS * COLS; i++){
    arr[i] = i;
  }

  //print whole array
  arr_print(arr, ROWS, COLS, COLS);

  //print subset of the array
  arr_print(arr, 3, 3, COLS);

  return EXIT_SUCCESS;
}
```

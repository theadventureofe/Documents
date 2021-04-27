## STRIDING AN ARRAY
To avoid using an array of arrays
(or a vector of vectors, or a pointer to an array of pointers)

You can use a 1d array as if it were a 2d array.

## PROGRAMMING LANGUAGES

### C
```c
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
  
  int arr[ROWS * COLS] = {0, 1, 2, 3, 4,
    10, 11, 12, 13, 14,
    20, 21, 22, 23, 24,
    30, 31, 32, 33, 34};
  
  arr_print(arr, ROWS, COLS, COLS);
  arr_print(arr, 3, 3, COLS);
  
  return EXIT_SUCCESS;
}
```

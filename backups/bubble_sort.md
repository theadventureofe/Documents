# BUBBLE SORT

## PROGRAMMING LANGUAGES

### C

```c
void swap(int *a, int *b){
  *a ^= *b ^= *a ^= *b;
}

void bubble_sort(int* arr, size_t n) {
  bool still_swapping = true;
  
  while(still_swapping){

    still_swapping = false;

    for (size_t i = 0; i < n - 1; i++){
      if (arr[i] > arr[i + 1]){
        swap(&arr[i], &arr[i+1]);
        still_swapping = true;
      }
    }
  }
}
```

### C++

```c++
void bubble_sort(std::vector<int>& a){
      bool still_swapping = true;
      while(still_swapping){
        still_swapping = false;
        for (size_t i = 0; i < a.size()-1; i++) {
            if (a[i]>a[i+1] ){
              std::swap(a[i], a[i+1]);
              still_swapping = true;
            }
        }
    }
}
```

### PYTHON

```python
def bubble_sort(arr):

    still_swapping = True
  
    while still_swapping:
        still_swapping = False
        for i in range(0, len(arr) - 1 ):
            if arr[i] > arr[i+1] :
                arr[i], arr[i+1] = arr[i+1], arr[i]
                still_swapping = True
```
### JAVASCRIPT

```javascript
const bubble_sort = (arr) => {
  let still_swapping = true;
  
  while(still_swapping) {
    still_swapping = false;
    
    for (let i = 0; i < arr.length; i++) {
          if (arr[i] > arr[i + 1]) {
              let tmp = arr[i];
              arr[i] = arr[i + 1];
              arr[i + 1] = tmp;
              still_swapping = true;
            }
        }
  }
}
```

### TYPESCRIPT

```typescript
const bubble_sort = (arr:number[]) => {
  let still_swapping:boolean = true;
  
  while(still_swapping) {
    still_swapping = false;
    
    for (let i = 0; i < arr.length; i++) {
          if (arr[i] > arr[i + 1]) {
              let tmp = arr[i];
              arr[i] = arr[i + 1];
              arr[i + 1] = tmp;
              still_swapping = true;
            }
        }
  }
}
```

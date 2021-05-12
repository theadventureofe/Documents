# TRIANGULAR NUMBERS
Triangular numbers can be arranged in an equilateral triangle

## SEQUENCE 
```
0, 1, 3, 6, 10, 15, 21, 28, 36, 45, 55, 66, 78, 91, 105, 120, 136, 153, 171, 190, 210, 231, 253, 276, 300, 325, 351, 378, 406, 435, 465, 496, 528, 561, 595, 630, 666...
```

## MODEL
```

               10
        6     8.9
   3   4.5   5.6.7
1 1.2 1.2.3 1.2.3.4
```

## PROGRAMMING LANGUAGES

### C
```C
int get_triangular(int n){
  return n * (n + 1 ) / 2;
}

int is_triangular(int n){

  if(n == 0 || n == 1) return 1;
  
  int sum = 0;
  for(int i = 0; i < n; i++){
    sum += i;

    if(sum == n){
      return 1;
    }
  }
  return 0;
}
```

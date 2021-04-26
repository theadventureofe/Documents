# FACTORS

## AlGORITHM FOR FINDING ALL FACTORS
A simple algorithm can be used to find all factors of a number. This guarantees
all factors are found. We will use the number 24 as an example. 

1. start with 1

![](https://latex.codecogs.com/gif.latex?%5Cbg_black%20%5CLARGE%2024%20%5Cdiv%201%20%3D%2024)

2. try each each other integer in order

![](https://latex.codecogs.com/gif.latex?%5Cbg_black%20%5CLARGE%20%5C%5C24%5Cdiv1%3D24%5C%5C24%5Cdiv2%3D12%5C%5C24%5Cdiv3%3D8%5C%5C24%5Cdiv4%3D6%5C%5C24%5Cdiv5%3D4.8)

3. remove any any numbers that do not divide exactly (like 5 in this example). 

![](https://latex.codecogs.com/gif.latex?%5Cbg_black%20%5CLARGE%20%5C%5C24%5Cdiv1%3D24%5C%5C24%5Cdiv2%3D12%5C%5C24%5Cdiv3%3D8%5C%5C24%5Cdiv4%3D6%5C%5C24%5Cdiv6%3D4)

4. Stop when you reach repeating numbers. (like "4×6" and "6×4" in this example)

5. All factors are now listed.

![](https://latex.codecogs.com/gif.latex?%5Cbg_black%20%5CLARGE%201%2C%202%2C%203%2C%204%2C%206%2C%208%2C%2012%2C%2024)
 
## PROGRAMMING LANGUAGES
``` c
void find_factors(int value){
  for(int i = 1; i <= value/2; i++){
    if(value % i == 0){
      printf("%d,", i);
    }
  }
  printf("%d \n", value);
}
```

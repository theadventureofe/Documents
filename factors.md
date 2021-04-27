# FACTORS

## DEFINITION

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

### C
``` c
void find_factors(int n){
  for(int i = 1; i <= n/2; i++){
    if(n % i == 0){
      printf("%d,", i);
    }
  }
  printf("%d \n", n);
}
```

### C++

``` c++
std::vector<int> find_factors(int n){
  std::vector<int> result;

  for(int i = 1; i <= n/2; i++){
    if(n % i == 0){
      result.push_back(i);
    }
  }
  
  result.push_back(n);
  return result;
}
```

## PRIME FACTORS
prime numbers are number that do not divide by anything other than itself and 1.
(it's only factors are itself an 1).
1 is not a prime number.

Any number can be broken down into a string of prime factors. 
this is called **prime factor decomposition** or **prime factorisation**


## ALGORITHM FOR FINDING PRIME FACTORS

we will use the number 420 as an example.

1. split the number into 2 factors

![](https://latex.codecogs.com/gif.latex?%5Cbg_black%20%5CLARGE%20420%20%3D%2042%20%5Ctimes%2010)

2. if any number is not prime, split the results again

![](https://latex.codecogs.com/gif.latex?%5Cbg_black%20%5CLARGE%2042%20%3D%207%20%5Ctimes%206)

![](https://latex.codecogs.com/gif.latex?%5Cbg_black%20%5CLARGE%2010%20%3D%205%20%5Ctimes%202)

3. repeat step 2 on remaining non-prime numbers until only prime numbers remain

![](https://latex.codecogs.com/gif.latex?%5Cbg_black%20%5CLARGE%206%20%3D%202%20%5Ctimes%203)

4. order the primes, writing as powers for any repeating primes

![](https://latex.codecogs.com/gif.latex?%5Cbg_black%20%5CLARGE%20420%20%3D%202%5E2%20%5Ctimes%203%20%5Ctimes%205%20%5Ctimes%207)

## PROGRAMMING LANGUAGES

### C

``` c
void find_prime_factors(int n){

  while(n % 2 == 0){
    printf("2, ");
    n = n/2;
  }
  
  for(int i = 3; i < sqrt(n); i = i+2){
    while(n%i == 0){
      printf("%d, ", i);
      n = n/i;
    }
  }
  
  if(n > 2){
    printf("%d, ", n);
  }

    printf("\n");
}
```

# FUNCTIONAL ELEMENTS

## RANGES

Having a declarative range is useful in functional programming as an alternative
to iterating in a loop

### C++ - RANGE
``` c++
#include <iostream>
#include <vector>
#include <numeric>

std::vector<int> range(int n){
  std::vector<int> result;
  for(int i = 0; i < n; i++){
    result.push_back(i);
  }
  return result;
}

int main(int argc, char** argv){
  for(int x : range(10)) std::cout << x << ", ";
  std::cout << "\n";
  return 0;
}
```

#### JAVA - RANGE
``` java
class Functional {
    public static void main(String[] args) {
        IntStream.range(1, 10).forEach(System.out::print);
        System.out.println(); 
    }
}
```
#### PYTHON - RANGE
``` python
for i in range(10):
    print(i);
```

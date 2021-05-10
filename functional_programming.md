# FUNCTIONAL PROGRAMMING

## RANGES

Having a declarative range is useful in functional programming as an alternative
to iterating in a loop

### C++ - RANGE
``` c++
#include <algorithm>
#include <iostream>
#include <vector>

int main(){
    std::vector<int> my_range;
    std::generate_n(std::back_inserter(my_range), 10, [n = 0] () mutable { return n++; });
    for(int i : my_range){std::cout << i << ", ";};
    std::cout << "\n";
}
```

#### JAVA - RANGE
``` java
class Functional {
    public static void main(String[] args) {
        IntStream.range(0, 10).forEach(System.out::print);
        System.out.println(); 
    }
}
```

#### PYTHON - RANGE
``` python
for i in range(10):
    print(i, end = ", ");

print()
```

#### JAVASCRIPT - RANGE
``` javascript
function* range(start, stop, step = 1) {
    if (stop == null) {
        // one param defined
        stop = start;
        start = 0;
    }

    for (let i = start; step > 0 ? i < stop : i > stop; i += step) {
        yield i;
    }
}

for (let i of range(10)) {
    console.log(i);
}
```

#### HASKELL - RANGE
``` haskell
my_range = [0..9]
main = print (my_range)
```

#### COMMON LISP - RANGE
``` lisp
(defun range (max &key (min 0) (step 1))
   (loop for n from min below max by step
         collect n))

(print (range 10))
```

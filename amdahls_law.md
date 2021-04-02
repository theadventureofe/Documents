# Amdahl's Law

## Formula

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;S_{latency(s)>}&space;=&space;\frac{1}{1&space;-&space;p&space;&plus;&space;\frac{p}{s}})

## Latex
```
\[S_{latency(s)} = \frac{1}{1 - p + \frac{p}{s}}\]
```
## Variables
<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">

<thead>
<tr>
<th scope="col">Variable Name</th>
<th scope="col">Variable Description</th>
</tr>
</thead>

<tbody>
<tr>
<td> <img src= "https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;S_{latency(s)}"> </img></td>

<td>Overall, theoretical speedup of the entire task by the improvement</td>
</tr>

<tr>
<td> <img src ="https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;p"> </img> </td>

<td>Proportion of execution time that the part benefiting from improved resources originally occupied</td>
</tr>

<tr>
<td><img src = "https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;s"></img></td>
<td>speedup of the part of the task that benefits from improved system resources</td>
</tr>
</tbody>
</table>

## Notes

A formula to work out the theoretical speedup of an entire task by improving only a part of the code or system.
This law states that the overall performance improvement gained by optimising a single part of a system is limited by the fraction of time that the improved part is actually used.

## Example

A system part initially consumes 60% of execution time (p = 0.6). The part is sped up by a factor of 3 (s = 3)

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;speedup&space;=&space;\frac{1}{1&space;-&space;p&space;&plus;&space;\frac{p}{s}})

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;1&space;\div&space;(1&space;-&space;0.6&space;&plus;&space;(0.6&space;\div&space;3))&space;=&space;1.66666666667)

or

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;speedup&space;=&space;\frac{1}{1&space;-&space;0.6&space;&plus;&space;\frac{0.6}{3}}&space;=&space;1.66666666667)

Notice that a significant increase to the speed of a part led to a much more modest increase in overall system performance.

## Example Latex

```
\[speedup = \frac{1}{1 - p + \frac{p}{s}}\]
```

```
\[1 \div (1 - 0.6 + (0.6 \div3)) = 1.66666666667\]
```

```
\[speedup = \frac{1}{1 - 0.6 + \frac{0.6}{3}} = 1.66666666667\]
```

## Links

### Wikipedia

<https://en.wikipedia.org/wiki/Amdahl%27s_law>

### Calculators

<https://www.vcalc.com/wiki/vCalc/Amdahl%27s+Law>
<https://www.fxsolver.com/solve/>

### Techopedia

<https://www.techopedia.com/definition/17035/amdahls-law>


## Programming Functions

### C
```C
    double amdahls_law_ratio(double p, double s){
      return 1 / (1 - p + p/s);
    }
    
    double amdahls_law_percentage(double p, double s){
      return 1 / (1 - (p/100) + (p/100)/s);
    }
```
### C++17
```c++
    auto amdahls_law_ratio = [](double p, double s){return 1 / (1 - p + p/s);};
    
    auto amdahls_law_percentage = [](double p, double s){return 1 / (1 - (p/100) + (p/100)/s);};
```
### Clojure
```clojure
    (defn amdahls_law_ratio [p s]
      (/ 1.0 (+  1.0 (- p) (/ p s))))
    
    (defn amdahls_law_percentage [p s]
      (/ 1.0 (+  1.0 (- (/ p 100.0)) (/ (/ p 100.0) s))))
```
### Common Lisp
```common-lisp
    (defun amdahls-law-ratio(p s)
      (/ 1.0 (+ 1.0 (- p)(/ p s))))
    
    (defun amdahls-law-percentage(p s)
      (/ 1.0 ( + 1.0 (- (/ p 100.0)) (/ (/ p 100.0) s))))
```
### Haskell
```haskell
    amdahls_law_ratio :: Double -> Double -> Double
    amdahls_law_ratio p s = 1 / (1 - p + p/s) 
    
    amdahls_law_percentage :: Double -> Double -> Double
    amdahls_law_percentage p s = 1 / (1 - (p/100) + (p/100) / s)
```
### Javascript
```javascript
    const amdahls_law_ratio = (p, s) => 1 / (1 - p + p/s);
    
    const amdahls_law_percentage = (p, s) => 1 / (1 - (p/100) + (p/100) / s);
```
### Python
```python
    amdahls_law_ratio = lambda p, s : 1 / (1 - p + p / s)
    
    amdahls_law_percentage = lambda p, s : 1 / (1 - (p/100) + (p/100) / s)
```

### Typescript
```typescript
    const amdahls_law_ratio = (p: number, s: number): number => 1 / (1 - p + p/s);
    
    const amdahls_law_percentage = (p: number, s: number): number => 1 / (1 - (p/100) + (p/100) / s);
```
## Graphs

![](https://user-images.githubusercontent.com/80133802/113050057-56ac7300-919c-11eb-98a9-968f08788b4d.png)

![](https://user-images.githubusercontent.com/80133802/113052863-8d37bd00-919f-11eb-8fed-d5fe098088e0.png)

### Graph Code

#### Python

```python
import numpy as np
import csv
import matplotlib.pyplot as plt

my_range = np.linspace(0,100,100)

amdahls_law = lambda p, s : 1 / (1 - (p/100) + (p/100) / s)

plot_factor = lambda my_range, factor:  plt.plot(amdahls_law(my_range, factor), my_range, label = "(s) Part sped up by a factor of " + str(factor))

plot_factor(my_range, 2)
plot_factor(my_range, 3)
plot_factor(my_range, 4)

plt.title(r'Amdahls Law')
plt.xlabel('(SLatency): Total Improvement of system')
plt.ylabel('(P): % of time the part previously occupied')
plt.grid(color='black', linestyle='-', linewidth=0.5)
plt.legend()
plt.show()
```

```python
import numpy as np
import csv
import matplotlib.pyplot as plt

my_range = np.linspace(0,10,100)

amdahls_law = lambda p, s : 1 / (1 - (p/100) + (p/100) / s)

plot_percentage = lambda percentage, my_range: plt.plot(my_range, amdahls_law(percentage, my_range), label = "(p): part previously  occupied " + str(percentage) + "% of time") 

plot_percentage(25, my_range)
plot_percentage(50, my_range)
plot_percentage(75, my_range)

plt.title(r'Amdahls Law')
plt.xlabel('(s): Part sped up by a factor of')
plt.ylabel('(SLatency): Total Improvement of system')
plt.grid(color='black', linestyle='-', linewidth=0.5)
plt.legend()
plt.show()
```
## Trivia

Sometimes called Amdahl's argument.

named after computer scientist Gene Amdahl.

Was presented at the AFIPS Spring Joint Computer Conference in 1967.

Often used in parallel computing to predict the theoretical speedup when using multiple processors.


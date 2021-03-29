
# Table of Contents

1.  [Amdahl's Law](#org34222e6)
    1.  [Formula](#org6a1c4ed)
    2.  [Latex](#orgccb2718)
    3.  [Variables](#org874f026)
    4.  [Notes](#org4205fe4)
    5.  [Example](#orgf603242)
    6.  [Wiki Article](#org049fbef)
    7.  [\*\* Links](#org8ebc373)
        1.  [Wikipedia](#org3396418)
        2.  [Calculators](#org0a72e4f)
        3.  [Techopedia](#org360878d)
    8.  [Programming Functions](#orgc5e3ff5)
        1.  [C](#org186cdab)
        2.  [C++17](#org4ad3f2a)
        3.  [Clojure](#org784c74b)
        4.  [Common Lisp](#org225793f)
        5.  [Haskell](#org2c86114)
        6.  [Javascript](#orgbfa778f)
        7.  [Python](#orge6e7a48)
        8.  [Typescript](#org1b021cd)
    9.  [Trivia](#org54d5b45)


<a id="org34222e6"></a>

# Amdahl's Law


<a id="org6a1c4ed"></a>

## Formula

<https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;S_{latency(s)>}&space;=&space;\frac{1}{1&space;-&space;p&space;&plus;&space;\frac{p}{s}}


<a id="orgccb2718"></a>

## Latex

\[S_{latency(s)} = \frac{1}{1 - p + \frac{p}{s}}\]


<a id="org874f026"></a>

## Variables

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">Variable Name</th>
<th scope="col" class="org-left">Variable Description</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left"><a href="https://latex.codecogs.com/gif.latex?%5Cbg_black&amp;space;%5CLARGE&amp;space;S_%7Blatency(s)">https://latex.codecogs.com/gif.latex?%5Cbg_black&amp;space;%5CLARGE&amp;space;S_%7Blatency(s)</a>}</td>
<td class="org-left">Overall, theoretical speedup of the entire task by the improvement</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">p</td>
<td class="org-left">Proportion of execution time that the part benefiting from improved resources originally occupied</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">s</td>
<td class="org-left">speedup of the part of the task that benefits from improved system resources</td>
</tr>


<tr>
<td class="org-left">&#xa0;</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>


<a id="org4205fe4"></a>

## Notes

A formula to work out the theoretical speedup of an entire task by improving only a part of the code or system.
This law states that the overall performance improvement gained by optimising a single part of a system is limited by the fraction of time that the improved part is actually used.


<a id="orgf603242"></a>

## Example

A system part initially consumes 60% of execution time (p = 0.6). The part is sped up by a factor of 3 (s = 3)

<https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;speedup&space;=&space;\frac{1}{1&space;-&space;p&space;&plus;&space;\frac{p}{s>}}
\[speedup = \frac{1}{1 - p + \frac{p}{s}}\]

<https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;1&space;\div&space>;(1&space;-&space;0.6&space;&plus;&space;(0.6&space;&divide;&space;3))&space;=&space;1.66666666667
\[1 / (1 - 0.6 + 0.6/3) = 1.66666666667\] 

or

<https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;speedup&space;=&space;\frac{1}{1&space;-&space;0.6&space;&plus;&space;\frac{0.6}{3}}&space;=&space;1.66666666667>
\[speedup = \frac{1}{1 - 0.6 + \frac{0.6}{3}} = 1.66666666667\]

Notice that a significant increase to the speed of a part led to a much more modest increase in overall system performance.


<a id="org049fbef"></a>

## Wiki Article

<https://en.wikipedia.org/wiki/Amdahl%27s_law>


<a id="org8ebc373"></a>

## \*\* Links


<a id="org3396418"></a>

### Wikipedia

<https://en.wikipedia.org/wiki/Amdahl%27s_law>


<a id="org0a72e4f"></a>

### Calculators

<https://www.vcalc.com/wiki/vCalc/Amdahl%27s+Law>
<https://www.fxsolver.com/solve/>


<a id="org360878d"></a>

### Techopedia

<https://www.techopedia.com/definition/17035/amdahls-law>


<a id="orgc5e3ff5"></a>

## Programming Functions


<a id="org186cdab"></a>

### C

    #include <stdlib.h>
    #include <stdio.h>
    
    double amdahls_law_ratio(double p, double s){
      return 1 / (1 - p + p/s);
    }
    
    double amdahls_law_percentage(double p, double s){
      return 1 / (1 - (p/100) + (p/100)/s);
    }
    
    int main(int argc, char** argv){
    
      printf("%f \n", amdahls_law_ratio(0.6, 3));
      printf("%f \n", amdahls_law_percentage(60, 3));
    
      return EXIT_SUCCESS;
    }


<a id="org4ad3f2a"></a>

### C++17

    auto amdahls_law_ratio = [](double p, double s){return 1 / (1 - p + p/s);};
    
    auto amdahls_law_percentage = [](double p, double s){return 1 / (1 - (p/100) + (p/100)/s);};


<a id="org784c74b"></a>

### Clojure

    (defn amdahls_law_ratio [p s]
      (/ 1.0 (+  1.0 (- p) (/ p s))))
    
    (defn amdahls_law_percentage [p s]
      (/ 1.0 (+  1.0 (- (/ p 100.0)) (/ (/ p 100.0) s))))


<a id="org225793f"></a>

### Common Lisp

    (defun amdahls-law-ratio(p s)
      (/ 1.0 (+ 1.0 (- p)(/ p s))))
    
    (defun amdahls-law-percentage(p s)
      (/ 1.0 ( + 1.0 (- (/ p 100.0)) (/ (/ p 100.0) s))))


<a id="org2c86114"></a>

### Haskell

    amdahls_law_ratio :: Double -> Double -> Double
    amdahls_law_ratio p s = 1 / (1 - p + p/s) 
    
    amdahls_law_percentage :: Double -> Double -> Double
    amdahls_law_percentage p s = 1 / (1 - (p/100) + (p/100) / s)


<a id="orgbfa778f"></a>

### Javascript

    const amdahls_law_ratio = (p, s) => 1 / (1 - p + p/s);
    
    const amdahls_law_percentage = (p, s) => 1 / (1 - (p/100) + (p/100) / s);


<a id="orge6e7a48"></a>

### Python

    amdahls_law_ratio = lambda p, s : 1 / (1 - p + p / s)
    
    amdahls_law_percentage = lambda p, s : 1 / (1 - (p/100) + (p/100) / s)


<a id="org1b021cd"></a>

### Typescript

    const amdahls_law_ratio = (p: number, s: number): number => 1 / (1 - p + p/s);
    
    const amdahls_law_percentage = (p: number, s: number): number => 1 / (1 - (p/100) + (p/100) / s);


<a id="org54d5b45"></a>

## Trivia

Sometimes called Amdahl's argument.

named after computer scientist Gene Amdahl.

Was presented at the AFIPS Spring Joint Computer Conference in 1967.

Often used in parallel computing to predict the theoretical speedup when using multiple processors.


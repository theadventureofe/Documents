Amdahl’s Law
============

Formula
-------

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;S_{latency(s)}&space;=&space;\frac{1}{1&space;-&space;p&space;&plus;&space;\frac{p}{s}})

Variables
---------

|Variable Name|Variable Description|
|:------------|:-------------------|
|\[S_{latency}\]|Overall, theoretical speedup of the entire task by the improvement|
|||
|p|Proportion of execution time that the part benefiting from improved resources originally occupied|
|||
|s|speedup of the part of the task that benefits from improved system resources|
|||

Notes
-----

A formula to work out the theoretical speedup of an entire task by improving only a part of the code or system. This law states that the overall performance improvement gained by optimising a single part of a system is limited by the fraction of time that the improved part is actually used.

Example
-------

A system part initially consumes 60% of execution time (p = 0.6). The part is sped up by a factor of 3 (s = 3)

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;speedup&space;=&space;\frac{1}{1&space;-&space;p&space;&plus;&space;\frac{p}{s}})

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;1&space;/&space;(1&space;-&space;0.6&space;&plus;&space;0.6/3)&space;=&space;1.66666666667)

or

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;speedup&space;=&space;\frac{1}{1&space;-&space;0.6&space;&plus;&space;\frac{0.6}{3}}&space;=&space;1.66666666667)

Notice that a significant increase to the speed of a part led to a much more modest increase in overall system performance.

C
-

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

Wikipedia Article
-----------------

<https://en.wikipedia.org/wiki/Amdahl%27s_law>

Trivia
------

Sometimes called Amdahl’s argument.

named after computer scientist Gene Amdahl.

Was presented at the AFIPS Spring Joint Computer Conference in 1967.

Often used in parallel computing to predict the theoretical speedup when using multiple processors.

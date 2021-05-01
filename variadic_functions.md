# VARIADIC FUNCTIONS

## DESCRIPTION

A variadic function accepts a variable number of arguments.

## LINKS
<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">

<thead>
<tr>
<th scope="col">Link</th>
<th scope="col">Description</th>
</tr>
</thead>

<tbody>
<tr>
<td><https://en.wikipedia.org/wiki/Variadic_function</td>
<td>Wikipedia</td>
</tr>

</tbody>
</table>

## PROGRAMMING LANGUAGES

### C

```c
#include <stdarg.h>
#include <stdlib.h>
#include <stdio.h>

double mean(int count,...){
  va_list ap;
  va_start(ap, count);
  
  double sum = 0;

  for(size_t i = 0; i < count; i++){
    sum += va_arg(ap, double);
  }
  va_end(ap);
  return sum / count;
}
    
int main (int argc, char** argv) {
  printf ("%f\n", mean(3, 10.5, 25.4, 30.5));
  printf ("%f\n", mean(5, 1.0, 21.0, 3.0, 9.0, 19.0));
  return EXIT_SUCCESS;
}
```

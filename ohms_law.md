# OHM'S LAW

## FORMULA
![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;I&space;=&space;\frac{V}{R})

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;V&space;=&space;IR)

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;R&space;=&space;\frac{V}{I})
## LaTeX
```
\[I = \frac{V}{R}\]
\[V = IR\]
\[R = \frac{V}{I}\]
```

## VARIABLES
<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">

<thead>
<tr>
<th scope="col">Variable Name</th>
<th scope="col">Variable Description</th>
</tr>
</thead>

<tbody>
<tr>
<td> <img src ="https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;I"> </img> </td>

<td>Current through conductor (Amperes)</td>
</tr>

<tr>
<td> <img src ="https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;V"> </img> </td>

<td>Voltage across conductor (Volts)</td>
</tr>

<tr>
<td><img src = "https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;R"></img></td>

<td>Resistance of the conductor (Ohms)</td>
</tr>
</tbody>
</table>

## NOTES

A law that states current through a conductor between 2 points is directly proportional to the
voltage across those 2 points. 

## EXAMPLE 1
A circuit has a 12 volt battery (V = 12) and a resistor of 600 ohms (R = 600). Find the current.

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;I&space;=&space;\frac{V}{R})

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;I&space;=&space;\frac{12}{600})

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;\frac{12}{600}&space;=&space;0.02&space;Amperes)

or

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;20&space;milliAmperes)

## EXAMPLE 1 LaTeX
```
\[I = \frac{V}{R}\]
\[I = \frac{12}{600i}\]
\[\frac{12}{600} = 0.02 Amperes\]
\[20milliAmperes\]
```

## EXAMPLE 2
A circuit has a battery and a resistor of 600 ohms (R = 600).
Current Measured in the circuit is found to be 3 mA or milliamperes (I = 0.003). Find the voltage.

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;V&space;=&space;IR)

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;V&space;=&space;600&space;\times&space;0.003)

![](https://latex.codecogs.com/gif.latex?\bg_black&space;\LARGE&space;600&space;\times&space;0.003&space;=&space;1.8V)

## EXAMPLE 2 LaTeX
```
\[V = IR\]
\[V = 600 \times 0.003\]
\[600 \times 0.003 = 1.8V\]
```
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
<td>https://en.wikipedia.org/wiki/Ohm%27s_law</td>
<td>Wikipedia</td>
</tr>

<tr>
<td>https://www.calculator.net/ohms-law-calculator.html</td>
<td>Calculator</td>
</tr>

<tr>
<td>https://www.techopedia.com/definition/8662/ohms-law</td>
<td>Techopedia</td>
</tr>

</tbody>
</table>

## PROGRAMMING LANGUAGES

### C

```C
double ohms_law_current(double voltage, double resistance){
  return voltage / resistance;
}

double ohms_law_voltage(double current, double resistance){
  return current * resistance; 
}

double ohms_law_resistance(double voltage, double current){
  return voltage / current;
}
```

### C++17

```C++
auto ohms_law_current = [](double voltage, double resistance){return voltage / resistance;};
auto ohms_law_voltage = [](double current, double resistance){return current * resistance;};
auto ohms_law_resistance = [](double voltage, double current){return voltage / current;};
```
### COMMON LISP
```common-lisp
(defun ohms-law-current(voltage resistance)
  (/ voltage resistance))

(defun ohms-law-voltage(current resistance)
  (* current resistance))

(defun ohms-law-resistance(voltage current)
  (/ voltage current))
```
### HASKELL
```haskell
ohms_law_current :: Double -> Double -> Double
ohms_law_current voltage resistance = voltage / resistance

ohms_law_voltage :: Double -> Double -> Double
ohms_law_voltage current resistance = current * resistance

ohms_law_resistance :: Double -> Double -> Double
ohms_law_resistance voltage current = voltage / current
```
### JAVASCRIPT
```javascript
const ohms_law_current = (voltage, resistance) => voltage / resistance;
      
const ohms_law_voltage = (current, resistance) => current * resistance;
      
const ohms_law_resistance = (voltage, current) => voltage / current;
```
### PYTHON
```python
ohms_law_current = lambda voltage, resistance: voltage / resistance;

ohms_law_voltage = lambda current, resistance: current * resistance;

ohms_law_resistance = lambda voltage, current: voltage / current;
```
### TYPESCRIPT
```typescript
const ohms_law_current = (voltage: number, resistance: number): number => voltage / resistance;
      
const ohms_law_voltage = (current: number, resistance: number): number => current * resistance;
      
const ohms_law_resistance = (voltage: number, current: number): number => voltage / current;
```

## TRIVIA
Named after Georg Ohm.

It was published in 1827.




[back to index](README.md)

# Complex Numbers

Complex numbers as topic could well fit into the topic [Variables and Types](VariablesAndTypes.md).

But as I use complex numbers quite often, I concentrate this topic on a separate page.

## non-vector complex numbers

* constructing a complex number from two integers or floats
```
import cmath

x = 1.0
y = 1.0
 
# converting x and y into complex number
z = complex(x,y)

print(z)
# (1+1j)
```
> [!NOTE]
> the args for complex() are Cartesian coordinates, German:Normalform

Or, by assignment:
```
z = 5+3j
```
Looking at it, the assignment variant looks much more readable.

The complex number *z* has those non-private functions:
* **conjugate**
* **imag**
* **real**

* converting a Cartesian complex number into polar coordinates
```
z_polar = cmath.polar(z)
print(z_polar)
# (1.4142135623730951, 0.7853981633974483)

print(dir(z_polar))
['count', 'index']
```
Hmm.., this is interesting. Why the heck returned cmath.polar something like a list..?

Anything else is understood. 1.41(..) is sqrt(+1 + +1); 

* getting the phase of a complex number
```
import cmath
print(cmath.phase(z))
```
* It looks as there are no methods to convert phases from rad to degree or vice versa.
* the built-in **abs()** returns the absolute value (or modulus)
* functions and constants for complex numbers
    * **exp()** is equivalent to *f(x) = e^x*
    * **log(x,b)** is equivalent to *f(x) = log**b**(x)*, with b = (10, 2, e, ...)
    * **log10()** is equivalent to **log(x, 10)**, see above
    * **sqrt()**, square root
    * **cmath.pi** = 3.14159265(...)
    * **cmath.e** = 2.7182818(...)
    * **cmath.sin()**, **cmath.cos()**, **cmath.tan()**
    * **cmath.asin()**, **cmath.acos()**, **cmath.atan()**
    * **cmath.sinh()**, **cmath.cosh()**, **cmath.tanh()**
    * **cmath.asinh()**, **cmath.acosh()**, **cmath.atanh()**


 ## vectors of complex numbers using NumPy
NumPy allows all of this functions to be done on single values, as well as vectors.

In NumPy, we have two functions for returning the imaginary or real part of a complex number.
* **numpy.real()**
* **numpy.imag()**
```
import numpy as np

print(np.real(c))
print(np.imag(c))
```

These functions return the absolute value or the phase of a complex number.
* **numpy.abs()**
* **numpy.phase()**
```
import numpy as np

print(np.abs(c))
print(np.phase(c))
```

Converting between degree (+/-180°) or radians.
* **numpy.rad2deg()**
* **numpy.deg2rad()**

Geometrically, **conjugation** is reflection on the real axis, or, just change the sign of the imaginary part in Cartesian.
* **numpy.conj()**

Numpy has own versions of sin and cos.
* **numpy.sin()**, **numpy.cos()**, **numpy.tan()**
 
[back to index](README.md)

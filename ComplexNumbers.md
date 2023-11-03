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
> the args for complex() are kartesian, German:Normalform

Or, by assignment:
```
z = 5+3j
```
Looking at it, the assignment variant looks much more readable.

The complex number *z* has those non-private functions:
* **conjugate**
* **imag**
* **real**

* converting a kartesian complex number into polar coordinates
```
z_polar = cmath.polar(z)
print(z_polar)
# (1.4142135623730951, 0.7853981633974483)

print(dir(z_polar))
['count', 'index']
```
Hmm.., this is interesting. Why the heck returned cmath.polar something like a list..?

Anything else is understood. 1.41(..) is sqrt(+1 + +1); 



[back to index](README.md)

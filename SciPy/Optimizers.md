[back to Index](Index.md)

# Optimizers

Optimizers are a set of procedures in SciPy that either find the minimum value of a function, or the root of an equation, ie polynoms.
> [!NOTE]
> A root of a polynomial P(z) is a number z_i such that P(z_i)=0.

Let's plot the function *f(x) = x + cos(x)*.
```
import matplotlib.pyplot as plt
import numpy as np
from math import cos

xpoints = np.array(list(range(-50,50))) * 0.1 
ypoints = np.array(list(map(lambda x : x + cos(x), list(xpoints))))

plt.plot(xpoints, ypoints)
plt.grid()
plt.show()
```
![Figure_1](./img/Figure_1.png)


[back to Index](Index.md)

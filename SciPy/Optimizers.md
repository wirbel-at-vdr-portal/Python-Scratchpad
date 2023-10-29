[back to Index](Index.md)

# Optimizers

Optimizers are a set of procedures in SciPy that either find the minimum value of a function, or the root of an equation, ie polynoms.

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

## *optimize.root()* - Find the roots of a function
Now, let's find the roots of the function *f(x) = x + cos(x)* using **optimize.root()**.

> [!NOTE]
> A root of a function F(x) is a number x, such that F(x)=0.

* [Syntax: *root\(fun, x0\[, args, method, jac, tol, ...\]\)*](https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.root.html#scipy.optimize.root)
* *fun* - a vector function to find a root of.
* *x0* - initial guess for x.

```
from math import cos
from scipy import optimize

def myfunc(x):
    return x + cos(x)

zeros = optimize.root(myfunc, 0)

print(zeros.x)
# [-0.73908513]

print(zeros)
# message: The solution converged.
# success: True
#  status: 1
#     fun: [ 0.000e+00]
#       x: [-7.391e-01]
#    nfev: 9
#    fjac: [[-1.000e+00]]
#       r: [-1.674e+00]
#     qtf: [-2.668e-13]
```
The return object *zeros* contains the result in it's member x.



[back to Index](Index.md)

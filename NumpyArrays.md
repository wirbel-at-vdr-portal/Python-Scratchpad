[back to index](README.md)

# *Numpy Arrays*
Numpy arrays are that they are fast, easy to work with, and give users the opportunity to perform calculations
across entire arrays. Numpy Arrays require the use of the numpy package.
> [!NOTE]
> To use a numpy array as a standard python array, use the list() function.

Numpy arrays can be multidimensional.

```
# Create 2 new lists height and weight
height = [1.87,  1.87, 1.82, 1.91, 1.90, 1.85]
weight = [81.65, 97.52, 95.25, 92.98, 86.18, 88.45]
          
# Import the numpy package as np: we need prefix np later
import numpy as np
          
# Create 2 numpy arrays from height and weight
np_height = np.array(height)
np_weight = np.array(weight)
          
#gives <class 'numpy.ndarray'>
#print(type(np_height))
          
#-------------------------------------------------------------------
# Now we can perform element-wise calculations on height and weight.
# For example, you could take all 6 of the height and weight
# observations above, and calculate the BMI for each observation
# with a single equation. These operations are very fast and
# computationally efficient. They are particularly helpful
# when you have 1000s of observations in your data.
#-------------------------------------------------------------------
          
# Calculate bmi
bmi = np_weight / np_height ** 2
          
# Print the result
print(bmi)
# [ 23.34925219  27.88755755  28.75558507  25.48723993  23.87257618 25.84368152]

#-------------------------------------------------------------------
# Another great feature of Numpy arrays is the ability to subset.
# For instance, if you wanted to know which observations in
# our BMI array are above 23, we could quickly subset it to find out.
#-------------------------------------------------------------------
print(bmi[bmi > 25])
# [ 27.88755755  28.75558507  25.48723993  25.84368152]
```

Second example
```
import numpy as np

weight_kg = [81.65, 97.52, 95.25, 92.98, 86.18, 88.45]
# Create a numpy array np_weight_kg from weight_kg
np_weight_kg = np.array(weight_kg)

# Create np_weight_lbs from np_weight_kg
np_weight_lbs = 2.2 * np_weight_kg

# Print out np_weight_lbs
print(np_weight_lbs)
```

If we want to explicitly set the data type of the resulting array, we can use the **dtype** keyword:
```
np.array([1, 2, 3, 4], dtype='float32')
```

* Create a length-10 integer **array filled with zeros**
```
np.zeros(10, dtype=int)
```
* Create a 3x5 floating-point **array filled with ones**
```
np.ones((3, 5), dtype=float)
```
* Create a 3x5 **array filled with 3.14**
```
np.full((3, 5), 3.14)
```
* Create an array filled with a **linear sequence** Starting at 0, ending at 20, stepping by 2
(this is similar to the built-in range() function)
```
np.arange(0, 20, 2)
```
* Create an array of **five values evenly spaced** between 0 and 1
```
np.linspace(0, 1, 5)
```
* Create a 3x3 array of uniformly distributed **random values between 0 and 1**
```
np.random.random((3, 3))
```
* Create a 3x3 array of normally distributed random values with mean 0 and standard deviation 1
```
np.random.normal(0, 1, (3, 3))
```
* Create a 3x3 array of random integers in the interval [0, 10)
```
np.random.randint(0, 10, (3, 3))
```
* Create an **uninitialized array** of three integers
```
np.empty(3)
```
* **Subarrays** of array 'x'
> [!NOTE]
> The returned subarray is a view rather than a copy of the array data. 
```
x[start:stop:step]
x[start:stop]  # step = 1
x[::2]         # every other element
x[1:2]         # as above, but starts at one
```
* Changing the number of rows or columns by **reshaping** an array
```
x.reshape((3, 1))
```
* **Concatenating several arrays** into one array
```
import numpy as np

array1 = np.array([1, 2, 3])
array2 = np.array([4, 5, 6])
array3 = np.array([7, 8, 9])

print(np.concatenate([array1, array2, array3]))
# [1 2 3 4 5 6 7 8 9]
```
* **Splitting of arrays**

If splitting an array with **N** points, **N+1** subarrays are generated.
```
import numpy as np
a = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9])
array1, array2, array3 = np.split([2, 5, 7])

print(array1, array2, array3)
# [1 2] [3 4 5] [6 7]
```

To split multidimensional arrays by *columns* or *rows*, use **np.vsplit()** and **np.hsplit()**.

* **Operators in Numpy**
These ops are done on each array member:

| short form | long form | comment |
| -----------| --------- | ------- |
| \+ 	   | np.add 	| Addition (e.g., 1 \+ 1 = 2) |
| \- 	   | np.subtract 	| Subtraction (e.g., 3 \- 2 = 1) |
| \- 	   | np.negative 	| Unary negation (e.g., \-2) |
| \* 	   | np.multiply 	| Multiplication (e.g., 2 \* 3 = 6) |
| \/ 	   | np.divide 	| Division (e.g., 3 \/ 2 = 1.5) |
| \/\/ 	   | np.floor_divide| floor division (e.g., 3 \/\/ 2 = 1) |
| \*\* 	   | np.power 	| Exponentiation (e.g., 2 \*\* 3 = 8) |
| \% 	   | np.mod 	| Modulus/remainder (e.g., 9 \% 4 = 1) |

* np.abs() absolute value
* np.linspace(From, To, Count)
* np.sin(), np.cos(), np.tan
* np.arcsin(), np.arccos(), np.arctan
* np.exp(x), f(x) = 2.718^x
* np.exp2(x), f(x) = 2^x
* np.power(base,exp)
* ln(x), log2(), log10()

All of these *ufuncs* accept an *out = ..* param, such thta direct on this memory may be written.
```
x = np.arange(5)
y = np.empty(5)
np.multiply(x, 10, out=y)
print(y)
```

[back to index](README.md)

# **Variables and Types**

## *Numbers*
2 types of numbers, integer and float:
```
myint = 7
myfloat = 7.0
myfloat = float(7)
```
## *Boolean*
```
True, False
```
## *Strings*
```
mystring = 'hello'
mystring = "hello"
```
## *Lists*
* empty list
```
mylist = []
```
* index is zero based
* list can be initialized with values
```
even_numbers = [2,4,6,8]
odd_numbers = [1,3,5,7]
x_list = [x] * 10   # [x,x,..,x]
```
* lists can be added by '+'
```
all_numbers = odd_numbers + even_numbers
```
* elements can be added using append()
```
mylist.append(1)
```
## *Numpy Arrays*
Numpy arrays are that they are fast, easy to work with, and give users the opportunity to perform calculations across entire arrays.  
Numpy Arrays require the use of the numpy package.

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

## *Pandas*
Pandas is a high-level data manipulation tool developed by Wes McKinney.  
It is built on the Numpy package and its key data structure is called
the **DataFrame**. DataFrames allow you to store and manipulate tabular
data in rows of observations and columns of variables.

There are several ways to create a DataFrame.  
One way way is to use a dictionary.   
For example:
```
dict = {"country": ["Brazil", "Russia", "India", "China", "South Africa"],
                  "capital": ["Brasilia", "Moscow", "New Dehli", "Beijing", "Pretoria"],
                  "area": [8.516, 17.10, 3.286, 9.597, 1.221],
                  "population": [200.4, 143.5, 1252, 1357, 52.98] }

import pandas as pd
brics = pd.DataFrame(dict)

# OPTIONAL: Set the index for brics
# otherwise zero based integers are used, 0..4
brics.index = ["BR", "RU", "IN", "CH", "SA"]

print(brics)
```

The data can also be imported as csv file.
```
brics = pd.read_csv('brics.csv')
```

Usage example:
```
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)
print(cars)
#       cars_per_cap        country drives_right
#  US            809  United States         True
#  AUS           731      Australia        False
#  JAP           588          Japan        False
#  IN             18          India        False
#  RU            200         Russia         True
#  MOR            70        Morocco         True
#  EG             45          Egypt         True

# Print out country column as Pandas Series (single brackets)
print(cars['cars_per_cap'])
#  US     809
#  AUS    731
#  JAP    588
#  IN      18
#  RU     200
#  MOR     70
#  EG      45

# Print out country column as Pandas DataFrame
print(cars[['cars_per_cap']])
# Name: cars_per_cap, dtype: int64
#      cars_per_cap
# US            809
# AUS           731
# JAP           588
# IN             18
# RU            200
# MOR            70
# EG             45

# Print out DataFrame with country and drives_right columns
print(cars[['country', 'drives_right']])
#            country drives_right
# US   United States         True
# AUS      Australia        False
# JAP          Japan        False
# IN           India        False
# RU          Russia         True
# MOR        Morocco         True
# EG           Egypt         True
```

Square brackets can also be used to access observations (rows) from a DataFrame.  
For example:
```
import pandas as pd

# Import cars data
cars = pd.read_csv('cars.csv', index_col = 0)
           
# Print out first 4 observations
# Note the last number..
print(cars[0:4])
#      cars_per_cap        country drives_right
# US            809  United States         True
# AUS           731      Australia        False
# JAP           588          Japan        False
# IN             18          India        False

# Print out fifth and sixth observation
print(cars[4:6])
#      cars_per_cap  country drives_right
# RU            200   Russia         True
# MOR            70  Morocco         True
```

You can also use loc and iloc to perform just about any data selection operation.  
* **loc** is **label-based**, which means that you have to specify rows and columns based on their row and column labels.
* **iloc** is **integer index based**, so you have to specify rows and columns by their integer index.
```
# Import cars data
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)

# Print out observation for Japan
print(cars.iloc[2])
# cars_per_cap      588
# country         Japan
# drives_right    False
# Name: JAP, dtype: object

# Print out observations for Australia and Egypt
print(cars.loc[['AUS', 'EG']])
#      cars_per_cap    country drives_right
# AUS           731  Australia        False
# EG             45      Egypt         Tru
```
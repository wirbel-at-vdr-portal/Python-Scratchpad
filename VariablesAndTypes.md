[back to index](README.md)

# **Variables and Types**

## Overview on Types

| Category        | Types                             |
|-----------------|-----------------------------------|
| Text Type       | [str](VariablesAndTypes.md#Strings) |
| Numeric Types   | [int, float, complex](VariablesAndTypes.md#Numbers) |
| Sequence Types  | [list](VariablesAndTypes.md#Lists), [tuple](VariablesAndTypes.md#Tuples), [range](VariablesAndTypes.md#Range), [array](VariablesAndTypes.md#Array) |
| Mapping Type    | [dict](VariablesAndTypes.md#Dictionaries)                              |
| Set Types       | [set](VariablesAndTypes.md#Sets), [frozenset](VariablesAndTypes.md#frozenset) |
| Boolean Type    | [bool](VariablesAndTypes.md#Boolean)                              |
| Binary Types    | [bytes](VariablesAndTypes.md#Bytes), [bytearray](VariablesAndTypes.md#ByteArray), [memoryview](VariablesAndTypes.md#MemoryView) |
| Untyped         | [NoneType](VariablesAndTypes.md#NoneType) |
| non-standard    | [Numpy Arrays](NumpyArrays.md), [Pandas](VariablesAndTypes.md#Pandas) |


## The *global* keyword
Variables defined with **global** belong to the global scope, even if defined in function.
```
def myfunc():
  global x
  x = 5

myfunc()
print(x)
# 5
```

## *Numbers*
integer, float and complex:
```
myint = 7
myfloat = 7.0
myfloat = float(7)
```

```
import cmath

x = 3 + 1j

print("type(x) = " + str(type(x)))
print("abs(x) = " + str(abs(x)))
print("phase(x) = " + str(cmath.phase(x)*180.0/3.1415) + "deg")
print("x.real = " + str(x.real))
print("x.imag = " + str(x.imag))
# type(x) = <class 'complex'>
# abs(x) = 3.1622776601683795
# phase(x) = 18.43549253267407deg
# x.real = 3.0
# x.imag = 1.0
```
## *Boolean*
```
True, False
```
## *Strings*
Single quotes and double quotes are supported. Single quotes may cause trouble with apostrophe.
```
mystring = 'hello'
mystring = "hello"
```
## *Lists*
Lists are multi-element containers, for which the items may have the same type. But - this not required.

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
L3 = [True, "2", 3.0, 4] # yes, this is allowed.
```
* lists can be added by '+'
```
all_numbers = odd_numbers + even_numbers
```
* elements can be added using **append()**
```
mylist.append(1)
```
* remove elements using **pop()**
```
# Delete the second element.
mylist.pop(1)
```
* print a list member
```
print(mylist[0])
```
* printing a list
```
print(all_numbers)
# [1, 3, 5, 7, 2, 4, 6, 8]
```
* iterate over list
```
for x in mylist:
    print(x)
```
* list members  

| function    | comment                                                                      |
| ----------- | ---------------------------------------------------------------------------- |
| *append()*  | Adds an element at the end of the list                                       |
| *clear()*   | Removes all the elements from the list                                       |
| *copy()*    | Returns a copy of the list                                                   |
| *count()*   | Returns the number of elements with the specified value                      |
| *extend()*  | Add the elements of a list (or any iterable), to the end of the current list |
| *index()*   | Returns the index of the first element with the specified value              |
| *insert()*  | Adds an element at the specified position                                    |
| *pop()*     | Removes the element at the specified position                                |
| *remove()*  | Removes the first item with the specified value                              |
| *reverse()* | Reverses the order of the list                                               |
| *sort()*    | Sorts the list                                                               |

## *Array*
Arrays are fixed type containers.
```
import array
L = list(range(10))
A = array.array('i', L)
A
# array('i', [0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
```
Here 'i' is a type code indicating the contents are integers.

## *Range*
**range()**  generates a sequence of ordered integers by defining a start and end point of the range.  
It is mainly used with the for loop. If start is not given, it defaults to zero, step defaults to 1.
* **Syntax**
```
range(stop)
range(start, stop[, step])
```
> [!NOTE]
> In Python 2, there are two functions for sequence of integers, *range* and *xrange*.
> These functions are very similar, but *range* returns a list, and *xrange* returns an *xrange object*.
> In Python 3, *xrange* has been dropped, and *range* behaves like Python 2 *xrange*.

## *Sets*
**Sets** can be understood as Lists with unique and constant items.  
Sets are
* a *collection of unique items* - **no duplicates**!
* *unordered*
* *unindexed* - no access by index
* *unchangeable*  
> [!NOTE]
> You can *add* or *remove* items, but not *change* items in a set.
```
aSet = {"apple", "banana", "cherry"}
```

* length of a set
```
    len(aSet)
```
* looping through a set
```
    for x in aSet:
        print(x)
```
* check if something is in a set
```
    if x in aSet:
        # do something
```
* add/remove items using its methods
```
    aSet.add("orange")
    aSet.remove("banana")
```
* union() and intersection() return a new set:
```
    set1 = {"a", "b" , "c"}
    set2 = {"a", "c", "e"}

    set3 = set1.union(set2)
    print(set3)
    # {'e', 'c', 'a', 'b'}

    print(set1.intersection(set2))
    # {'a', 'c'}
```
* Set methods

| Method                           | Description                                                                    |
| -------------------------------- | ------------------------------------------------------------------------------ |
| *add()*                          | Adds an element to the set                                                     |
| *clear()*                        | Removes all the elements from the set                                          |
| *copy()*                         | Returns a copy of the set                                                      |
| *difference()*                   | Returns a set containing the difference between two or more sets               |
| *difference_update()*            | Removes the items in this set that are also included in another, specified set |
| *discard()*                      | Remove the specified item                                                      |
| *intersection()*                 | Returns a set, that is the intersection of two or more sets                    |
| *intersection_update()*          | Removes the items in this set that are not present in other, specified set(s)  |
| *isdisjoint()*                   | Returns whether two sets have a intersection or not                            |
| *issubset()*                     | Returns whether another set contains this set or not                           |
| *issuperset()*                   | Returns whether this set contains another set or not                           |
| *pop()*                          | Removes an element from the set                                                |
| *remove()*                       | Removes the specified element                                                  |
| *symmetric_difference()*         | Returns a set with the symmetric differences of two sets                       |
| *symmetric_difference_update()*  | inserts the symmetric differences from this set and another                    |
| *union()*                        | Return a set containing the union of sets                                      |
| *update()*                       | Update the set with another set, or any other iterable                         |

## *frozenset*

* Syntax
**frozenset(iterable)**  
*iterable* - any object that can be iterated: list, tuple, string, dictionary, or a set.

The *frozenset()* is an inbuilt function, which takes an iterable object and returns its *frozenset object* initialized with elements from the given iterable. Frozenset objects and sets in Python are very similar. Both are unordered and unindexed. Frozenset objects are immutable (they can't be changed). The order of elements is not guaranteed to be preserved.
Since the frozenset is an immutable data type, it can be used in cases where we have to create a group of keys (or some other data) that we don't want the user to change, as frozenset doesn't allow changes.
```
myList = ['apple', 'banana', 'cherry']
x = frozenset(myList)
print(x)
```

## *Tuples*
**Tuples** can be understood as ordered Lists with constant items.  
Sets are
* a *collection of items*
* *ordered*
* *indexed* - zero based index
* *unchangeable*  
> [!NOTE]
> You can *add* or *remove* items, but not *change* items in a set.
```
    aTuple = (1,3,5,7)
```
* length of tuple
```
    len(aTuple)
```
* element access, negative index is from end
```
    aTuple[1]
    # 3

    aTuple[1:3]
    # (1,3)
```
* tuple methods

| Method     | Description                        |
| ---------- | ---------------------------------- |
| *count()*  | Returns the number of times a specified value occurs in a tuple                         |
| *index()*  | Searches the tuple for a specified value and returns the position of where it was found |

	

## *Dictionaries*
Similar to lists/array, but works with keys and values instead of indexes.  
Also similar to std::map.
```
phonebook = {}
phonebook["John"] = 938477566
phonebook["Jack"] = 938377264
phonebook["Jill"] = 947662781

# or ..
# phonebook = {
#     "John" : 938477566,
#     "Jack" : 938377264,
#     "Jill" : 947662781
#     }

print("Jacks number is %d." % phonebook["Jack"])  << Jacks number is 938377264.

for name, number in phonebook.items():                
    print("Phone number of %s is %d" % (name, number))

# delete an entry 
del phonebook["John"]

# add entry
phonebook["Jake"] = 938273443

# alternative zu del
phonebook.pop("Jake")
```

| Method         | Description |
| -------------- | ----------- |
| *clear()*      | Removes all the elements from the dictionary |
| *copy()*       | Returns a copy of the dictionary |
| *fromkeys()*   | Returns a dictionary with the specified keys and value |
| *get()*        | Returns the value of the specified key |
| *items()*      | Returns a list containing a tuple for each key value pair |
| *keys()*       | Returns a list containing the dictionary's keys |
| *pop()*        | Removes the element with the specified key |
| *popitem()*	   | Removes the last inserted key-value pair |
| *setdefault()* | Returns the value of the specified key. If the key does not exist: insert the key, with the specified value |
| *update()*     | Updates the dictionary with the specified key-value pairs |
| *values()*	   | Returns a list of all the values in the dictionary |


## *Byte Literals*
```
bytesliteral   ::=  bytesprefix(shortbytes | longbytes)
bytesprefix    ::=  "b" | "B" | "br" | "Br" | "bR" | "BR"
shortbytes     ::=  "'" shortbytesitem* "'" | '"' shortbytesitem* '"'
longbytes      ::=  "'''" longbytesitem* "'''" | '"""' longbytesitem* '"""'
shortbytesitem ::=  shortbyteschar | bytesescapeseq
longbytesitem  ::=  longbyteschar | bytesescapeseq
shortbyteschar ::=  <any ASCII character except "\" or newline or the quote>
longbyteschar  ::=  <any ASCII character except "\">
bytesescapeseq ::=  "\" <any ASCII character>
```
* example:
```
x = b'Bytes objects are immutable sequences of single bytes'
```
## *Bytes*
Returns a new *bytes object*, which is an immutable (constant) sequence of unsigned chars. *bytes* is an immutable version of bytearray.
* **Syntax** *bytes*([source[, encoding[, errors]]])

## *ByteArray*
Returns a new *array of bytes*. The *bytearray* type is a mutable (non-constant) sequence of unsigned chars.
* **Syntax** *bytearray*([source[, encoding[, errors]]])
If source is
  * ommitted - an array of size 0 is created
  * string - initialized by str.encode(). encoding is required.
  * an object conforming to the *buffer interface* - a read-only buffer of the object will be used to initialize
  * integer - an zeroed array of that size is created

> [!NOTE]
> The **buffer protocol** provides a way to access the internal data of an object. This internal data is a memory array or a buffer.
> The buffer protocol allows one object to expose its internal data (buffers) and the other to access those buffers without intermediate copying.
> This protocol is only accessible to us at the C-API level and not using our normal codebase.
> So, in order to expose the same protocol to the normal Python codebase, memory views are present.

## *MemoryView*
A memory view is a safe way to expose the **buffer protocol** in Python.
It allows you to access the internal buffers of an object by creating a memory view object.

Whenever we perform some action on an object (call a function of an object, slice an array), Python needs to create a copy of the object.
If we have large data to work with (eg. binary data of an image), we would unnecessarily create copies of huge chunks of data, which serves almost no use.
Using the **buffer protocol**, we can give another object access to use/modify the large data without copying it. This makes the program use less memory and increases the execution speed.

* Syntax: **memoryview(obj)**
   * obj - an object, which supports the buffer protocol (bytes, bytearray)
```
b = bytearray('ABC', 'utf-8')
print('Before:', b)

m = memoryview(b)

# update 1st index of m to 'Z'
m[1] = 90
print('After:', b)
# Before: bytearray(b'ABC')
# After: bytearray(b'AZC')
```

## *NoneType*
If you have experience with other programming languages, like C/C++, then you know the use of *null* or *NIL*. Other languages use a special pointer, which always doesn't point to anything. Sometimes *null* is an alias to int(0).

The purpose is to show, that *some value is not initialized* or a function failed to return a result.

Python uses the keyword **None** to define *null objects and variables* or **no value**. It's also used by functions that doesnt return anything.

**None** is not a value, but an object, even an *first class citizen*.  
None is a singleton. That is, the NoneType class only ever gives you the same single instance of None. There’s only one None in your Python program and that's why you should use the **is** operator.

> [!NOTE]
> Comparison with **None** should be done with the **is** operator, but not **==**.
> In boolean comparisons, *not None* is *True*.
> 
Of course, most operations doesnt work with None, for example adding it to a string.
But at least print() will accept a None.

* checking if result is valid or None
```
import re
match = re.match("Goodbye", "Hello, World!")
if match is None:
    print("It doesn't match.")
# It doesn't match.
```

* not preferred
```
some_result = None
if some_result:
    print("Got a result!")
else:
    print("No result.")
# No result.
```

## *Objects*
```
x = object()
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
* **iloc** is **integer index based**, so you have to specify rows and columns by their zero-based integer index.
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

[back to index](README.md)

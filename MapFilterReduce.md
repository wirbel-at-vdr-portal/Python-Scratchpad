[back to index](README.md)

# Map, Filter and Reduce

Map, Filter, and Reduce apply a function across a number of [iterables](Iterators.md), in a one line.

## The **map()** function
* *Syntax:* **map object = map(func, \*iterables)**
* *func* is applied to any member of the iterables, and a *map object* is returned.
* The returned *map object* can be passed to functions like
   * *list()* - to convert to list
   * *set()* - to convert to a set, and so on.
```
    my_pets = ['alfred', 'tabitha', 'william', 'arla']

    uppered_pets = list(map(str.upper, my_pets))

    print(uppered_pets)
    # ['ALFRED', 'TABITHA', 'WILLIAM', 'ARLA']
```

Second example, square each item of numbers.
```
    numbers = (1, 2, 3, 4)
    # now using a lambda
    result = map(lambda x : x*x, numbers)

    print(result)
    # <map object at 0x7ff36ce33070>

    # map object -> set
    numbersSquare = set(result)
    print(numbersSquare)
    # {16, 1, 4, 9}
```

In this example, corresponding items of two lists are added.
```
num1 = [4, 5, 6]
num2 = [5, 6, 7]

result = map(lambda n1, n2: n1+n2, num1, num2)

print(list(result))
# [9, 11, 13]
```

## The **filter()** function

* *Syntax:* **filter object = filter(func, iterable)**
* **filter()** selects those elements from an iterable, for which *func* returned True.
* *func* takes one arg (the type of the iterable's items) and returns boolean
* as in map(), the result needs to be converted with list(), set(), tuple(), ..
```
num = [6, 5, 8, 1]

result = filter(lambda i:i>5, num)

print(type(result))
print(list(result))
# <class 'filter'>
# [6, 8]
```

## The **reduce()** function
* *Syntax:* **variable_of_type_iterable_member = reduce(func, iterable[, initializer])**
* **reduce()** applies a function over all items are returns a single item.
* **reduce()** is inside functools module, we need to import it.

* func() is applied to:
   * the first two items
   * while next items are avail, the result of the last call and the next item
   * if no more items, the result of the last call is returned

 The idea behind is to take an existing function, apply it cumulatively to all the items in an iterable, and generate a single final value.

> [!NOTE]
> **reduce()** is written in C and might be *faster* than a normal for loop.The same with an initializer
```
from functools import reduce

def myAdd(a, b):
    result = a + b
    print(f"{a} + {b} = {result}")
    return result

myList = [0,1,2,3,4,5]

print(reduce(myAdd, myList))
# 0 + 1 = 1
# 1 + 2 = 3
# 3 + 3 = 6
# 6 + 4 = 10
# 10 + 5 = 15
# 15
```
Similar, now using an initializer:
```
from functools import reduce

def myAdd(a, b):
    result = a + b
    print(f"{a} + {b} = {result}")
    return result

numbers = [0, 1, 2, 3, 4]

print(reduce(myAdd, numbers, 100))
# 100 + 0 = 100
# 100 + 1 = 101
# 101 + 2 = 103
# 103 + 3 = 106
# 106 + 4 = 110
# 110
```


[back to index](README.md)

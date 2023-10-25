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

[back to index](README.md)

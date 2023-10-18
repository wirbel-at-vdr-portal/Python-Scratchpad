# List Comprehensions

***List comprehensions** offer a short syntax to create a new list based on the values of an existing list.  
The existing list is not touched.*

Imagine the following code
```
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
newlist = []

for x in fruits:
  if "a" in x:
    newlist.append(len(x))

print(newlist)

# [5, 6, 5]
```

This may be shortened to
```
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
newlist = [len(x) for x in fruits if "a" in x]

print(newlist)

# [5, 6, 5]
```

## The Syntax
newlist = [*expression* **for** *item in iterable* **if** condition == True]

The returned list is made of the existing list (*iterable*).
For each member of *iterable*, for which *condition == True*:
* item is resolved with it's value inside *expression*
* *expression* evaluated and the result put to the list

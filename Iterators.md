# Iterators

We will always read again and again about **Iterators** and **iterable**.

Python's for loops do not rely on indexes, they rely on iterators. Iterators are everywhere in Python.  
So it's worth to document a few things.

* **iterable**  
An **iterable** is  
  * anything that you can loop over in for loops
  * anything that you can pass to the built-in **iter()** function without having a *TypeError* being raised.
  * When passed to the built-in iter function, an **Iterator** will be returned.
 
One can check, if an object is an iterable:
```
print(iter(1))
TypeError: 'int' object is not iterable

print(iter((1,2,3)))
<tuple_iterator object at 0x1537f9ac1610>

print(iter([1,2,3]))
# <list_iterator object at 0x14be1f980610>
```
 
* **Iterators**  
An **iterator** is  
  * an object, which can be returned by the built-in **iter()** function.
  * an object, which implements the methods **\_\_iter__()** and **\_\_next__()**
  * if you call **next()** on an iterator object, you get **the next item** from it,
    or an *StopIteration exception* is raised, if no more items are available.
  * **iterators** are **iterables**.  
    If passed to *iter()*, an iterator returns itself back.    
```
try:
    it = iter([1,2,3])
    it2 = iter(it)
    
    if it2 is it:
        print("iter() on an iterator returns the iterator itself")
    else:
        print("iter() on an iterator returns a new iterator")

    print(next(it))
    print(next(it2))
    print(next(it))
    print(next(it))
except StopIteration:
    print("reached StopIteration exception")
# iter() on an iterator returns the iterator itself
# 1
# 2
# 3
# reached StopIteration exception
```

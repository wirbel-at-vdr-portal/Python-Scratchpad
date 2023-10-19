[back to index](README.md)

# Code Introspection

**Code Introspection** is an ability to determine the type of an object at runtime.

* Everything in python is an object.
* Every object in Python may have attributes and methods.
* By using introspection, we can dynamically examine python objects.

Code Introspection is used for examining the classes, methods, objects, modules, keywords and get information about them so that we can utilize it.
Introspection reveals useful information about your program’s objects.

Python provides some built-in functions that are used for code introspection.  
Let's start with this lines of code..

```
class Vehicle:
    name = ""
    kind = "car"
    color = ""
    value = 100.00
    def __init__(self, aName, aColor,aKind,aValue):
        self.name = aName
        self.kind = aKind
        self.color = aColor
        self.value = aValue
    def description(self):
        '''returns a description of the vehicle'''
        desc_str = "%s is a %s %s worth $%.2f." % (self.name, self.color, self.kind, self.value)
        return desc_str

def my_function():
    """use triple single or double quotes to add an description."""
    return None


myCar = Vehicle("otto", "yellow", "van",500.0)
```

* **help(obj)**, prints some useful hints on the usage of an object
```
    help(Vehicle)

    Help on class Vehicle in module __main__:
    
    class Vehicle(builtins.object)
     |  Methods defined here:
     |  
     |  description(self)
     |      returns a description of the vehicle
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  __dict__
     |      dictionary for instance variables (if defined)
     |  
     |  __weakref__
     |      list of weak references to the object (if defined)
     |  
     |  ----------------------------------------------------------------------
     |  Data and other attributes defined here:
     |  
     |  color = ''
     |  
     |  kind = 'car'
     |  
     |  name = ''
     |  
     |  value = 100.0

    help(my_function)
    Help on function my_function in module __main__:

    my_function()
        use triple single or double quotes to add an description.
 
```  
* **type(obj)**, returns the type of an object as string.
```
    print(type(Vehicle))
    print(type(myCar))
    print(type(100.0))
    # <class 'type'>
    # <class '__main__.Vehicle'>
    # <class 'float'> 
```
* **dir(obj)**, returns a list of names comprising the attributes of the given object, and of attributes reachable from it.
```
    for s in dir(Vehicle):
        print(s)
    # __class__
    # __delattr__
    # __dict__
    # __dir__
    # __doc__
    # __eq__
    # __format__
    # __ge__
    # __getattribute__
    # __gt__
    # __hash__
    # __init__
    # __init_subclass__
    # __le__
    # __lt__
    # __module__
    # __ne__
    # __new__
    # __reduce__
    # __reduce_ex__
    # __repr__
    # __setattr__
    # __sizeof__
    # __str__
    # __subclasshook__
    # __weakref__
    # color
    # description
    # kind
    # name
    # value
```
* **hasattr(obj, name)**  Return whether the object has an attribute with the given string name.
```
   hasattr(myCar, "description")
   # True

   hasattr(myCar, "Description")
   # False
```
* **id(obj)** returns the *identity* of the object.  
The identity of an object is an integer, which is guaranteed to be unique and constant for this object during its lifetime. Two objects with non-overlapping lifetimes may have the same id() value.
```
   print(id(myCar))
   # 139775667641928
```
* **repr(obj)** returns a printable representation of the object by converting that object to a string.  
> [!NOTE]
> **repr()** calls the objects **\_\_repr__()** method internally.
> As we didn't implement it here, repr() doesn't show too much.
```
   print(repr(myCar))
   # <__main__.Vehicle object at 0x7f200f049ba8>
```














[back to index](README.md)

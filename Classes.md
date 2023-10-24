[back to index](README.md)

# Classes

To create a class, we use the keyword **class**.  
Creating an instance of a class requires the use of brackets: **()** after the class name, optional with argument(s).

```
class MyClass:
    myString = "blah"

    # like a constructor, called once on create instance
    # note the usage of 'self'
    def __init__(self, aString):
        self.myString = aString

    def function(self):
        print("This is a message inside the class.")

# now working with it
m = MyClass("hello world")
m.function()

# This is a message inside the class.
```

* In Python, there is no concept of **Private** members or methods.  
However, in most Python code, a name prefixed with an underscore, For e.g. _aMember should be treated as a non-public part of the class interface.

* Inside a class, any identifier of the form __aMember (two leading underscores) is replaced with _classname__aMember.

* **The \_\_init__() Function**  
Use the **\_\_init__** function to initialize a class. It may assign values to it's members or call methods to enshure the class works as expected. The arguments following the *self* parameter are those passed to a new instance.
> [!NOTE]
>  The \_\_init__() function is called automatically, every time a new instance of this class is created.


* **The \_\_str__() Function**  
Use the **\_\_str__** function to set, how to represent the class as a string.
If we try to print our class, we get the following
```
print(m)
# <__main__.MyClass object at 0x000001B22E6C0470>
```
As we didn't yet implement this function, we get an default. Lets add this function and retry.
```
class MyClass:
    myString = "blah"

    # like a constructor, called once on create instance
    # note the usage of 'self'
    def __init__(self, aString):
        self.myString = aString
        
    def __str__(self):
        return "MyClass(%s)" % self.myString

    def function(self):
        print("This is a message inside the class.")

m = MyClass("hello world")
print(m)
# MyClass(hello world)
```



* **The self Parameter**  
The **first parameter** of any function in the class is **a reference to the current class instance**. Usually, it's called **self** in Python examples.  
   
In C++ for example, the current instance pointer is called **this**, in Lazarus and Delphi the current instance variable is also called **self** and a reference.
But neither require users to put it into the argument list. We could also rename the variable:
```
class MyClass:
    myString = "blah"

    # now i called it 'this'
    def __init__(this, aString):
        this.myString = aString

    def function(this):
        print("This is a message inside the class.")

# now working with it
m = MyClass("hello world")
m.function()
```

* **Inheritance**
  * A derived class will inherit the properties and methods from it's base class.
  * A method in the child class with the same name as a function in the parent class,  
    overrides the inheritance of the parent method.

> [!NOTE]
> The child's \_\_init__() function overrides the parent's \_\_init__() function.
> Therefore, the base classes \_\_init__() should be called inside.

```
class ChildClass(BaseClass):
    def __init__():
        BaseClass.__init__()
    # add child class members here.
    pass
```

If calling members of the base class, we may use the name of the base class, or, the **super()** function.  
For single inheritance, **super()** is just a fancier way to refer to the base type. That way, you make the code more maintainable, for example in case you want to change the base type's name. When you are using super() everywhere, you just need to change it in the class line.  
When using **super()**, a single call will not only automatically call the method of all base types (in the correct inheritance order), but it will also make sure that each method is only called once.
> [!NOTE]
>  If a child class is derived more than once, using **super()** is safer than the name of the base class.

```
class ChildClass(BaseClass):
    def __init__():
        super().__init__()
    # add child class members here.
    pass
```


[back to index](README.md)

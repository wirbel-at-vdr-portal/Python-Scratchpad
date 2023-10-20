[back to index](README.md)

# Classes

To create a class, we use the keyword **class**.

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

* **The \_\_init__() Function**  
Use the **\_\_init__** function to initialize a class. It may assign values to it's members or call methods to enshure the class works as expected. The arguments following the *self* parameter are those passed to a new instance.
> [!NOTE]
>  The \_\_init__() function is called automatically, every time a new instance of this class is created.


* **The \_\_str__() Function**  
Use the **\_\_str__** function to set, how to represent the class as a string.


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


[back to index](README.md)

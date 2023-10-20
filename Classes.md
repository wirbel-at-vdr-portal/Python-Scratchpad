[back to index](README.md)

# Classes

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
Use the **\_\_init__** function to initialize a class.

* **The \_\_str__() Function**  
Use the **\_\_str__** function to set, how to represent the class as a string.

* **The self Parameter**  
The first parameter of any function in the class is a reference to the current class instance.  
Usually, it is called **self** in examples.

Some self explaining name should be used in any case.

[back to index](README.md)

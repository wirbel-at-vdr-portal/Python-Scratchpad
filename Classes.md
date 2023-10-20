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
m = MyClass()
m.function()
```

[back to index](README.md)

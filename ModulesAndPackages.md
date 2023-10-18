# Modules and Packages

Python code needs to be structured, as C++ would do in .cpp files and headers.  
A single file is called a Module, a set of one or more Modules called a Package.

## Using a Module

Modules are used, by making them available.
```
import foo
```
This imports the whole file 'foo.py', similar to #include in C/C++. To use one of the object from there, we have to prefix them with 'foo.', a function 'bar' would be called as foo.bar().

We could also give another name, for example
```
import numpy as np
```
Now, we use the prefix 'np.'.

We could also select which objects to import.
```
from draw import draw_game
```
Now, we may use draw_game(), but this time without the prefix. To import all synbols and objects, we may use
```
from draw import *
```

Sometimes, there's the need to select the imports.
```
# import the draw module
if visual_mode:
    # in visual mode, we draw using graphics
    import draw_visual as draw
else:
    # in textual mode, we print out text
    import draw_textual as draw
```

## Selecting the main() function
```
import (..)

(..)

def main():                                        
    # do some tasks                         
                                                            
# this means that if this script is executed, then 
# main() will be executed                          
if __name__ == '__main__':                         
    main()
```

## Finding function in a Module
To find members of a module, one can use the **dir()** function, after importing the module.

```
import re
find_members = []
for fct in dir(re):
    if "find" in fct:
        find_members.append(fct)
print(find_members)
```

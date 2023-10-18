# Modules and Packages

Python code needs to be structured, as C++ would do in .cpp files and headers.  
A single file is called a Module, a set of one or more Modules called a Package. The module initializes it's internal variables once during load of module.

## Modules
#### Using a Module

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

#### Selecting the main() function
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

#### Finding function in a Module
To find members of a module, one can use the **dir()** function, after importing the module.

```
import re
find_members = []
for fct in dir(re):
    if "find" in fct:
        find_members.append(fct)
print(find_members)
```

Also, the **help()** command may be used.
```
import urllib
dir(urllib)
(..)
help(urllib.urlopen)
```

#### Extending the python module search path
To be able to find modules an Environment Variable called **PYTHONPATH** is used.
```
PYTHONPATH="/foo python game.py"
```

Alternativly, one may use **sys.path.append()**.
```
sys.path.append("/foo")
```

## Modules and Packages delivered with Python
[https://docs.python.org/3/library/](https://docs.python.org/3/library/)

## Packages

A package is actually both, an Namespace *and* an Folder on disk. It may contain packages and/or modules.

As a minimum, it needs to contain the file
```
__init__.py
```
, which indicates this as a Python package. This file might be even empty.
Packages are imported similar like a module.

If we create a directory called foo, which marks the package name,
we can then create a module inside that package called bar.
Then we add the __init__.py file inside the foo directory.

To use the module bar, we can import it in two ways:
```
import foo.bar
from foo import bar
```

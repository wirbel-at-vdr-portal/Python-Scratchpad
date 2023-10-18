# Functions

Functions/Methods are denoted by keyword **def**.  
The returned valued is denoted by **return**, except for generator function, where **yield** is used.

Note the missing curly braces.
```
         def sum(a, b):
             return a + b
```

## Variadic arguments

Sometimes, you don't know exactly the number of function arguments while coding.  
A good example could be the print() function.

In C/C++, you might use something like this
```
#include <cstdarg>
(..)
void variadic_function(size_t count, const char* fmt, ...) {
   std::va_list args;
   va_start(args, fmt);
   int result = 0;
   for(size_t i=0; i<count; i++)
      result += va_arg(args, int);
   va_end(args);
```

Python knows two alternative solutions to get a similar result.
* *args: Receive multiple arguments **as a tuple**
* **kwargs: Receive multiple **keyword arguments as a dictionary**

The name doesn't matter here, *args* is short for *arguments* and kwargs stands for *keyword arguments*.  
You can use any name as long as it is prefixed with * or **.

#### Multiple arguments as a tuple
args should be converted into a [list](VariablesAndTypes.md#Lists), or used as iterable type:
```
def foo(*args):
    print("I got as arguments... %s" % list(args))
    
foo("bla", "blubb", "last arg")
# I got as arguments... ['bla', 'blubb', 'last arg']
```
> [!NOTE]
> You can place *args anywhere in the parameter list.  
> However, any params defined after *args must be specified using the keyword format *parameter_name=value* when calling the function.
> Therefore, I strongly recommend to use *args as the last arg.


#### Multiple arguments as a dictionary

As one can see, kwargs is received as a [dictionary](VariablesAndTypes.md#Dictionaries).
```
def foo(**kwargs):
    print('kwargs: ', kwargs)
    print('type: ', type(kwargs))

foo(key1=1, key2=2, key3=3)
# kwargs:  {'key1': 1, 'key2': 2, 'key3': 3}
# type:  <class 'dict'>
```
In this example, you would get the args by name:
```
    if kwargs.get("key2") == 2:
        print("heyy .. i received a '2' as 'key2')
```

We could pass a *dictionary* directly to such function, if it's prefixed with **:
```
d = {'key1': 1, 'key2': 2, 'arg1': 100, 'arg2': 200}
foo(**d)
```
> [!NOTE]
> A parameter prefixed with ** can only be defined at the end of the parameter list.

#### Example

The foo and bar functions receive a variable amount of arguments (3 or more).  
The foo function returns the amount of extra arguments received.  
The bar function returns True if the argument with the keyword magicnumber is worth 7, and False otherwise.

```
def foo(a, b, c, *args):
    return len(list(args));

def bar(a, b, c, **kwargs):
    if kwargs.get("magicnumber") == 7:
        return True
    else:
        return False;


# test code
if foo(1, 2, 3, 4) == 1:
    print("Good.")
if foo(1, 2, 3, 4, 5) == 2:
    print("Better.")
if bar(1, 2, 3, magicnumber=6) == False:
    print("Great.")
if bar(1, 2, 3, magicnumber=7) == True:
    print("Awesome!")
```

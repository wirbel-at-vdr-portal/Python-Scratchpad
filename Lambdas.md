[back to index](README.md)

# Lambda functions

***Lambda functions** are short inline functions without a name.*

Instead of writing a complete function, functions just needed once might be written as a **Lambda**.
Different languages call them different, sometimes they are also called *anonymous functions*.

So, this code with short function *sum()*
```
def sum(a,b):
    return a + b

a = 1
b = 2
c = sum(a,b)
print(c)
```

could be re-written as
```
a = 1
b = 2
sum = lambda x,y : x + y
c = sum(a,b)
print(c)
```

# Syntax

**lambda** *inputs* : *output*

*inputs* is a comma separated list of arguments  
*output* is the return value.

[back to index](README.md)

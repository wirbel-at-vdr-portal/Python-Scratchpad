[back to index](README.md)

# Decorators
* a **Decorator** is a function that takes a function and extends the behavior of the function without explicitly modifying it.
* a shorter definition: **Decorators wrap a function, modifying its behavior.**
* The wrapper function needs to take the *same arguments* and *return the value of the decorated function*.

```
def my_decorator(func):
    def wrapper():
        print("before \"{}()\" is called.".format(func.__name__))
        func()
        print("after \"{}()\" is called.".format(func.__name__))
    return wrapper

def say_whee():
    print("Whee!")

say_whee = my_decorator(say_whee)

say_whee()

# before "say_whee()" is called.
# Whee!
# after "say_whee()" is called.
```
In effect, the name *say_whee* now points to the *wrapper()* inner function.
```
print(say_whee)
# <function my_decorator.<locals>.wrapper at 0x7f1908335e50>
```

* **The *pie* Syntax**  
We may also write this line shorter, by writing it on top of the function, note the **@my_decorator**. The line **say_whee = my_decorator(say_whee)** gets..
```
    @my_decorator
    def say_whee():
        print("Whee!")
```
* **Using the functools**  
As we have seen before, [Introspection](Introspection.md) doesn't work properly any longer, if using this approach of wrapping:
```
    print(say_whee)
    # <function my_decorator.<locals>.wrapper at 0x7f1908335e50>
```
To fix this, we need to import functools and use **@functools.wraps()**.
```
import functools

def my_decorator(func):
    @functools.wraps(func)
    def wrapper():
        print("before \"{}()\" is called.".format(func.__name__))
        func()
        print("after \"{}()\" is called.".format(func.__name__))
    return wrapper

@my_decorator
def say_whee():
    print("Whee!")

print(say_whee)
# <function say_whee at 0x7f1399fb14c0>
```


[back to index](README.md)

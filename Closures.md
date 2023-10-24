[back to index](README.md)

# Closures
Closures are useful to **avoid global vars**, but rather *hiding those values* them inside a function variable.  
Actually, this is a kind of special Python thing, i guess. It's also a bit hard to understand.

* A [*Nested Function*](Functions.md#Nested%20Functions), which has arguments and returns it's inner function object, may be called a **Closure**.
* A closure is a function whose return value depends on the value of one or more variables that are declared outside the function.
* If used as a **closure**, the function, together with it's arguments, is assigned to a variable

> [!NOTE]
> A nested function contains inside it's function body a function only defined there, the inner function.

> [!NOTE]
> A closure function is able to remember the values which are declared outside the function.

## Examples
We define here a nested function called *outer_function*, which returns it's inner function object called *inner_function*.  
Later, we assign the nested function, together with it's argument to a variable called *x*.  
Now, we can call *x()*, without passing an argument to it, the argument is nowhere else visible.
* Please note the missing brackets at the statement *return inner_function*.
```
def outer_function(aString):
    def inner_function():
        print(aString)
    return inner_function

x = outer_function("This string is only defined here.")

x()
```

The following example is a bit different, now the number, passed later as *power*, is hidden in the variable assignment.
> [!NOTE]
> **pow(number, power)** returns (number ^ power)

```
def nth_power(power):
    def pow_of(number):
        return pow(number,power)
    return pow_of

square = nth_power(2)
cubic = nth_power(3)

print(square(3))
print(cubic(3))
# 9
# 27
```

* **Notes**
   * We can avoid the use of global values  by calling the local function outside its scope, and accessing the enclosed variable outside its scope.
   * Can be used for hiding data in your programs and is highly used while building python microservices.
   * It is used for implementing [**decorators**](Decorators.md) in Python.

[back to index](README.md)

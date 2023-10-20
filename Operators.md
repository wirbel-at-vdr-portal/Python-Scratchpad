[back to index](README.md)

# Operators

* **arithmetic and bitwise**
```
    # add, subtract, multiply, divide
    + - * /

    # modular division
    %

    # exponent (power of), ie. 2 ** 3 is 2^3
    **

    # floor
    //

    # bitwise and/or
    & |

    # bitwise not
    ~

    # xor
    ^

    # shift left, shift right
    >> <<
```
* **assignment**
```
    # assign LHS
    =

    # see arithmetic
    += -= *= /=
    %=
    **=
    //=
    &= |=
    ^=
    >>= <<=  
```

* **logic**
```
    # and/or
    a and b
    a or b

    # not operator
    not a
```
* **comparison**
```
    # equal and not equal
    == !=

    # greater, greater or equal, less, less or equal
    > >= < <=
```
* **in** / **not in** operator, True, if value is (not) present in the object
```
    name = "John"
    if name in ["John", "Rick"]:
        print("Your name is either John or Rick.")
```
* **is** / **is not** operator, True, if (not) same instance of object  
```
    x = 2
    y = 2
    print(x is y)
    # False
```
* **==** operator, True, if same value
```
    x = 2
    y = 2
    print(x == y)
    # True
```

[back to index](README.md)

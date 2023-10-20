[back to index](README.md)

# Working with strings

* **printing strings and variables**
```
print("This line will be printed.")
print("String: %s" % mystring)
print("Float: %f" % myfloat)
print("Integer: %d" % myint)
print("%s is %d years old." % (name, age))
```
* **casting to string**
```
x = str(3)
# x will be '3'
```
* **print a list using the objects 'repr' method**
```
mylist = [1,2,3]
print("mylist = %s" % mylist)
```
* **Length of a string**
```
mylist = [1,2,3]
len(mystring)
# 5
```
* **concatenate strings using '+'**
```
hello = "hello"
world = "world"
helloworld = hello + " " + world
```
* **assign *multiline strings* to a variable using three double quotes**
```
s = """Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."""
print(s)
# Lorem ipsum dolor sit amet,
# consectetur adipiscing elit,
# sed do eiusmod tempor incididunt
# ut labore et dolore magna aliqua.
```
* **multiply strings**
```
print("hello" * 10)
# "hellohellohellohellohellohellohellohellohellohello"
```
* **Get the index of the first occurence of a char in a string**
```
print(mystring.index("o"))
# 4, zero based idx of first 'o'
```
* **Count a certain char in a string**
```
print(mystring.count("l"))
# 2, 'hello' contains 2 chars 'l'.
```
* **substrings**
```
mystring = 'Hello world'
print(mystring[3:7])
# 'lo w' substring starting at index 3, and ending at index 6

print(mystring[::-1])
# '!dlrow olleH' - reverse string

print(mystring[:5])
# 'Hello'

print(mystring[2:])
# 'llo world'
```
* **upper and lower case**
```
print(mystring.upper())
# 'HELLO WORLD!'

print(mystring.lower())
# 'hello world!'
```
* **Check if string begins or ends with substring**
```
mystring.startswith("Hello")
# True
mystring.endswith("asdf")
# False
```
* **Check if "free" is present in the following text**
```
txt = "The best things in life are free!"
print("free" in txt)
# True
```
* **Split string to a list, using a delimiter**
```
mystring.split(" ")
# ['Hello', 'world!']
```

[back to index](README.md)

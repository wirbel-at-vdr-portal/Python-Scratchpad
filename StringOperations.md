[back to index](README.md)

# Working with strings

* **printing strings and variables**
```
print("This line will be printed.")
print("String: %s" % mystring)
print("Float: %f" % myfloat)
print("Integer: %d" % myint)
print("%s is %d years old." % (name, age))

age = 36
name = John
txt = "{} is {} years old."
print(txt.format(name,age))
# John is 36 years old.
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
* **Trim a string using strip()**
```
a = " Hello, World! "
print(a.strip())
# 'Hello world!'
```
* **Check if string begins or ends with substring**
```
print(mystring.startswith("Hello"))
# True
print(mystring.endswith("asdf"))
# False
```
* **Replace parts of string**
```
s = mystring.replace("Hel", "Jap")
print(s)
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
* **Escape sequences**
```
\' 	Single Quote
\" 	Double Quote 	
\\ 	Backslash 	
\n 	New Line 	
\r 	Carriage Return 	
\t 	Tab 	
\b 	Backspace 	
\f 	Form Feed 	
\ooo 	Octal value 	
\xhh 	Hex value
```
* **List of string methods**  
A list with all string functions/methods can be found [here.](https://www.w3schools.com/python/python_strings_methods.asp)

| Method             | Description                                                                                   |
| ------------------ | --------------------------------------------------------------------------------------------- |
| **capitalize()**   | Converts the first character to upper case                                                    |
| **casefold()**     | Converts string into lower case                                                               |
| **center()**       | Returns a centered string                                                                     |
| **count()**        | Returns the number of times a specified value occurs in a string                              |
| **encode()**       | Returns an encoded version of the string                                                      |
| **endswith()**     | Returns true if the string ends with the specified value                                      |
| **expandtabs()**   | Sets the tab size of the string                                                               |
| **find()**         | Searches the string for a specified value and returns the position of where it was found      |
| **format()**       | Formats specified values in a string                                                          |
| **format_map()**   | Formats specified values in a string                                                          |
| **index()**        | Searches the string for a specified value and returns the position of where it was found      |
| **isalnum()**      | Returns True if all characters in the string are alphanumeric                                 |
| **isalpha()**      | Returns True if all characters in the string are in the alphabet                              |
| **isascii()**      | Returns True if all characters in the string are ascii characters                             |
| **isdecimal()**    | Returns True if all characters in the string are decimals                                     |
| **isdigit()**      | Returns True if all characters in the string are digits                                       |
| **isidentifier()** | Returns True if the string is an identifier                                                   |
| **islower()**      | Returns True if all characters in the string are lower case                                   |
| **isnumeric()**    | Returns True if all characters in the string are numeric                                      |
| **isprintable()**  | Returns True if all characters in the string are printable                                    |
| **isspace()**      | Returns True if all characters in the string are whitespaces                                  |
| **istitle()**      | Returns True if the string follows the rules of a title                                       |
| **isupper()**      | Returns True if all characters in the string are upper case                                   |
| **join()**         | Converts the elements of an iterable into a string                                            |
| **ljust()**        | Returns a left justified version of the string                                                |
| **lower()**        | Converts a string into lower case                                                             |
| **lstrip()**       | Returns a left trim version of the string                                                     |
| **maketrans()**    | Returns a translation table to be used in translations                                        |
| **partition()**    | Returns a tuple where the string is parted into three parts                                   |
| **replace()**      | Returns a string where a specified value is replaced with a specified value                   |
| **rfind()**        | Searches the string for a specified value and returns the last position of where it was found |
| **rindex()**       | Searches the string for a specified value and returns the last position of where it was found |
| **rjust()**        | Returns a right justified version of the string                                               |
| **rpartition()**   | Returns a tuple where the string is parted into three parts                                   |
| **rsplit()**       | Splits the string at the specified separator, and returns a list                              |
| **rstrip()**       | Returns a right trim version of the string                                                    |
| **split()**        | Splits the string at the specified separator, and returns a list                              |
| **splitlines()**   | Splits the string at line breaks and returns a list                                           |
| **startswith()**   | Returns true if the string starts with the specified value                                    |
| **strip()**        | Returns a trimmed version of the string                                                       |
| **swapcase()**     | Swaps cases, lower case becomes upper case and vice versa                                     |
| **title()**        | Converts the first character of each word to upper case                                       |
| **translate()**    | Returns a translated string                                                                   |
| **upper()**        | Converts a string into upper case                                                             |
| **zfill()**        | Fills the string with a specified number of 0 values at the beginning                         |



[back to index](README.md)

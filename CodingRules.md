[back to index](README.md)

# Coding Rules

* **line length should be less than 80 chars**
    * if possible, max 72 chars.
    * lines should be wrapped inside
        * parentheses,
        * brackets and
        * braces
    * there's also a possibility to wrap a line using a backslash '\\',  
      but this method is *not preferred*
    * if wrapped, the continued line should start *after* the last operator/brac/bracket,  
      see the color arg:
```
        def __init__(self, width, height,
                     color='black', emphasis=None, highlight=0)
```
* **No semicolon at end of line.**
> [!NOTE]
> The line just ends.

* **Indent is 4 (four) spaces.**
> [!NOTE]
> Tab is accepted, and also other number of spaces.  
> I don't use Tabs because every editor displays them different.

* **Code Blocks** (if/else, loops, functions, ..) are formed by **indent**, instead of curly braces.  
  * top-level functions and class definitions should separated with two blank lines.
  * Method definitions inside a class are separated by a single blank line.
  * Blank lines should be used to indicate logical sections
  * Blank lines may be omitted between a bunch of related one-liners

* **Comments** are done with '#'.   
  Comments can be placed at the end of a line, and Python will ignore the rest of the line

* **multiple Assignments** in a single row are possible:
```
   a, b = 3, 4
   print(a, b)
   # a = 3, b = 4
```

* **function arguments** are comma-separated.

* **Variable names** are case-sensitive.

* **The pass Statement**  
The **pass** statement is used, where no content/code should be done, but for syntax reason an indent is needed.
It just does nothing, but avoiding an python syntax error.  
```
   for x in [0, 1, 2]:
      pass
```

[back to index](README.md)

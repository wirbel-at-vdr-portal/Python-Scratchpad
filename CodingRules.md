[back to index](README.md)

# Coding Rules

* **No semicolon at end of line.**
> [!NOTE]
> The line just ends.

* **Indent is 4 (four) spaces.**
> [!NOTE]
> Tab is accepted, and also other number of spaces.  
> I don't use Tabs because every editor displays them different.

* **Code Blocks** (if/else, loops, functions, ..) are formed by **indent**, instead of curly braces. 

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

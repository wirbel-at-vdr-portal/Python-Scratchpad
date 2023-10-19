[back to index](README.md)

# Loops and Branches

* **if/elif/else**  
    Note the ':' at the end of if statement and missing curly braces.
```
         if (..) :
             # do something
             pass
         elif (..) :
             # do something else
             pass
         else:
             # do another thing
             pass
```
* **for**
```
         for i in [1,2,3]:
             print(i)

         # equal to for i in [0,1,2,3,4]:
         # range returns a new list with numbers
         for x in range(5):

         # dito, but xrange returned an iterator
         for x in xrange(5):
```
* **while**
```
         while STATEMENT:
             #do something
```
* **break/continue**  
as in C/C++
* use of **else** in loops  
**else** is executed, if the checked loop statement is evaluated to False:
```
         count=0
         while(count<5):
             print(count)
             count +=1
         else:
             print("count<5 is no longer True")
         
         # Prints out 1,2,3,4
         for i in range(1, 10):
             if(i%5==0):
                 break
             print(i)
         else:
             print("not printed: loop terminated by 'break'.")
```

[back to index](README.md)

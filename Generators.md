[back to index](README.md)

# Generator functions and generator iterators
If looping over large lists/arrays, not always it is needed to hold the complete array in memory. This is, when generators come into play.
Instead of holding a complete array in memory, a special function is used, which initializes it's internal state on first call and subsequently returns the next value on request.
The for loop receives an interator object, which get it's next value from this special function called generator function.

Some details:

* A function that contains a **yield** statement is called a **generator function**.
* The **yield** statement can only be used inside functions.
* A **generator function** is an ordinary function object in all respects,  
but has the new CO_GENERATOR flag set in the code object’s co_flags member.
* When a generator function is called, the actual arguments are bound to function-local
formal argument names in the usual way, but no code in the body of the function is executed.  
Instead a **generator-iterator** object is returned; this conforms to the iterator protocol, so in particular can be used in for-loops in a natural way.
> [!NOTE]
> The iterator provides a '.next()' method that produces the next item in the sequence each time it is called.
> When no more items are available, either an 'StopIteration' exception is raised or NULL returned.
* Each time the **.next()** method of a **generator-iterator** is invoked, the code in the body of the generator-function is executed until
    * a yield statement is encountered, *or*
    * a return statement is encountered, *or*
    * until the end of the body is reached.
    ```
                def fib():
                a, b = 0, 1
                while 1:
                   yield b          # "yield" expression_list
                   a, b = b, a+b
    ```
* If a **yield** statement is encountered, the state of the function is ***frozen***, and the value of expression_list is returned to .next()’s caller.
* A generator function can also contain **return** statements (but no value/expression allowed to be returned):
    ```
                 return
    ```

> [!NOTE]
> **return** means **"I’m done, and have nothing interesting to return".**
> In such case not always the 'StopIteration' exception may be raised.


[back to index](README.md)

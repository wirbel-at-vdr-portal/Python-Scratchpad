[back to index](README.md)

# Generator functions and generator iterators
If looping over large lists/arrays, not always it is needed to hold the complete array in memory. This is, when generators come into play.
Instead of holding a complete array in memory, a special function is used, which initializes it's internal state on first call and subsequently returns the next value on request.
The for loop receives an interator object, which get it's next value from this special function called generator function.

Some details:

* A function that contains one or more **yield** statement(s) is called a **generator function**.
* The **yield** statement can only be used inside functions.
* A **generator function** is an ordinary function object in all respects,  
but has the new CO_GENERATOR flag set in the code object’s co_flags member.
* When a generator function is called, the actual arguments are bound to function-local
formal argument names in the usual way, but no code in the body of the function is executed.  
Instead a **generator-iterator** object is returned; this conforms to the [iterator protocol](Iterators.md), so in particular can be used in for-loops in a natural way.
> [!NOTE]
> The iterator provides a **\_\_next__()** method that produces the next item in the sequence each time it is called.
> When no more items are available, either an 'StopIteration' exception is raised or None returned.
* Each time the **\_\_next__()** method of a **generator-iterator** is invoked, the code in the body of the generator-function is executed until
    * a yield statement is encountered, *or*
    * a return statement is encountered, *or*
    * until the end of the body is reached.
    ```
                def fib():
                a, b = 0, 1
                while 1:
                   yield b          # "yield" expression_list
                   a, b = b, a+b    # a = b, b += a;
    
                it = fib()
                print(next(it))
                print(next(it))
                print(next(it))
                print(next(it))
                print(next(it))
                print(next(it))
                print(next(it))
                print(next(it))
                # 1
                # 1
                # 2
                # 3
                # 5
                # 8
                # 13
                # 21
    ```
* If a **yield** statement is encountered, the state of the function is ***frozen***, and the value of expression_list is returned to .next()’s caller.
* A generator function can also contain **return** statements (but no value/expression allowed to be returned):
    ```
                 return
    ```

> [!NOTE]
> **return** means **"I’m done, and have nothing interesting to return".**
> In such case not always the 'StopIteration' exception may be raised.

* the returned **Generator iterator** is just a normal **[Iterator](Iterators.md) object:
    ```
                def fib():
                a, b = 0, 1
                while 1:
                   yield b          # "yield" expression_list
                   a, b = b, a+b    # a = b, b += a;
    
                it = fib()

                print(type(it))
                # <class 'generator'>

                help(it)
                #    <class 'generator'>
                #Help on generator object:
                #
                #fib = class generator(object)
                # |  Methods defined here:
                # |  
                # |  __del__(...)
                # |  
                # |  __getattribute__(self, name, /)
                # |      Return getattr(self, name).
                # |  
                # |  __iter__(self, /)
                # |      Implement iter(self).
                # |  
                # |  __next__(self, /)
                # |      Implement next(self).
                # |  
                # |  __repr__(self, /)
                # |      Return repr(self).
                # |  
                # |  close(...)
                # |      close() -> raise GeneratorExit inside generator.
                # |  
                # |  send(...)
                # |      send(arg) -> send 'arg' into generator,
                # |      return next yielded value or raise StopIteration.
                # |  
                # |  throw(...)
                # |      throw(typ[,val[,tb]]) -> raise exception in generator,
                # |      return next yielded value or raise StopIteration.
                # |  
                # |  ----------------------------------------------------------------------
                # |  Data descriptors defined here:
                # |  
                # |  gi_code
                # |  
                # |  gi_frame
                # |  
                # |  gi_running
                # |  
                # |  gi_yieldfrom
                # |      object being iterated by yield from, or None
    ```


[back to index](README.md)

[back to index](README.md)

# Exception Handling

Well, I have so far never seen a program without possible mistakes and errors.  
But - i'm not a programmer at all, i'm just using different computer languages to reach goals..

Many functions raise exceptions, if some inputs are wrong or something really unexpected happens.  
For example, on Delphi and Lazarus, this usually happens, if converting strings to floating point numbers.

System language is En and String contains German decimal point separator - **BOOM**.  
Vice versa dito, System language is De and String contains English decimal point separator - **BOOM**.  
Comma versus dot, once again - aargh.

So functions, which work fine under some circumstances, may fail under wrong circumstances. Usually this stops your program with an stupid message to the user.

So now, there are ways to trap such problems and do something better. Usually, the keyword is **catch** or **except**.

If we would work on a [**pascal** language](https://wiki.freepascal.org/Try/de) (i could have also cited some C/C++ code, it doesnt really matter), it would look like this
```
begin
  ...
  try
    ... // something dangerous here
  except
    ... // okay, something went wrong
  finally
    ... // done in any case.
  end;
  ...
end;
```

In **Python**, the syntax looks somewhat similar. Let's look at this example:
```
actor = {"name": "John Cleese", "rank": "awesome"}

def get_last_name():
    try:
        return actor["last_name"]
    except:
        return "missing key 'last_name'"

# Running code
get_last_name()
print("All exceptions caught! Good job!")
print("The actor's last name is %s" % get_last_name())
```
In the dictionary **actor**, no key called **last_name** was defined.  
So, calling get_last_name() does not succeed, as **actor["last_name"]** cannot return anything useful. Some exception is thrown now.

Without handling it, the program will stop. With our exception, it will continue at least to some point, where a user may read a meaningful messsage, or, continue normally:
```
    All exceptions caught! Good job!
    The actor's last name is missing key 'last_name'
```

We could also try to handle different exceptions differently. The example above just catched *any* exception.  
And it also reported stupid stuff. To be improved! But..  

Capturing just the expected error could look like this
```
    try:
    except KeyError:
        print("This dictionary is key is undefined. Try again...")
```

Capturing/Handling Exceptions is in any programming language so far a loooong and difficult topic, [pls read yourselves](https://docs.python.org/3/tutorial/errors.html#handling-exceptions).

[back to index](README.md)

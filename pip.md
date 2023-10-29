[back to index](README.md)

# Using pip

With **pip**, python packages can be installed.

## Installing pip

1. download [get-pip.py](https://bootstrap.pypa.io/get-pip.py) and save it to your pythons install top folder
2. run get-pip.py in Python.

## Using pip
In a normal command shell (*cmd window* or *xterm*), change to the folder where pip was installed.  
In my case, this is *C:\\Programme\\Python-3.12\\Scripts*. On linux this is most likely not needed as usually program reside in */usr/bin* or a similar which is included in $PATH.

After that, run the install command for the package.

```
pip install <PACKAGE>
```

example
```
pip install scipy
```

> [!NOTE]
> **pip** needs to be run in a command shell, not in a Python environment.
> Execute the command above in a *xterm* or *cmd window*.


[back to index](README.md)

# Module or Import

I edited cube.py, I added a line as shown.

```
cube_text = "Yo, time to cube stuff!"

def cube(x):
    return x*x*x

# Uncomment to test
# print(cube(2))

print(f"This module is called {__name__}") 
```

In Python, there are many variables which use a double underscore, like **\_\_main\_\_** and we call these _dunder variables_. when I run a script, Python sets the dunder variable \_\_**name\_\_** to \_\_**main\_\_** If I run **cube.py**, I get the response&#x20;

```
This module is called __main__
```

When a .py file is imported as a module, the variable \_\_**name\_\_** is set to the name of the module.&#x20;

Examine and try running **project2.py** which calls **cube.py** as a module, I now get the response&#x20;

```
This module is called mylib.cube
```

I now edit cube.py to best practice and test it.

```
cube_text = "Yo, time to cube stuff!"

def cube(x):
    return x*x*x

# Uncomment to test
# print(cube(2))

if (__name__ == '__main__'):
    print(f"This module is called {__name__} and executes as a standalone script")
else:
    print(f"This module is called {__name__} and is being called by another script")
```

If I run the module by itself, it runs the **cube.py** code under the if statement and tells me it is a standalone script.

```
This module is called __main__ and executes as a standalone script
```

If I run **project2.py** it runs the cube.py code under the else statement, and I get the message

```
This module is called mylib.cube and is being called by another script
```

In this way, I set a design pattern for simple scripting. I write my functions and my variables, and I can call then from within the script for basic functionality. If I want to use this script in a different project, as a module, I can include it and only the functions and variables will be accessible when the module is called.

## Exercise

Tidy up **cube.py** and **square.py** so they follow this pattern.&#x20;

Include code under the if statement so you can verify that the modules still work.

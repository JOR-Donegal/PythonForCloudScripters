# Modules

Modules are just .py scripts that can be called from another .py script.&#x20;

I’m going to create two programs&#x20;

project.py is the code for a project I might write.&#x20;

```
"""
project.py
"""
import reusable
print("Running code from the project")
print(reusable.my_square(4))
```

reusable.py is the code for the utilities that I could reuse across multiple projects.

```
"""
reusable.py
"""
def my_square(a: int)->int:
    print("Running code from the module")
    return a*a
```

If I run project.py I get the following output.

```
Running code from the project
Running code from the module
16
```

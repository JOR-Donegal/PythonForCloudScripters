# The Python Standard Library

There are libraries of standard functions available, take a few minutes and review the [documentation](https://docs.python.org/3/library/). Python code in one module gains access to the code in another module by the process of importing it.

As a simple example, if I wanted to do mathematics, I could write functions to derive trigonometry values from first principles. Instead of each individual programmer doing this, we can call the math library from the Python standard library.&#x20;

Create a file called library1.py with the following content, run it to test.

```
import math
print("Input lengths of the two short triangle sides:")
a = float(input("a: "))
b = float(input("b: "))
c = math.sqrt(a**2 + b**2)
print("The length of the hypotenuse to four places is: {hypo:1.4f}".format(hypo=c))
```

The import statement does not make the contents of a module directly accessible. Instead, it creates a namespace, making the contents available. In this case the function _sqrt_ becomes available as part of the math package.

Create a file called library2.py with the following content, run it to test.

```
from math import sqrt
print("Input lengths of the two short triangle sides:")
a = float(input("a: "))
b = float(input("b: "))
c = sqrt(a**2 + b**2)
print("The length of the hypotenuse to four places is: {hypo:1.4f}".format(hypo=c))
```

It is better coding practice to import the specific function you require from a module, allowing the function to be directly accessed within your code. Do not use separate lines, for example, to import trigonometry functions use

```
from math import sin, cos, radians
```

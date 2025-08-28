# Packages

To help organize modules and provide a naming hierarchy, Python has the concept of packages.&#x20;

Packages are just collections of modules, and we normally keep them in a separate directory. We add an empty file with the filename **\_\_init.py\_\_** to signal to Python that this is a package. Under the folder Exercises\_06, I create a folder called **mylib**. Under this folder, I create an empty file called **\_\_init.py\_\_** marking this as a package.&#x20;

I add the following line to \_\_**init**.py\_\_&#x20;

```
copyright = "© JOR 2024" 
```

This is now a global variable accessible throughout. There are much more useful things to put into **\_\_init.py\_\_** but I’ll leave you to figure that out as your coding skills develop.

Under the folder Exercises\_06, I create and test a file called **project1.py** as shown.

```
import mylib
print(mylib.copyright)
```

Under the folder **Exercises\_06\mylib**, I create a file called **square.py** with the following content. I run it to test.

```
square_text = "Yo, time to square stuff!"

def square(x):
    return x*x

# Uncomment to test
print(square(2))
```

Under the folder **Exercises\_06\mylib**, I create a file called **cube.py** with the following content. I run it to test.

```
cube_text = "Yo, time to cube stuff!"

def cube(x):
    return x*x*x

# Uncomment to test
print(cube(2))
```

Back up to the folder Exercises\_06, I create a file called **project2.py** with the following content.&#x20;

Comment out the test lines in **square.py** and **cube.py** and run **project2.py** it to test.

```
import mylib.cube as mycube
import mylib.square as mysquare

print(mycube.cube_text, mycube.cube(3))
print(mysquare.square_text, mysquare.square(3))
```

There are quite a few ideas to take away from this. I can build packages of reusable code, making all my work modular. To reuse this code in a different project, all I need to do is to copy the entire directory. Obviously, I need heavy commenting and comprehensible documentation to make this really work.&#x20;

In the examples, I have used functions, but I've also created and used variables from within my packages. I can use the **as** keyword to reference an imported function and give it any name I like to make it meaningful in my code. Note that I can apply this technique to an entire module also.&#x20;

For example, the graphing library matplotlib is typically imported as plt, making code more economical and readable. In case you are lost, I have used the tree command to map my directory structure for this exercise so far.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

In a large project, I may have several packages which I call, and I need to keep track of all of them.&#x20;

In a recent project I had network utilities, serial utilities, the decoding of UBlox GPS equipment, the decoding of standard marine instruments, all as separate packages.&#x20;

Imagine being able to pull years of work into a project in a modular way, without having to worry too much about interdependencies, it all just works! 

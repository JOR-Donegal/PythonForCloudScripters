# Building a class from scratch

I've been coding in Python for many years, and when I start building an OO project, I use a template.&#x20;

Let us start building a template you can use for future projects. Save this exercise as **oo2.py**

The code below is the simplest I can create!

```
"""
Class template by JOR

Revision History
06OCT22: Alpha
11OCT23: Beta
"""

class MyTemplate():
    pass

# Instantiate the class
my_object = MyTemplate()
# Check the object and type
print(type(my_object))

```

The pass keyword just means “do nothing!”.&#x20;

Next, we will add the _constructor_, a _dunder_ method called **\_\_init\_\_**, passing the **self** keyword to connect this method to the instance of the class.&#x20;

I replace the keyword **pass** with

```
# Constructor, called whenever an instance of the class is created.
    def __init__(self) -> None:
        print("Constructor ran")
```

Objects have attributes, we normally pass these to an object as arguments when we instantiate. I edit the constructor as shown to add two attributes. I pass two argument values to the object and I set them to the object attributes **self.attr1** and **self.attr2**.

```
# Constructor, called whenever an instance of the class is created.
    def __init__(self, attribute1: str, attribute2: bool) -> None:
        print("Constructor ran")
        # Take in an argument and assign it to a meaningful attribute name
        self.attr1 = attribute1
        self.attr2 = attribute2
```

I must also edit the line where I instantiate the class, otherwise I am missing the two positional arguments. This will create a type error.

```
# Instantiate the class
my_object = MyTemplate("John", True)
```

In Visual Studio Code, if I type **my\_object**. I am now offered these attributes.

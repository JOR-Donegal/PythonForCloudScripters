# Anatomy of a simple class

At the start, the anatomy and syntax of a class is not intuitive. Create this example as **oo1.py**

```
"""
Simple Class by JOR, by convention, use camel case to name classes
"""

# Create a class 
class JORzClass():
    
    # Constructor, called whenever an instance of the class is created.
    def __init__(self, my_greeting):
        print("Running constructor for JORzClass")
        # Create attributes and set initial values
        self.message = my_greeting

    def my_method(self):
        print(self.message)

my_class1 = JORzClass("Morning JOR!")
my_class1.my_method()
print(type(my_class1))
```

Firstly, I used the _class_ keyword to define the class JORzClass. Note the use of _camel case_ as the class name and the use of snake case for functions. A function within an object is called a _method_.

The self keyword causes a lot of confusion!&#x20;

It is used to represent an instance (object) of the given class. Remember, we can create many objects from a class, and each will have its own unique attributes. We can use _**self.something**_ to refer to attributes within an instance of an object.&#x20;

The code block **def \_\_init\_\_(self):** is the _constructor_ and is called whenever an instance of this object is created, and the first parameter is _self_. We can also pass parameters to the object at this point, I am using **my\_greeting**. The **print** statement will execute, letting us know that we are running the constructor. For use with the class, I make the attribute **self.message** equal to the parameter **my\_greeting** to use it in the object.&#x20;

When I create a function or method, I pass the _self_ attribute first, letting Python know that it is a method of the class.&#x20;

We saw earlier in this module how to use the **type** method. What do you expect the last line in my script to do?

## Exercise

Write and test a class like the one above and save it as oo1.py&#x20;

In addition to MyClass1, write some code to create and exercise an instance of your class called MyClass2.

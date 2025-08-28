# Methods

Methods are functions within the class which will act on attributes of the class. The simplest implementation just looks like a function. I add the method under the **\_\_init\_\_** code block at the same indentation as the **\_\_init\_\_** method.

```
def my_method1(self):
    if self.attr2:
        print(f"Good morning {self.attr1}")
    else:
        print(f"No greeting {self.attr1}")
```

I can then call that method by the following line at the end of my code.

```
my_object.my_method1()
```

I use the object attributes to make a decision and to give feedback. I could also pass an argument to a method at runtime.

```
def my_method2(self, my_name:str):
    if self.attr2:
        print(f"Good morning {my_name}")
    else:
        print(f"No greeting {my_name}")
```

I can then call this method by the following line at the end of my code.

```
my_object.my_method2(“Slartibartfast”)
```

As demonstrated with functions in previous notes, I can set a default value for an argument.

## Exercise

Create and document a template for your own use, such that whenever you need a simple class, you can just copy the source code. Call it **class\_template.py**. 

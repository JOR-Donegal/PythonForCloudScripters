# Anatomy

A function in Python uses the **def** keyword to tell Python you are writing a function and indentation is used to define the code block that will be run.&#x20;

In parenthesis (), parameters can be passed to the function.&#x20;

The name of the function uses _snake\_case_ and the parenthesis indicate that this is a function. Take a look at [PEP8](https://peps.python.org/pep-0008/).

As with loops, the colon denotes the start of a block.&#x20;

We include a docstring (between """ marks) to explain the function.

```
def name_of_function():
    """
    Simple test function
    """
    print("Yoo hoo!")
```

If I run this, nothing happens. I have created a function, but I have not called the function. I add the following line underneath, with no indentation and rerun.

```
name_of_function()
```

This final line calls the function.&#x20;

Try doing this without the brackets.&#x20;

What happens and why?

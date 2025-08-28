# Passing and returning values

We normally pass variables to a function, and we may refer to them as arguments. Try the example below, where I pass a string to the function.

```
def name_of_function(first_name):
    """
    Simple test function
    """
    print(f"Yoo hoo, hello {first_name}!")

name_of_function("JOR")
```

We normally use the keyword **return** to send the output of a function back to the main program as a variable.&#x20;

I pass the value 5 to the function and then make the return value equal to a, finally I print a.

```
def calculate_circumference(radius):
    """
    Calculate the circumference of a circle based on its radius
    """
    return 2 * 3.142 * radius 

a = calculate_circumference(5)
print(a)
```

If I leave out the value when I call the function, I will get an error:

```
TypeError: calculate_circumference() missing 1 required positional argument: 'radius'
```

One way to avoid this would be to use a default value.

```
def calculate_circumference(radius = 1):
    """
    Calculate the circumference of a circle based on its radius
    """
    return 2 * 3.142 * radius 

a = calculate_circumference()
print(a)
```

I can use the **input** statement to take a value from the operator. Unfortunately, the input keyword returns a string, you cannot add a string to an integer and a float, I also need to do a conversion from string to float.

```
def calculate_circumference(radius):
    """
    Calculate the circumference of a circle based on its radius

    """
    return 2 * 3.142 * radius 

# Get a radius value as a string
r = input("Provide a radius value: ")
# Convert it to a float
r_float = float(r)
# Call the function and create the variable for the return value
a = calculate_circumference(r_float)
print(a)
```

There may be cases where you want to pass an unknown number of arguments to a function. We could use the asterisk symbol **\*** for this.

```
def auto_adder(*my_numbers):
    final_number = 0
    for number in my_numbers:
        final_number = final_number + number
    return final_number

print(auto_adder(12,34,23,66,8,99))
```

In real coding, we can use the **sum()** function, we do not need to use a loop. This was a demonstration only! 

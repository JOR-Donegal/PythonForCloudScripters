# Raising Exceptions

You can also raise an exception when validating input.

```
# Take an input number as a string and convert it to an integer
my_value = int(input("Enter an integer greater than 0"))

if my_value <= 0:
    raise Exception("Values must be > 0")
else:
    print("Validation checks passed")
```

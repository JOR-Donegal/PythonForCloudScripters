# Scope

When we create variables in any programming language, they are normally the concatenation of the variable and its namespace. We say that a variable has _scope_.&#x20;

Run the following code with a nested function.&#x20;

What results do you get and why?

```
my_string = "global"

def my_function():
    my_string = "enclosing"
    def nested_function():
        my_string = "local"
        print(my_string)
    nested_function()
    return my_string

# Print the variable my_string
print(my_string)
# Print the output of the function, my_function
print(my_function())
```

Python has a hierarchy with which it looks for variables as _LEGB_.

1. **L**ocal names assigned in a function and not declared as global
2. **E**nclosing function locals, names in an enclosing function where we next functions
3. **G**lobal names assigned at the top level of a Python module, or declared as global
4. **B**uilt in names in Python, do not override these!

Using the **global** keyword, I can change the global variable name from within a function.

```
my_string = "global"

def my_function():
    global my_string
    print(f"At the moment, my_string is: {my_string}")
    my_string = "mangled!"

my_function()
print(f"Now the global value of my_string is: {my_string}")
```

Avoid using the global keyword unless you have a very specific reason to. Its much less confusing to change a module level variable using the return value of a function.

## Exercise 1

Briefly explain and comment this code.&#x20;

What values in the final statement will result in the function returning True?&#x20;

Why?

```
def divisible(numerator: int, denominator: int)->bool:
    return numerator % denominator == 0

print(divisible(30,4))
```

## Exercise 2

Briefly explain and comment this code.&#x20;

Why do you get the value None?&#x20;

What values in the final statement will result in the function returning True?&#x20;

Why?&#x20;

Can you modify this function to return False instead of None if the value is not found?

```
def find_num(number_list: list, number: int)->bool:
    for iterate_number in number_list:
        if iterate_number == number:
            return True
        else:
            pass

result = find_num([1,2,3,4,5,6,7,8], 9)
print(result)
```

## Exercise 3

Write a function to search for an even number in a list of numbers.&#x20;

Return True if you find an even number.&#x20;

Return False if you do not.&#x20;

Write a lambda function to calculate the volume of a cylinder.

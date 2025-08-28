# List Comprehensions

In previous notes we looked at data structures such as lists. Sometimes you may find yourself using a loop to populate a list.&#x20;

For example

```
my_list = []
my_string = "Morning Folks!"
for letter in my_string:
    my_list.append(letter)

print(my_list)
```

Give this a go, the final result I got was as expected \['M', 'o', 'r', 'n', 'i', 'n', 'g', ' ', 'F', 'o', 'l', 'k', 's', '!']&#x20;

In a list comprehension, we collapse the block of code to

```
my_string = "Morning Folks!"
my_list = [letter for letter in my_string]
print(my_list)
```

And we get the same result!&#x20;

The comprehension takes an element, for an element, from a string or other iterable object.&#x20;

Try

```
my_list = [number for number in range(0,20)]
print(my_list)
```

We can perform operations on variables, for example

```
my_list = [number * 10 for number in range(0,20)]
print(my_list)
```

How about adding an if statement to further filter the output?

```
my_list = [number * 10 for number in range(0,20) if number < 10]
print(my_list)
```

Final scenario.&#x20;

I have a list of depths in feet on a US Sonar log file and I want to convert them to meters, rounded to 2 decimal places.

```
conversion = 0.3048
my_depth_in_feet = [12.3, 13.8, 15.3, 12.1, 8.8]
my_depth_in_meters = [(round(depth * conversion, 2)) for depth in my_depth_in_feet] 
print(my_depth_in_meters)
```

We can create complicated comprehensions with if, else and nested loops. I never do this! If a list comprehension makes your code more readable, use it.&#x20;

If it makes it hard to understand, don’t!&#x20;

## Exercise&#x20;

I have an American air conditioner system returning temperatures, but I need the temperatures in standard units. Create a list of 10 values in degrees Kelvin. Write a code block to print these values in Celsius and Fahrenheit.

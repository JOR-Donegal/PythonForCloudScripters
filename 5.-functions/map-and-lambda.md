# Map and Lambda

## Map()

The map() function provides us with a way to iterate through an iterable object without using a loop. I only pass the name of the function to map, and it has an anatomy like

```
map(function, iterable)
```

As an example

```
def double_number(n: int)->int:
    """
    Simple function to double a number
    """
    return n+n

# Create a list of numbers for testing
my_numbers = [1,2,3,4,5]
# Map my_numbers to the double_number function, return type is map
result = map(double_number, my_numbers)
# Print a list of the map 
print(list(result))
# Or iterate through it
for item in map(double_number, my_numbers):
    print(item)
```

## Lambda

A lambda function is like a single-use function which is not needed perpetually, and it has an anatomy like

```
lambda arguments : expression
```

For example

```
circumference = lambda radius : 2 * 3.142 * radius
area = lambda radius : 3.142 * radius * radius
radius = 5
print(circumference(radius), area(radius))
```

Give this a try!&#x20;

I use lambdas for very simple functions only.&#x20;

With a complex function, they are less readable than the full function.

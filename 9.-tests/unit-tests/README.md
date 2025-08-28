# Unit Tests

There is a built-in unit testing library. This allows you to provide input to programmes and check the responses. Up up to now, we have tested our code by

1. Casually including some lines at the end of the program.
2. Using the **\_\_main\_\_** design pattern
3. Calling functions from **main.py**&#x20;

I write a file called formater.py as below.

```
def convert_upper(my_text):
    return my_text.upper()

def convert_lower(my_text):
    return my_text.lower()

def convert_capital(my_text):
    return my_text.capitalize()
```

I add the following lines to test.

```
print(convert_lower("John ORaw"))
print(convert_upper("John ORaw"))
print(convert_capital("dUBLIN"))

```

That all works fine, its just not very scalable or methodical.

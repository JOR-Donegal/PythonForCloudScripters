# Floating Point Errors

Computers are not very good with floating point numbers, a CPU is an integer processor.&#x20;

```
C:\Users\JohnO>python
Python 3.11.0 (main, Oct 24 2022, 18:26:48) [MSC v.1933 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> a = 0.1 + 0.1 + 0.1
>>> print(a)
0.30000000000000004
>>>
```

Have a read [here](https://docs.python.org/3/tutorial/floatingpoint.html) to understand why and what the implications of floating point errors are.

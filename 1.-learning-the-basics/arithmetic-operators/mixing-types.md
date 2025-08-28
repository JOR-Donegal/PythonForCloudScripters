# Mixing types

I cannot add a number to a string, for example the following line makes no sense.

```
C:\Users\JohnO>python
Python 3.11.0 (main, Oct 24 2022, 18:26:48) [MSC v.1933 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> a = "JOR" + 3/2
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate str (not "float") to str
>>>
```

This will result in a **syntax error**, and Python will give you feedback because you wrote it wrongly.

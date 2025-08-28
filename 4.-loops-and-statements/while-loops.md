# While Loops

Start by creating a new file called **my\_while.py**

While loops will continue to execute a block of code so long as the condition is true.&#x20;

The syntax is:

```
while condition:
    # Execute code block
else:
    # Execute something else
```

I give a very simple example below. Run this and understand the result.

```
x = 0
while x < 10:
    print(f"X is = {x}")
    x = x + 1
else:
    print(f"As x is now = {x}, we are all finished")
```

When we want to increment a variable, we used **x = x + 1**

In Python, it is more common to do this as an increment using: **x += 1**

If you make a mistake in your code and create a never-ending loop, you can exit it by pressing **\[ctrl]\[c]**.

Sometimes I want a program to run forever. I can do this by enclosing the code in a never-ending while block, using **while True:** or **while 1:**

```
print("press [ctrl][c] to exit")
while 1:
    pass
```

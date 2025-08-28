# Precedence

Calculations will yield a different result depending on the order in which we do the calculation. In standard mathematics, we have established **laws of precedence**, so the calculations are always done consistently in the **order** shown below.&#x20;

| **Order** | **Symbol** | **Function**   |
| --------- | ---------- | -------------- |
| 1         | \*\*       | Exponentiation |
| 2         | \*         | Multiplication |
| 2         | /          | Division       |
| 2         | %          | Modulus        |
| 2         | //         | Floor Division |
| 3         | +          | Addition       |
| 3         | -          | Subtraction    |

In coding, the normal mathematical laws of precedence apply, so be careful to use brackets if the order of calculation requires it. The operators are evaluated in the order shown and then from left to right. I prefer to use brackets to make this explicit.

```
C:\Users\JohnO>python
Python 3.11.0 (main, Oct 24 2022, 18:26:48) [MSC v.1933 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> 10 * 2 + 3 * 5
35
>>> 10 * (2 + 3) * 5
250
>>>
```

If you intended to use the first example, but use the second instead, we would refer to that as a **semantic error**. Very simply, you did not think the mathematics through. Python cannot read your mind and will not show this as an error.&#x20;

We will talk about testing much later.

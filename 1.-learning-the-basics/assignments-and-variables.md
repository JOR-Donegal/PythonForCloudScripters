# Assignments and Variables

Any computer program could be simply described as a sequential list of commands acting on data. When we store data in a memory location with an identifier so we can access it, we have created a **variable**.&#x20;

In mathematics, an **assignment** occurs when you create a variable and assign it a value using an  **operator**. A variable points at a location in memory where the value is stored.&#x20;

| Variable | Operator | Value |
| -------- | -------- | ----- |
| a        | =        | 3     |

In Python, the format is

```
a = 2
```

Sometimes the right side of the equation could be a calculation, this will be evaluated before it is assigned. For example, in the line

```
a = 1 + 2
```

the variable _a_ will evaluate as 3.

Variable names must start with an underscore or a letter and the Python Style Guide recommends **snake\_case**, which uses underscores to divide words in a variable name. Other possibilities are to use **camelCase** or **MixedCase**. Which one you use is less important than using one, consistently throughout a project. Lower case is generally used, but you will see some variations later, for example when you are using global variable names. I use long, descriptive names, for example **latitude\_in\_decimal\_degrees**.&#x20;

Do not use any built-in key words as variable names. Look these up now and document them.

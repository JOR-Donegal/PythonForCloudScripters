# Loops

As a general guide, loops keep repeating themselves until the condition to stop the loop is met.

## For Loops

There is a technical term called iteration. If I have a shopping list, I can walk down the aisles of the supermarket, iterating through the shopping list, until each of the items is in my basket. We can use loops to iterate through items (lists, sequences) and execute a block of code utilizing each item. The loop finishes when a condition is met.

1. Start by creating a new file called **my\_for.py**
2. Never use an actual Python keyword as a file name!
3. I entered the following code.&#x20;
   1. I created a list called iterable\_variable and populated it.
   2. The next line means, for every item in iterable\_variable, execute the indented code.

```
iterable_variable = [1,2,3,4,5,6]

for item in iterable_variable:
    # For each item, execute this code block
    print(item)
```

By default, print appends a **\n** character, so each item appears on its own line.

How about I combine some things we have learned so far? Examine the if statement and see if you can understand what it does. Can you make this code print out even number only?

```
iterable_variable = [1,2,3,4,5,6]

for item in iterable_variable:
    if item %2 != 0:
        print(item)

```

I can add each number in the list.

1. First, I need to define a variable to hold the result.
2. Then I can iterate through the list, adding for each item in iterable\_variable
3. Finally, I print the total out, at the same ident level as the for statement, so it will only run after the for loop has completed.
4. What happens if you ident the print statement? Why?

```
iterable_variable = [1,2,3,4,5,6]
total = 0

for item in iterable_variable:
    total = total + item

print(total)
```

Indentation is rather important, it determines programme flow.

We can use any legal variable name and we do not have to create a variable to iterate over. Try this code below using your own name.

```
# Define a string to iterate over
for this_letter in "John ORaw":
    # Specify which letter to test for
    if this_letter == "J":
        # Found the test letter
        print(f"Woo hoo, found a {this_letter}!")
        # Exit the current loop
        break
    else:
        # Didn't find the test letter
        print(f"Aww man, I didn't want a {this_letter}!")

```

Now change the test letter to a lower case “j” and rerun.&#x20;

Note how I used the keyword break above. We have some special keywords for all our Python loops.&#x20;

* break exists from the current loop and ends it immediately&#x20;
* continue goes to the top of the current loop, skipping to the next iteration&#x20;
* pass does absolutely nothing, I use it as a placeholder when I am writing code, and I will do the code block later.&#x20;

We can end an entire program using **sys.exit()**, but we will talk about that later.  

Try the code below, make sure you understand what is happening.

```
my_list = [1,2,3,0]

for my_number in my_list:
    if my_number == 1:
        pass
    if my_number == 2:
        continue
    if my_number == 3:
        print(f"Found the number {my_number}")
    if my_number == 0:
        break
```

Note that we can iterate through any sequence, for example a tuple. We can also nest tuples in lists, etc. Try the code below.

```
list_of_tuples = [(1,2), (3,4), ("A", "B")]
for item in list_of_tuples:
    print(item)  
```

How about this code? Read a little about tuple unpacking to see what the term means.

```
# Tuple unpacking
list_of_tuples = [(1,2), (3,4), ("A", "B")]
for a,b in list_of_tuples:
    print(a)  
    print(b)

```

Sometimes in my networking or serial code, I get a tuple returned with multiple properties, but always in the same order. I can just extract the property I want based on its order.

When I started programming using languages like C and Basic, we used for loops very differently, with start, stop and step parameters. In Python, the range() function returns a range object (we will look at objects in a later session) which is like a sequence. In Python, I can use a for loop with a range(start, stop, step) to emulate this.

```
for index in range(1, 100, 5):
    print(index)
```

This can be a useful way to step through data with fixed fields, or with information in fixed positions.

## Exercise

Create a dictionary as shown, do not worry about what it means, its a few lines from a network scanner.

scan = {"192.168.3.10": "80", "192.168.3.11": "443", "192.168.3.55": "22"}

1. Iterate through this dictionary as you have been shown. What is the result? What are you missing?
2. Instead of iterating through scan, try iterating through scan.items(), What is the difference?
3. Finally, we can address each item in the tuple. Here is an extract from some real code written for a network security scan. Try it!

```
scan = {"192.168.3.10": "80", "192.168.3.11": "443", "192.168.3.55": "22"}
for ipv4, port in scan.items():
    print(f"Found a service on {ipv4} at {port}")
```

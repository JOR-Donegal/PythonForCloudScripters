# If, Elif and Else

The first conditional statement we will consider is the if statement. This is also one of the oldest statements used in high level languages.

1. I have opened Visual Studio Code and created a new directory C:\Python\Exercise\_04
2. I have created a file, my\_if.py
3. Over the next few minutes, I am going to build a code template I can use in any project.
4. In Python, control flow is determined by colons (:) and indentation. Indentation must be perfect, or you will generate errors when you try to run the program. Way back, people used spaces (how many?) and tabs interchangeably.&#x20;

The style guide [PEP8 ](https://peps.python.org/pep-0008/)tells us to use four spaces for indentation.&#x20;

The syntax is

```
if condition1:
    # Execute code
elif condition2:
    # Execute code
else:
    # Execute other code
```

If a condition1 is met, code is executed until the end of the if indented block.&#x20;

If the first condition is not met, condition2 is checked, if it is, code is executed until the end of the **elif** indented block. You may have many **elif** conditions, but once one is met, its code block will be executed and the programme will move beyond the **if, elif, else** code block.&#x20;

If no condition is met, the **else** code block is executed. I pulled an example from a program I wrote c. 2015 to decode some Smart Grid data. Note that I put enough comments in that even now, I can figure out what I did and why.

```
# First byte AA flags start of sequence
# Now test the second byte to identify the frame type
if SecondByte == 0x00:                                   
    # AA0x Data frame
    self.FrameType = 'Data'      
elif SecondByte == 0x10:                                
    # AA1x Header frame
    self.FrameType = 'Header'      
elif SecondByte == 0x20:                                
    # AA2x Configuration Frame1
    self.FrameType = 'ConfigurationFrame1'                
else:                                                                    
    # Corrupt data?
    self.FrameType = 'Unknown'
```

Take note of the indentation, the location of colons and the conditions. 

## Exercise

Try the following and save as **my\_if.py**

```
a = True
b = True
c = True

if a:
    print("a was true")
elif b:
    print("b was true")
elif c:
    print("c was true")
else:
    print("None of our boolean variables were true")

```

Run this code, then:

1. Set a = False and run, examine the output
2. Set b = False and run, examine the output
3. Set c = False and run, examine the output&#x20;

Notice the limitations, once the first test is met, the **if/elif/else** code block terminates.&#x20;

I wrote the following code snippet to check more complicated Boolean conditions. Play around with the numbers and conditions so you can understand what I did.

```
if (3<2) and (5<9):
    print("Yup!")
else:
    print("Nope!")
```

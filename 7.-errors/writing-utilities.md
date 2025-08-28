# Writing Utilities

I’m going to take some code from Exercise\_06 and I’m going to start building up some OS utilities. Save the new file under Exercises\_07 as **detect\_working\_directory.py**&#x20;

Consider the changes.

1. I’ve added an import to the sys and os libraries.
2. I’m going to define global variables which I can use anywhere in the code.
3. I am going to exit the programme unless I detect Windows or Linux.
4. I have added a simple function to get my working path and print it for diagnostics.

```
"""
directory_utilities.py
By: JOR
Date: 01OCT22
"""

import os, platform

# Define global variables
current_working_directory = None

def detect_os()->str:
    # Detect the OS in use
    return platform.system()

def detect_working_directory()->str:
    # Returns the directory this script was run from
    return os.getcwd()

if (__name__ == '__main__'):
    print(f"This module executes as a standalone script")
    
    # Check the OS in use, lower case
    my_os = detect_os()
    my_os = my_os.lower()
    
    # Parse the response, only check for Windows and Linux
    if my_os == "windows":
        print("Your system is Windows")
    elif my_os == "linux":
        print("Your system is Linux")
    else:
        print(f"Cannot continue, unidentified system = {my_os}")
        sys.exit()

    # Get the current working directory
    current_working_directory = detect_working_directory()
    print(f"You are coding in: {current_working_directory}")

else:
    print(f"This module is called {__name__} and is being called by another script")

```

So far, I'm just taking responses from the operating system. the if statement is now only checking for Linux and Windows. The else option deals with any other OS and exits the program.

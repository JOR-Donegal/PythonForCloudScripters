# Utilities

I steal some code from Exercises\_7, to determine what operating system I’m working with. I save this under **Project\Source**

```
"""
directory_utilities.py
By: JOR
Date: 01OCT23
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

I create a file **main.py** under the Project directory.

```
"""
main.py
By: JOR
Date: 20OCT23
"""

from Source.directory_utilities import detect_os, detect_working_directory
print(detect_os())
print(detect_working_directory())        

```

I run **main.py**

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

This is a nomal anatomy for my projects. I have a small and simple programme called **main** which only includes the programme flow. Often, this will be a **while True:** loop, continuing on until I do a break from the keyboard with **\[ctrl]\[c]**. All my reusable code can sit in the **Source** directory. On complex projects I may have multiple source directories with reusable code from many different projects.

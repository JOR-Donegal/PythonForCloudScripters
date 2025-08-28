# Data Logfiles

I need to detect my OS before I start my logfiles program.&#x20;

The following code from Section 6 is saved as **Exercises\_10/os\_utilities.py**

```
""""
OS utilities, forked from the Comm module of SD-Node, written c. 2017
Tested with Python >=3.6
By: JOR
    v0.1    26AUG21     
"""
import platform

def detect_os()->str:
    # Detect the OS in use
    return platform.system()

if (__name__ == '__main__'):
    print(f"This module is called {__name__} and executes as a standalone script")
    
    # Check the OS in use, lower case
    my_os = detect_os()
    my_os = my_os.lower()
    
    # Parse the response
    if my_os == "windows":
        print("Your system is Windows")
    elif my_os == "linux":
        print("Your system is Linux")
    elif my_os == "darwin":
        print("Your Apple system is MacOS")
    elif my_os == "cygwin":
        print("Your Apple system is MacOS")
    elif my_os == "aix":
        print("Your IBM system is AIX")
    else:
        print(f"Unidentified system = {my_os}")
else:
    pass
    #print(f"This module is called {__name__} and is being called by another script")

```

Note that at the end, I have commented out my diagnostic text and added a pass statement. Interestingly, I can copy and paste from the **if (\_\_name\_\_ == '\_\_main\_\_'):** section if I want to use functions in another program.

When I’m saving logfiles, I like to have unique filenames. I wrote the following file long ago in my utilities package and I am copying it now as **Exercises/file\_utilities.py**

```
""""
File utilities, forked from the Comm module of SD-Node, written c. 2017
Tested with Python >=3.6
By: JOR
    v0.1    26AUG21     
"""

from datetime import datetime as dt
import sys, csv

def path_name():
    # Operating system dependent stuff
    this_os = sys.platform
    if this_os == 'win32':
        return './logfiles/'
    elif this_os == 'linux':
        return '/home/pi/logfiles/'
    else:
        print(f'Unsupported OS: {this_os}')
        exit(0)

def log_file_name(extension):
    """
    Create a file name in the logfiles directory, based on current data and time
    Requires the computer to have an RTC or synched clock
    """
    now = dt.now()
    # Linux
    file_name = '%0.4d%0.2d%0.2d-%0.2d%0.2d%0.2d' % (now.year, now.month, now.day, now.hour, now.minute, now.second)
    return file_name + extension

if (__name__ == '__main__'):
    print(f"This module is called {__name__} and executes as a standalone script")
    log_path = path_name()
    filename = log_file_name(".log")
    print(log_path + filename )
else:
    pass
    #print(f"This module is called {__name__} and is being called by another script")

```

The path that I use to store my log files is dependent on the operating system I'm using. As you can guess from the Linux path, this is intended for a Raspberry Pi.&#x20;

Once again, I can copy and paste from the **if (\_\_name\_\_ == '\_\_main\_\_'):** section if I want to use these functions in another program.

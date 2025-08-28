# Writing Main

I can bring all this together now in a **main.py** program.

```
from file_utilities import path_name, log_file_name
from os_utilities import detect_os


# Check the OS in use, and figure out a log file name and path
this_os = detect_os()
log_path = path_name()
filename = log_file_name(".log")
print(log_path + filename )

```

On my Windows machine, this returns **./logfiles/20221012-142149.log**&#x20;

In three lines of code, I reliably get a logfile name and path in any supported OS.&#x20;

Interestingly, if I sort by filename, the logfiles will sort in chronological order.&#x20;

I can use the above code for any project where I need to log data. This is my own standard for logging instrumentation data, you can find this code in many places in the real world!&#x20;

Now I need to log something useful, in this example I’m going to log CPU information.

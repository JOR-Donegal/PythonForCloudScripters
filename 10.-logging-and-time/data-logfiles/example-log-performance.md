# Example - Log Performance

I need to do&#x20;

```
pip install psutil 
```

in the terminal to get the library I need.&#x20;

Do some reading about this library [here](https://pypi.org/project/psutil/). &#x20;

In **os\_utilities** I add the line&#x20;

```
import psutil 
```

beside the other import statements.&#x20;

Then I add a function **cpu\_load()** in **os\_utilities.py** to gather useful information, it almost doesn’t matter what I gather, this is meant as an example only.

```
def cpu_load():
    # Return significant numbers relating to the CPU
    #print(f"Number of CPUs: {psutil.cpu_count()}" )
    #print(f"CPU load: {psutil.cpu_percent()}")
    return(psutil.cpu_count(), psutil.cpu_percent())
```

I used the print statements for testing and then commented them out.

Back in Section 7 we learned how to do basic file handling, I’m going to reuse that code now. I modify my main program and call it **cpu\_log.py** and I change the file extension to “.csv”.

I use **time.sleep** to create a one second delay.

If you have a program running in an endless loop, in Visual Studio Code, click into the terminal window and press **\[ctrl]\[c]** to exit. If you run code in the Linux or Windows terminal window, the same approach works.

I wrote edited **main.py**

<pre><code>""""
Main.py

Tested with Python >=3.6

By: JOR
    v0.1    26AUG21     

"""
<strong>from file_utilities import path_name, log_file_name
</strong>from os_utilities import detect_os, cpu_load
from time import sleep

# Check the OS in use, and figure out a log file name and path
this_os = detect_os()
log_path = path_name()
filename = log_file_name(".csv")

# Loop forever
while True:
    # Sleep for 1 second
    sleep(1)
    # Get a time stamp for this line
    timestamp = log_file_name("")
    # Get some information
    information = cpu_load()
    # Create a line for the logfile, convert the integer values to string
    logline = timestamp + ":" + str(information[0]) + "," + str(information[1]) + "\n"
    # Now write it to the logfile
    try:
        with open(filename, "a") as file_handle:
            print(f"logging to {filename}")
            file_handle.write(logline)
    except IOError as err:
        print(f"IOError was {err}")
    except EOFError as err:
        print(f"End of file error was {err}")
    except OSError:
        print("OS Error")
    except:
        print("General Error")

</code></pre>

Note that I used the **log\_file\_name()** function with no extension to generate a timestamp for each line in the logfile. Read and understand this program, then run it.

## Testing

Run the code for a few minutes to verify it saves data once per second. Do that more than once, verify that a new logfile is created each time.&#x20;

A comma space delimited file is a typical way to exchange sensor data.&#x20;

You should be able to open and process the log file in Excel, check that now.

# Basic file handing

One of the things we must do in many programs, is to open a file for reading or writing. There are four modes in which you can open a file:&#x20;

* Read = “r”&#x20;
* Write = “w”&#x20;
* Append = “a”&#x20;
* Read and write = “rw”

Try the following as **file\_handler.py**

```
my_filename = "logfile.txt"

try:
    with open(my_filename, "a") as file_handle:
        print(f"Writing a test line to {my_filename}")
        file_handle.write("Test line")
except IOError as err:
    print(f"IOError was {err}")
except EOFError as err:
    print(f"End of file error was {err}")
except OSError:
    print("OS Error")
except:
    print("General Error")
else:
    print("File created")
finally:
    print("Finishing up!")
    # close not needed because with statement
    # file_handle.close()
```

Notice the use of the with statement, this has special characteristics for use with streaming IO, files, serial ports etc.&#x20;

Try this code out, it should create a log file and give you messages for each section which runs.

&#x20;When you open a file, you can open to write (”w”) or read (“r”). In the open command, change the “w” to an “r”, you are now opening the file read only. When you attempt to write to the file, this will generate an operating system error. But more specifically, it generates an IO Error.&#x20;

In this example, I take the error message back and provide it to the user. In this example I specifically handle some common file related errors. Any other error is handled as a general error using the except keyword. Review these [examples](https://docs.python.org/3/tutorial/errors.html).

# Writing Docstrings

In these notes, I am mostly interested in writing scripts. A script docstring is placed at the start of the file and should explain to users how to use the script. Sometimes we need to set the variables we were acting on at runtime. We refer to these as **arguments**. If you intend to pass arguments to the script, detail them here. If the script has **return** values, they are similarly detailed here.

```
'''
Script: TCPClient.py
By: JOR
Purpose: sends TCP packets with static text and a time stamp to a particular address and port.
Prerequisites: ensure the sockets library is installed
Tested: on Python v3.10.4 under Windows 10

Revision History:
Alpha version:      13FEB22

Notes:
Do not edit the values in this script, all fixed settings are maintained at .\settings\tcp.py
This script has no error handling, by design.
'''
```

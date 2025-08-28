# Template

The final thing I need in a every project is a template with my header, take a look at [PEP257](https://peps.python.org/pep-0257/).

There are certain properties I also might want to define for any project, I gave this example in Section 2. These are often referred to as module metadata. If you are using source control like GIT, this may be a bad idea.

```
__author__ = "John ORaw"
__contact__ = "barney@disney.com"
__copyright__ = "Copyright $YEAR, JOR"
__date__ = "12FEB23"
__deprecated__ = False
__license__ = "GPLv3"
__status__ = "Production"
__version__ = "1.2.1"
```

I will then run with the simplest possible header to each file. Below is an example of **main.py** in one of my projects.

```
#!/usr/bin/env python3

""""
This file: Main routine for Binary Mux
Origin: Forked from the Comm module of SD-Node, written c. 2017
Description: Takes a serial input and logs, optionally forwards to a UDP address:port
Compatibility: Tested with Python >=3.6

By: JOR
    v0.1    26AUG21     Modified NMEAMux to log UBX, RTCM, AIS
    v0.2    27JUL23     Modified as a general RTCM test suite

"""
```

## Exercise

Create a folder called **Templates** within your project.

Save a header file in there that you can use as an inital file for anything you write.

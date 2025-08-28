# File Headers

If you are writing a simple script, one file, then the documentation lives in the script.

&#x20;If I am running my script under Linux directly, I may start with a _shebang_ (#!)

```
#!/usr/bin/env python
```

During a class in October 2023, I discovered a downside of this. If you write a python program in Windows, there is a **\[cr]\[lf]** at the end of every line. If you write in Linux, there is only a **\[lf]**. Python does not care and you can run either file type without issue. However, if you use the shebang directive above, it needs the python file to be in a Linux format. This was all news to me!

Next, I will insert a short docstring, you can find a related [PEP](https://peps.python.org/pep-0257/)

```
""" scanner.py: scans the local subnet using ping. """
```

If this is a single file, I do not have information elsewhere identifying the author, license etc. In Python we use double underscore or **dunder** variables to identify variables which need to be treated in a special way.

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

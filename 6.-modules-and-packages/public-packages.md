# Public Packages

A programmer can write code for their use, or they take it publicly available for anybody to use. The _Package Installer for Python_ (PIP) is the standard tool used to find and install these packages. This is installed when you install Python.&#x20;

Read the [documentation](https://packaging.python.org/en/latest/tutorials/installing-packages/).&#x20;

There is an index that pip can access called the Python Package Index or PyPi.&#x20;

At the command prompt in Windows, type **pip -h**&#x20;

In Linux or Apple, this may be **pip3 -h**&#x20;

Once you confirm pip is installed, update it by using

```
pip install --upgrade pip
```

One of the most used and useful external packages in Python is numpy, however, it is not included in the base libraries.&#x20;

Open a new file under Exercises\_06 as public.py and enter the line&#x20;

```
import numpy 
```

VSC will underline **numpy** as it does not have a package of that name. If you run this, it will generate an error.&#x20;

In the VSC terminal window, I type&#x20;

```
pip install numpy 
```

I restart VSC and numpy is recognized!&#x20;

You can also remove packages by typing&#x20;

```
pip uninstall package_name 
```

You can list the packages to install by typing&#x20;

```
pip list 
```

You can get information about a package by typing&#x20;

```
pip show package_name 
```

Work your way through pip's [getting started](https://pip.pypa.io/en/stable/getting-started/).

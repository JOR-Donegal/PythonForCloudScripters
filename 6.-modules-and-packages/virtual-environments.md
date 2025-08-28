# Virtual Environments

On recent versions of Python [PEP704](https://peps.python.org/pep-0704/) is enforced and we must use Virtual Environments.

A virtual environment in Python is a self-contained directory that contains a specific Python interpreter and installed dependencies. It helps isolate Python projects so that each project can have its own dependencies, regardless of what is installed on the system version of Python or in other projects.

## Why Use Virtual Environments?&#x20;

Dependency Isolation:&#x20;

Each project may require different versions of Python packages. Virtual environments ensure that one project’s dependencies do not interfere with another's.

Reproducibility:&#x20;

By isolating dependencies, you can ensure your project runs with the same library versions it was developed with, preventing unexpected issues due to library updates.

Cleaner System:&#x20;

Virtual environments prevent cluttering your system Python installation with numerous packages that may only be relevant to specific projects.

Compatibility:&#x20;

When deploying applications, virtual environments ensure the environment matches production or development requirements.

## How Virtual Environments Work

When you create a virtual environment, Python sets up a directory structure with:

* A **local copy of the Python interpreter** (matching the system or specified version).
* A **local `site-packages` directory**, where third-party libraries can be installed.
* Scripts to activate and deactivate the environment.

Once activated, the virtual environment overrides the system’s Python and `pip` paths for the duration of the session, ensuring all commands apply to the isolated environment. You can install any version of Python.

## Creating and Using a Virtual Environment

### Linux

To create an environment called test1

```
python -m venv test1
```

Activate the environment with&#x20;

```
source /test1/bin/activate
```

### Windows

To create an environment called test1

```
py -m venv ./test1
```

Activate the environment with&#x20;

```
test1\Scripts\activate

(test1)C:Users\john.oraw\Desktop\Python> 
```

### Installing packages

Install packages as normal in either OS

```
python -m pip install matplotlib
```

### Deactivate

&#x20;Get back to the command prompt using the command

```
deactivate
```

## Visual Studio Code

Create a folder for your new project (my project is called OSWeather) and open that folder in VSCode. In the VSCode terminal window, I type&#x20;

```
python -m venv myvenv
```

This tell the Python 3.12 interpreter to use the venv module to create a new virtual environment called myvenv.

I press \[ctrl]\[shift]\[p] and then type interpreter into the command box, to select the python interpreter for VSCode. In my case it is 3.12.3

VSCode detects what I have done and asks me if I want to use this venv for this folder. I click **yes**.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

I can now see a new folder called myvenv, with all the normal content of a venv.

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

Restart the terminal for it to use the venv. Close the existing terminal window and type \[ctrl]\[j] to open a new terminal. Unfortunately, it doesn't show a venv prompt, but it is working!

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Now I can install my requirements for this project. In the terminal,&#x20;

```
pip install matplotlib, seaborn
```

## Conda

On data science projects, we use Conda instead of ordinary Python. The commands above are almost exactly the same. When you are in the shell, use the command conda to create and activate the environment.&#x20;

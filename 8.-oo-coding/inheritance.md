# Inheritance

If a project is complex enough to justify the overhead of writing it OO, it's probably complex enough to justify a little advanced planning and the use of inheritance. Classic books on OO design will specify Unified Modeling Language (UML) for this kind of work. In practice, I'm just not seeing that used in industry.&#x20;

In this section, I'm going to build up a basic class model on which I can build network automation code and utilities. Don't worry too much about the details, I do not assume you know anything about network hardware. This is just a slightly contrived context I'm using to build code which might actually be useful in another module!&#x20;

I am going to start off with the assumption but there are characteristics in common with all network devices.

```
# In any complex application, create a base class which will never be instantiated.
class Device():
    
    # Define a class object attribute, it will be the same for 
    # any instance of the class
    pi = 3.142

    # Constructor, called whenever an instance of the class is created.
    def __init__(self) -> None:
        print("Running constructor for base class")
        # Create attributes and set initial values
        self.debug = False

    def run(self):
        raise NotImplementedError("This is an abstract class, do not instantiate")

    def calculate_crc(self, frame:str)->int: 
        print("Checking CRC from base")
        # Put real code in here, this is a dummy value for initial setup
        crc = 123456789
        return crc

```

The first new idea is that of an _abstract class_. I am never going to instantiate an object called device, I'm going to want objects like firewalls, routers, and switches. I'm only using the abstract class to hold the attributes and methods common to all devices.&#x20;

For example, I will always want a CRC check, I have created a placeholder using a print statement (I might just have used pass). It all works, but there is no live code. If someone executes the run method, it will raise an error.

```
my_devices = Device()
my_devices.calculate_crc("dummy")
my_devices.run()
```

What I will actually need are objects which abstract real network devices.

```
# Create child classes which can access the methods and properties of the base class
class Firewall(Device):

    # Constructor, called whenever an instance of the class is created.
    # Use parameter1 as a tag to identify the object
    def __init__(self, parameter1) -> None:
        # Call back to the parent class
        Device.__init__(self)
        print(f"Running constructor for {parameter1}")
        # Create attributes and set initial values
        self.parameter1 = parameter1
        self.test_message = ""

    def configure_firewall(self):
        print("Configuring Firewall")
```

I create the child class using _**class ChildClassName(ParentClassname):**_&#x20;

The command **class Firewall(Device):** creates a derived class inheriting from the parent class, **Device**.&#x20;

I create an instance of Firewall by using **def \_\_init\_\_(self, parameter1) -> None:**&#x20;

I also need to initialize the base class using **Device.\_\_init\_\_(self)** when I create the Firewall class.&#x20;

You should understand all the other code. I can access attributes and methods from either the parent or child class from an object based on the child class.

```
hostname = "firewall3"
my_firewall = Firewall(hostname)
my_firewall.calculate_crc("dummy")
my_firewall.configure_firewall()
```

It can be mind-blowingly confusing, but I can _override methods_ in the base class from the derived class. Add the following code to the Firewall class and retest.

```
def calculate_crc(self, frame:str)->int: 
    print("Checking CRC from child")
    # Put real code in here, this is a dummy value for initial setup
    crc = 123456789
    return crc
```

The method **calculate\_crc** from the base is ignored and overridden.

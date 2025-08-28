# 8. OO Coding

These notes are provided to demonstrate how to get started with Object Oriented (OO) coding in Python. So far, we have concentrated on functional programming. The fundamental units of coding are functions, and we create a main program to call these functions in the correct sequence. In scripting, this is a perfect paradigm for most of the code we are going to write.&#x20;

But there is an entirely different paradigm which organizes our code around self-contained objects, which encapsulate data, properties (attributes), and functions (methods). Where we create large projects, which are complex, and will be maintained by many people, this is a more scalable way to organize.&#x20;

On a large project, I can have groups working separately on different objects, giving me better scalability and code reuse. In this approach, a class is a template used to create objects. We instantiate the class to create instances of an individual object. Everything related to this class is contained inside an object, and only selected attributes and methods are exposed to the outside.&#x20;

Some of my projects look at _digital twins_, a very poorly defined term. However, in every case, I use OO techniques for these projects.&#x20;

In electronics terms, an object is a black box. It provides an abstraction to the complexity which it contains.&#x20;

Imagine I am writing an instrument system for an airplane, and I create an instrument class. Instruments have certain characteristics or properties (Name, Type, etc) that all instruments have. If I want to verify communications, I could have a method to check a cyclical redundancy check (CRC). By making the barometer class a sub-class of the instrument class, the barometer class can inherit all the properties and methods of the instrument class.&#x20;

My airspeed class could also inherit the properties and methods of all instruments and have additional properties and methods specific to the pitot sensor. Methods can be extended and overridden; this is polymorphism.&#x20;

Objects can share behaviours and functions can have different meanings and usages depending on the context.&#x20;

In our coding so far, you have extensively used this functionality! Every time you use the format object.method you are using this.&#x20;

For example

```
my_string = "jor" 
my_proper_string = my_string.capitalize() 
print(my_proper_string)
```

Appending, sorting are all examples of methods which change the contents of an object.

Before you begin. create a directory to keep example files in and you are ready to code.&#x20;

This could be on your OneDrive, in these examples, I am using **OneDrive\Python\Exercises\_08**&#x20;

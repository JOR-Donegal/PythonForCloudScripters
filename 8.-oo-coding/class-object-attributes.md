# Class object attributes

Sometimes we need values which will be the same for all instances of the class. Imagine I'm writing some code for a geographical information system (GIS). The earth is abstracted as an ellipsoid, with a defined semi major axis, and semi minor axis. These will not change.&#x20;

I can define a class object attribute in the same way that we used to define constants in other programming languages. I add the following code before the constructor.

```
# Define a class object attribute, it will be the same for any instance of the class
    semi_major_axis = 6378137
    semi_minor_axis = 6356752 
```

We don't need to use the self keyword, as these values will be the same for every instance of the class. The following code at the end tests that this works.

```
# Instantiate the class
my_object = MyTemplate("John", True)
# Check the object
print(my_object.semi_major_axis, my_object.semi_minor_axis)
```

To generalize the template, change

* semi\_major\_axis to class\_object\_attribute1
* semi\_minor\_axis to class\_object\_attribute2

Then change the print statement to accommodate these changes and retest.

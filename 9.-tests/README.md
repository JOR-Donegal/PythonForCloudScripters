# 9. Tests

When I'm writing simple automation scripts, I write them as functions and then I called the functions from **\_\_main\_\_** as demonstrated earlier in the course. For simple scripts with no dependencies this is fine. However, I also demonstrated how to make modular code, how to build functions which will be permanently reusable. For example, utilities for Serial, TCP, UDP, cryptography and whatever other code you spend time building. By its very nature this code will be modified and improved during its unlimited operational lifetime. If I make it change in my code for one project, does that break the code for use in other projects?&#x20;

Do a little bit of reading to understand _DevOPS_. In a modern environment, we might write code, test the individual components (unit testing), test the integrated project, and deploy it to production, all in an automated workflow.&#x20;

In these exercises, I want to look at mandatory requirements for reusable code, the integration of tests.&#x20;

There is a quote attributed to Martin Fowler…&#x20;

_"Any fool can write code that a computer can understand. Good programmers write code that humans can understand."_

Before you begin. create a directory to keep example files in and you are ready to code.&#x20;

This could be on your OneDrive, in these examples, I am using **OneDrive\Python\Exercises\_09**&#x20;

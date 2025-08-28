# Finally

The examples I used here were trivial, but they did effectively demonstrate unit testing. On a large project, we create the unit tests as part of the project. When code is edited or refactored, we rerun the unit tests and hopefully spot any runtime errors. However, there is a whole school of thinking that says we are doing this backwards.&#x20;

When you are writing the specification for a software project, how do you write it unambiguously? One way to do so might be to write it in code. What more effective way could there be to do this, than to write the tests. The definition of a completed working program is that it passes the tests.&#x20;

I used **unittest** because historically, it has always been in Python. Many programmers advocate other frameworks, like **pytest**.&#x20;

_Test driven development_ (TDD) Is a key programming style, and you should read a little bit about the background to this.&#x20;

At the very least, if I'm creating a project, it will be documented, structured with modules or classes, separated out as packages if necessary, and with integrated tests.&#x20;

I showed you how to manually run the tests from the command prompt. Obviously, the final step would be to write a script file (DOS or Linux) to execute these tests. When we consider DevOPs, the execution of tests is just one step in a deployment.

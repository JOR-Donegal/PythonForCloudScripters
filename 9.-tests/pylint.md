# Pylint

Pylint is a library which examines your code and reports back possible issues, it is a _static code analyser_. In the terminal window I type&#x20;

```
pip install pylint
```

I create the following with Notepad++ and saved in **Exercises\_09** as **pylint1.py**

<pre><code><strong>a = 1
</strong>b = 2
c = "JOR"

print(a+b)
print(a+B)
print(a+c)
</code></pre>

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Wow, it gave me 0/10 marks!&#x20;

* The C prefixes are style issues flagged by pylint.&#x20;
* The E prefix is an actual error, I have mistakenly used capital B in my code.&#x20;

Review Pylint [here](https://pylint.pycqa.org/en/latest/tutorial.html).

## Exercise

Rewrite my simple code and get as close as you can to 10/10. Make any assumptions you need. I wrote and saved as **pylint2.py**

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

It took me a few goes looking at the test before I got full marks.&#x20;

A static code check can be good for quality assurance in teams.

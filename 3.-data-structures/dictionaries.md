# Dictionaries

Another data structure available in Python, is the dictionary. Dictionaries are unordered structures for storing objects.&#x20;

Previously with lists, we saw that they were ordered. We could access an entry by its index, and we use them when the data we are representing is positional and want to retrieve objects based on their location. For example, this is one possible sentence from a GPS, and it is comma delimited. If I convert these values to a list, index \[1] will always be the time in UTC.

```
GNGGA,120113.00,5510.0019168,N,00726.0946454,W,4,12,0.60,109.635,M,53.911,M,1.0,0000*73
```

Dictionaries have a key pair format, uniquely identifying each entry, without needing to know its location. The format uses curly braces and is {“key1”:”value1”, “key2”:”value2”}&#x20;

For example:

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

If I need the value of the key name, I retrieve it by key, not by its index.&#x20;

I do not need to know which order the value is in, however, I cannot index or slice a dictionary.&#x20;

Keys must always be strings.

I can add a key:value pair to the dictionary as follows.

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

I can edit any individual value in place. I have added comments to break up the code.

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

A dictionary can hold any type of object, for example, other dictionaries or lists.&#x20;

If I am working with large scientific data sets, for example for environmental, weather, physics, or maritime data, they will always be provided in lists and dictionaries.&#x20;

## Exercise&#x20;

Try using the methods

* my\_dictionary.keys()
* my\_dictionary.values()
* my\_dictionary.items()

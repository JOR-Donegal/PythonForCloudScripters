# Paths

I run the command&#x20;

```
pip install pathlib
```

to get the library I need.

Then I copy Exercises\_11 to my project and call it Network.

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Once my project becomes more complex, I may need to be more sophisticated in how I handle paths.

In the root directory, I create a file called **mypaths.py** and I define how to find some of my important files.

```
from pathlib import Path

PROJECT_ROOT = Path(__file__).parent
UDP_SETTINGS = str(PROJECT_ROOT / "Network/settings/udp.py")
```

I edit **main.py**

```
"""
main.py
By: JOR
Date: 20OCT23
"""

from mypaths import UDP_SETTINGS as udp_settings
print(udp_settings)
```

And I get the result

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

We do all the hard work in **mypaths.py** and keep our code nice and readable in **main.py**

Read about [pathlib](https://docs.python.org/3/library/pathlib.html), it is very powerful once we have complex directory structures.

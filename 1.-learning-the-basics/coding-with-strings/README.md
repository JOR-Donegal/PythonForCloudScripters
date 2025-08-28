# Coding with Strings

Strings are ordered sequences, so we can index and slice the string.We can use a square bracket notation to extract characters from the string, in the format \[start:stop:step].Consider the string “Greetings!” indexed from the start.

| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
| - | - | - | - | - | - | - | - | - | - |
| G | r | e | e | t | i | n | g | s | ! |

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

We can use forward or reverse indexing. Consider the string “Greetings!” indexed and sliced from the end.

| -10 | -9 | -8 | -7 | -6 | -5 | -4 | -3 | -2 | -1 |
| --- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
| G   | r  | e  | e  | t  | i  | n  | g  | s  | !  |

<figure><img src="../../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

I can also grab a single character.

<figure><img src="../../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

As discussed previously, strings are immutable, that means you cannot change the string. You can however slice the string and reassemble a new string with changes.

<figure><img src="../../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

You cannot add a string and a number, they are different types. Examine the code below.

<figure><img src="../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>






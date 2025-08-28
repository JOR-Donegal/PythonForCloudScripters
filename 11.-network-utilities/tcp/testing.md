# Testing

To make this work, I run the programs in two separate console sessions. I must press **\[ctrl]\[c]** to exit. I start the server first; it will listen indefinitely.

<figure><img src="../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

I start the client next. I need to do it in this order. The client tries to make a connection to a definite end point. There is no error handling, so if the connection is not available, it times out and exits.

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

If you cannot exit using \[ctrl]\[c], just close the command window.

Whenever you see **b’something’** this indicates that Python is handling bytes. This is normal in communications, but you may have to do some conversions to and from strings.

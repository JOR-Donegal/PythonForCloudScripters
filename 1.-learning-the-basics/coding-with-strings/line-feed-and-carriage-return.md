# Line feed and carriage return

In the Networking module, we introduce ASCII and Unicode. If you are unfamiliar with ASCII, do some background reading now.&#x20;

In any Windows system, if I look at the hidden characters in a file, I can see the carriage return \[CR] and line feed \[LF] characters.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

In a Linux system, I opened a script file and noted the differences and then used WinSCP to copy it to my Windows workstation. Only \[LF] characters at the end of each line!

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

Windows and Linux treat text files a bit differently, keep this in mind if you are moving files from system to system.

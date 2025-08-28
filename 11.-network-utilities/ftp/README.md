---
description: File Transfer Protocol
---

# FTP

The simplest (and most insecure) way we can transfer files will be to use file transfer protocol (FTP). The commands below may need to be altered depending on the version of Linux you use them on. I have tested this on Azure Labs to UB2204 in WSL2, it works fine!

I can install the most modern FTP library using&#x20;

```
pip3 install pyftpdlib 
```

I can run a simple server to share my working directory from the command prompt using&#x20;

```
python3 -m pyftpdlib -w --user=username --password=password 
```

Anonymous FTP (no username or password) works using

```
python3 -m pyftpdlib -w
```

I can then use WinSCP to make the connection and upload/download files. Test this and see if you can make it work!

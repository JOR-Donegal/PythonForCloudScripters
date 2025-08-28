# HTTP

As you might guess, we can also do a one-line HTTP server. Do <mark style="color:red;">NOT</mark> use this as a production HTTP server!!

I check my Ubuntu server's IP address, its 192.168.1.153.

I open a terminal in my home directory and I run&#x20;

```
python3 -m http.server
```

and then check a web browser from a W11 client. It defaults to port 8000.

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

Better if I create a directory called _WebServer_ and create a dummy file.

```
touch WebTest.txt
```

&#x20;I make that my working directory, before running the web server.

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

If I want to limit access to the machine I'm on, I can use the 127.0.0.x loopback addresses. This web server can only be reached from the local host.

```
python3 -m http.server -b 127.0.0.2 8080
```

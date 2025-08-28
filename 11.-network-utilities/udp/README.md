---
description: User Datagram Protocol
---

# UDP

For some things in networking, we use User Datagram Protocol (UDP). We send packets of data to a target, but we have no idea if they are received or not. Strangely, this is normal for many network protocols, especially those that carry real time data.&#x20;

First, I create **Exercises\_11\settings\udp.py**

```
UDP = {
    "SERVER_UDP_IPv4": '127.0.0.1',
    "CLIENT_UDP_IPv4": '127.0.0.0',
    "SERVER_PORT": 23
}
```

Then I create **Exercises\_11\udp\_client.py**

```
'''
UDPClient by: JOR
Send UDP packets to a particular address and port.
Alpha: 13FEB22
'''

import socket
import time
from datetime import datetime
import settings.udp as settings

UDP_IP = settings.UDP["SERVER_UDP_IPv4"]
UDP_PORT = settings.UDP["SERVER_PORT"]

print(f'This is the UDP client, it will try to connect to a server at {UDP_IP}:{UDP_PORT} in the settings file.')
print('This script has no error handling, by design')

while True:
    with socket.socket(socket.AF_INET, socket.SOCK_DGRAM) as s:
        s.setsockopt(socket.SOL_SOCKET, socket.SO_BROADCAST, 1)
        message_text = f"ATU {datetime.now()}"
        message = message_text.encode('utf-8')
        s.sendto(message, (UDP_IP, UDP_PORT))
        print(f'Sent {message_text}')
        time.sleep(1)

```

In network terminology, a _socket_ is an endpoint on a node, which can take part in two-way communication. T

This program constructs a test line, for example&#x20;

ATU 2022-10-13 12:38:01.285021&#x20;

This is sent to a server defined by the settings file, once per second, and to the screen as feedback to the user. I tested this on the Azure Labs and because of firewall restrictions, I used the loopback address 127.0.0.1. This worked for me, even through there was no server at the other end.&#x20;

Why does this work?

Then I create **Exercises\_11\udp\_server.py**

```
'''
UDPServer by: JOR
Listens for packets on a particular address and port.
Alpha: 13FEB22
'''

import socket
import settings.udp as settings

UDP_IP = settings.UDP["SERVER_UDP_IPv4"]
UDP_PORT = settings.UDP["SERVER_PORT"]
BUFFER_SIZE = 1024

print(f'This is the UDP server, it will open a port at {UDP_IP}:{UDP_PORT} and being listening')
print(f'Make sure the actual server IP address matches {UDP_IP} in the settings file')
print('This script has no error handling, by design')

with socket.socket(socket.AF_INET, socket.SOCK_DGRAM) as s:
    s.setsockopt(socket.SOL_SOCKET, socket.SO_BROADCAST, 1)
    s.bind( (UDP_IP, UDP_PORT) )
    print('Listening on', UDP_IP)
    while True:
        data, addr = s.recvfrom(BUFFER_SIZE)
        data = data.decode()
        print(addr, data)
```

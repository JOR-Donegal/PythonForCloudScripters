---
description: Transmit Control Protocol
---

# TCP

When we need reliable data communications, we use Transmit Control Protocol (TCP). The client and server in this communication have a complex network stack. Every communication is acknowledged, and functionality exists within the protocol for it to auto-tune to the characteristics of the communication medium.&#x20;

First, I create **Exercises\_11\settings\tcp.py**

```
TCP = {
    "SERVER_TCP_IPv4": '127.0.0.1',
    "SERVER_PORT": 23
}
```

Then I create **Exercises\_11\tcp\_client.py**

```
'''
TCPClient by: JOR
Send TCP packets to a particular address and port.
Alpha: 13FEB22
'''

import socket
import time
from datetime import datetime
import settings.tcp as settings

TCP_IP = settings.TCP["SERVER_TCP_IPv4"]
TCP_PORT = settings.TCP["SERVER_PORT"]

print(f'This is the TCP client, it will try to connect to a server at {TCP_IP}:{TCP_PORT} in the settings file.')
print('This script has no error handling, by design')

BUFFER_SIZE = 1024
while True:
    print(f'Trying to open a socket to {TCP_IP}:{TCP_PORT}')
    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
        message_text = f"ATU {datetime.now()}"
        message = message_text.encode('utf-8')
        s.connect((TCP_IP, TCP_PORT))
        s.send(message)
        print(f'Sent {message_text} to {TCP_IP}:{TCP_PORT}')
        data = s.recv(BUFFER_SIZE)
        print('Server echoed:', data)
        time.sleep(1)

```

Then I create **Exercises\_11\tcp\_server.py**

```
'''
TCPServer by: JOR
Listens for packets on a particular address and port.
Alpha: 13FEB22
'''

import socket
import settings.tcp as settings

TCP_IP = settings.TCP["SERVER_TCP_IPv4"]
TCP_PORT = settings.TCP["SERVER_PORT"]
BUFFER_SIZE = 1024

print(f'This is the TCP server, it will open a port at {TCP_IP}:{TCP_PORT} and being listening')
print(f'Make sure the actual server IP address matches {TCP_IP} in the settings file')
print('This script has no error handling, by design')

try:
    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
        s.bind((TCP_IP, TCP_PORT))
        print(f'Bound to {TCP_IP}:{TCP_PORT}')
        while True:
            s.listen(1)
            conn, addr = s.accept()
            print(f'Connection address: {addr}')
            data = conn.recv(BUFFER_SIZE).decode()
            print(data)
            conn.send(data.encode())
except socket.error as e:
    print(f'Error: {e}')
```

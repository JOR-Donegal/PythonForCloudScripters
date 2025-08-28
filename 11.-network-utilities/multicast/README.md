# Multicast

In simple terms, I can do a broadcast on a network. This results in every client on the network receiving and processing the packet. That's a great way to cause congestion on a network! There are cases where the output of process needs to be seen by many other processes on many other nodes.&#x20;

Imagine I have power monitoring equipment in my data centre, and I have distributed control to take action based on the power state. For example, if the power is out, and the temperature is OK, I might shut down ventilation fans to reduce the load on the Uninterruptible Power Supply (UPS).&#x20;

One way to do this is to use multicast. Make all the data available, any device which wants to consume the data can do so. A modern architecture for this might use [MQTT](https://mqtt.org/).

First, I create **Exercises\_11\settings\mc.py**

```
MCSERVER = {
    "MCAST_GROUP": '239.1.1.1',
    "IP_ADDRESS": '127.0.0.1',
    "PORT": 5001
}

MCCLIENT = {
    "MCAST_GROUP": '239.1.1.1',
    "IP_ADDRESS": '127.0.0.1',
    "PORT": 5001
}
```

Then I create **Exercises\_11\mc\_client.py**

```
'''
Multicast client by: JOR
Sends multicast packets to a particular address and port.
Alpha: 13FEB22
'''
import socket
import time
from datetime import datetime
import settings.mc as settings

# Set multicast information
MCAST_GRP = settings.MCCLIENT["MCAST_GROUP"]
MCAST_PORT = settings.MCCLIENT["PORT"]
MCAST_IF_IP = settings.MCCLIENT["IP_ADDRESS"]

print(f'This is the client, make sure its IP address matches {MCAST_IF_IP} in settings.')
print(f'This selects which interface is used for multicast to {MCAST_GRP}.')
print('This script has no error handling, by design')

while True:
    with socket.socket(socket.AF_INET, socket.SOCK_DGRAM, socket.IPPROTO_UDP) as s:
        # inet_aton converts IPv4 from the a dotted decimal string to 32 bit packed binary format
        s.setsockopt(socket.IPPROTO_IP, socket.IP_ADD_MEMBERSHIP, socket.inet_aton(MCAST_GRP) + socket.inet_aton(MCAST_IF_IP))
        message_text = f"ATU {datetime.now()}"
        message = message_text.encode('utf-8')
        s.sendto(message, (MCAST_GRP, MCAST_PORT))
        print(f'Sent {message_text} to {MCAST_GRP}:{MCAST_PORT}')
        time.sleep(1)

```

Then I create **Exercises\_11\mc\_server.py**

```
'''
Multicast Server by: JOR
Reads multicast packets from a particular address and port.
Alpha: 13FEB22
'''
import socket
import struct
import settings.mc as settings

# Set multicast information
MCAST_GRP = settings.MCSERVER["MCAST_GROUP"]
SERVER_ADDRESS = ('', settings.MCSERVER["PORT"])
MCAST_IF_IP = settings.MCSERVER["IP_ADDRESS"]

print('This is the server.')
print(f'Make sure its IP address matches {MCAST_IF_IP} in settings.')
print(f'This selects which interface is used to listen for multicast as {MCAST_GRP}.')
print('This script has no error handling, by design.')

with socket.socket(socket.AF_INET, socket.SOCK_DGRAM) as s:
    s.bind(SERVER_ADDRESS)
    # inet_aton converts IPv4 from the a dotted decimal string to 32 bit packed binary format
    s.setsockopt(socket.IPPROTO_IP, socket.IP_ADD_MEMBERSHIP, socket.inet_aton(MCAST_GRP) + socket.inet_aton(MCAST_IF_IP))

    while True:
        print('Waiting to receive message')
        data, address = s.recvfrom(1024)
        print(f'received {len(data)} bytes from {address}')
        print(data)
```

---
description: Network Time Protocol
---

# NTP

In April 2024 I was working on some [GNSS boards](https://www.ardusimple.com/product/simplertk3b-x5/) to detect navigation spoofing and jamming. As an extra, the boards support NTP and PTP clocks. I had 20 lines of Python to check the NTP server using UDP, I wanted to extend it to show meaning of all 48 bytes in a response packet.&#x20;

Way too much hard work, I used the [ntplib](https://github.com/cf-natali/ntplib/blob/master/test_ntplib.py) library instead. The version below points at a pool of NTP servers.

```
'''
NTPClient by: JOR
Simple test of NTP server
Alpha: 30APR24
'''
import ntplib
from time import ctime

ntpServer = "ie.pool.ntp.org"

ntp = ntplib.NTPClient()
ntpResponse = ntp.request(ntpServer)

if (ntpResponse):
   print(f"NTP Time: {ctime(ntpResponse.tx_time)}")
   print(f"Precision: {ntpResponse.precision}")
   print(f"Version: {ntpResponse.version}")
   print(f"Offset: {ntpResponse.offset}")
   print(f"Root delay: {ntpResponse.root_delay}")
   print(f"Root dispersion: {ntpResponse.root_dispersion}")
   print(f"Delay: {ntpResponse.delay}")
   print(f"Leap: {ntpResponse.leap}")
   print(f"Stratum of NTP server: {ntpResponse.stratum}")
```

This is very useful!

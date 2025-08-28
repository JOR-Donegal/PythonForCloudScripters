# Finally

Sorry for dumping network terminology on you when we may not yet have covered networking!&#x20;

In my examples, I used the loopback address 127.0.0.1 to get around Windows Firewall and the security restrictions. If you can run these programs on two or more virtual machines, it is a much better way to test things. I am a big fan of Raspberry Pi, and I will often use a rack of these for testing. Many of my production instrumentation systems end up on a Raspberry Pi or similar.&#x20;

This code is based on functions I have used for years for testing client-server applications. Around 2013 I started writing code to control automation infrastructure; think about all the things that are required in the electrical and cooling parts of a data centre.&#x20;

This code has been incrementally improved, but always with the goal of keeping it as simple and stable as possible. I made all sorts of excursions into multithreaded code and that all worked. I also did versions based on object-oriented code. I want to keep things as simple and reliable as possible, the code demonstrated here works fine.

## LLDP

When connecting up systems, its really nice to be able to detect which port a device is on, where it is on a network. By enabling LLDP on any system, this information can propagate. Take a look [here](https://github.com/OpenCPSL/Setup_LLDP), this is the repo of one of our research collaborators.&#x20;

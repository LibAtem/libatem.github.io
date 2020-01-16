---
#layout: page
title: "Blackmagic Design ATEM Protocol Links"
permalink: /links
---
### Libraries
[LibAtem](https://github.com/libatem/libatem) is a C# library to do everything ATEM. It runs anywhere dotnetcore is supported, and aims to be as feature complete as possible. It has tests to compare behaviour to the official SDK, to ensure it is correct. It is used as the source of data for this site.

[atem-connection](https://github.com/nrkno/tv-automation-atem-connection) is a Typescript library for nodejs. This makes it very portable and easy to use. It has tests to ensure it's command encoding is the same as LibAtem for correctness

[libqatemcontrol](https://github.com/petersimonsson/libqatemcontrol) is a C++ library supporting the main parts of the protocol.

### Tools
[LibAtem AtemUtils](https://github.com/LibAtem/AtemUtils) Some small tools to aid in reverse engineering the protocol

[Wireshark dissector](https://github.com/peschuster/wireshark-atem-dissector) A wireshark plugin to inspect ATEM packets and the commands they contain

### References
This builds on the work originally pioneered by [SKAARHOJ](https://www.skaarhoj.com/fileadmin/BMDPROTOCOL.html)

If you know of other libraries, feel free to make a Pull Request on [Github](https://github.com/LibAtem/libatem.github.io)
---
#layout: page
title: "Blackmagic Design ATEM Protocol Encoding"
permalink: /protocol
---
## Protocol

This page tries to explain the structure and flow of the protocol.

### Packet Structure

Each packet has a 12 byte header set out as follows

| Name | Bytes | Type | Description |
| --- | --- | --- | --- | --- |
| Command Code | 0 (5 bits) | Enum (Flags) | Bit 0 = AckRequest<br/>Bit 1 = NewSessionId<br/>Bit 2 = IsRetransmit<br/>Bit 3 = RetransmitRequest<br/>Bit 4 = AckReply |
| Packet Length | 0-1 (skips first 5 bits) | Int | Length of this packet including header |
| Session Id | 2-3 | Int | Id of the connection. When CommandCode.NewSessionId is set this will change and should be used for future packets |
| Acked Packet Id | 4-5 | Int | Only if CommandCode.AckReply, then the ATEM is confirming receipt of the packet with this ID |
| Retransmit Packet Id | 6-7 | Int | Only if CommandCode.RetransmitRequest, then the ATEM is asking for retransmit of the packet with this ID and all following |
| Packet Id | 10-11 | Int | Only if CommandCode.AckRequest, the ATEM requires an ACK of this packet to confirm receipt |
| Payload | 12-end | Bytes | Encoded commands (Only if CommandCode.AckRequest is set) |

Packet Id is a 16 bit Integer (allowed range 0 - 32767), and wraps back to 0 when it reaches the maximum.  
Care should be taken to ensure acks and retransmits handle this wrap properly. This is a common cause of connection stability issues.

Only packets with CommandCode.AckRequest should set the Packet Id, and it should increase for each packet it is set on.  
The ATEM can ask for retransmits of packets, and the connection will stall if the retransmits are not fullfilled.


### Packet Flow

TODO - explain fields + uses?

TODO - pings
TODO - timeouts

TODO - acking in batches

### Handshake

Handshaking is a very simple process, and is needed to initialise a connection.

TODO - send packet
TODO - receive packet

At this point the ATEM will now send you the whole state. There are a few commands which are only seen here which describe the topology of the connected device. The rest is the same commands received during state changes, making it all very easy to process. 

The connection state dump is complete when you receive an `InCm` command. At this point the connection is ready for use.

### Command Encoding

### Macro Operation Encoding

Macro Operations follow very similar encoding rules to Commands.

Each operation has a header, with the full structure of the wrapped buffer as follows. A full macro is stored as a list of these.

| Name | Bytes | Type | Description |
| --- | --- | --- | --- | --- |
| Length | 0 | UInt | Length of the operation, including header |
| MacroOperation | 2-3 | Enum | Id of the operation. (eg 31 for AuxiliaryInput) |
| Payload | 4-? | Bytes | Encoded payload |

Note: Payload length is always a multiple of 4.

### Data Transfers

TODO

# Lesson 4 — TCP/IP

## Introduction

TCP/IP is the networking foundation of the Internet. IP finds the destination, and TCP makes the communication reliable.

## Why This Exists

IP alone can route packets, but it does not guarantee delivery, order, or error recovery. TCP was created to make network communication reliable.

## Core Ideas

### IP
- Finds the destination
- Routes packets
- Provides addressing
- Does not guarantee delivery

### TCP
- Creates a connection
- Ensures reliable delivery
- Keeps packets in order
- Retransmits lost packets
- Detects errors

## TCP Three-Way Handshake

1. Client sends SYN
2. Server replies SYN + ACK
3. Client sends ACK
4. Connection is established

After this, HTTP can send data.

## Sequence and Order

TCP uses sequence numbers so packets can be placed in the correct order even if they arrive out of order.

## Acknowledgment and Retransmission

If a packet is missing, TCP waits and then retransmits it. This is why file downloads, banking requests, and database traffic use TCP.

## TCP vs UDP

### TCP
Use TCP when reliability matters more than speed.
Examples: login, payments, file downloads, databases.

### UDP
Use UDP when low latency matters more than perfect delivery.
Examples: live video, voice calls, online games, DNS lookups.

## Real MERN Example

When React calls `fetch("/api/login")`, the browser first resolves the domain, then establishes a TCP connection, and only then sends the HTTP request.

## Common Mistakes

- DNS does not create the connection.
- HTTP does not create the connection.
- IP and TCP are not the same thing.
- UDP is not better in every case.

## Trick Questions

- Is TCP faster than UDP? Not usually, because TCP has more reliability overhead.
- Why use TCP for banking? Because every byte matters.
- Why use UDP for video calls? Because delay is worse than loss.

## Interview Ready Answer

TCP/IP is the networking foundation of the Internet. IP handles addressing and routing, while TCP provides reliable, ordered, and error-checked delivery. A TCP connection is established with a three-way handshake before application data such as HTTP requests is sent.

## Revision Summary

- DNS gives the IP address.
- IP routes packets.
- TCP makes delivery reliable.
- TCP uses a three-way handshake.
- TCP handles ordering and retransmission.
- UDP is used when latency matters more than reliability.

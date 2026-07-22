# Lesson 4 — TCP/IP Notes

## What TCP/IP means
TCP/IP is a protocol suite used for communication over networks.
- IP handles addressing and routing.
- TCP handles reliable communication.

## Why TCP/IP exists
IP alone can send packets across networks, but it cannot guarantee that packets will arrive, stay in order, or be recovered if lost. TCP was built to solve that problem.

## IP responsibilities
- Give devices an address
- Route packets to the destination
- Move data across networks
- Best-effort delivery only

## TCP responsibilities
- Create a connection before sending data
- Make delivery reliable
- Keep packets in order
- Detect missing packets
- Retransmit lost packets
- Provide flow control

## TCP three-way handshake
Connection setup happens in three steps:
1. Client sends SYN
2. Server sends SYN + ACK
3. Client sends ACK

After this, the connection is established and application data can move.

## Why TCP is needed
If packets arrive out of order or get lost, TCP fixes it using sequence numbers, acknowledgments, and retransmission.

Example:
- Packet 1 arrives
- Packet 2 is delayed
- Packet 3 arrives
TCP waits and reorders the packets so the application receives clean data.

## What happens after DNS
When DNS returns the IP address, the browser does not send HTTP immediately. It first establishes a TCP connection. Only after that does it send the HTTP request.

## TCP vs UDP
### TCP
Use TCP when reliability matters.
Examples:
- login
- payments
- file downloads
- databases
- emails

### UDP
Use UDP when low latency matters more than perfect delivery.
Examples:
- live video
- voice calls
- online games
- DNS lookups

## Real MERN example
For `fetch("/api/login")`:
1. Browser resolves the domain using DNS
2. Browser establishes a TCP connection
3. Browser sends the HTTP request
4. Node.js receives it
5. Server returns the response

## Common mistakes
- DNS does not create the connection
- HTTP does not create the connection
- TCP and IP are not the same
- UDP is not always better

## Trick questions
- Is TCP faster than UDP? Usually no, because TCP does more work for reliability.
- Why does banking use TCP? Because no packet should be lost.
- Why do video calls use UDP? Because delay is worse than a small packet loss.

## Interview-ready line
TCP/IP is the networking foundation of the Internet. IP routes packets to the destination, and TCP ensures the data arrives reliably, in order, and without loss.

## One-line revision
DNS finds the IP, TCP opens the reliable connection, and HTTP sends the request on top of that connection.

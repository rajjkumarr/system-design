# Notes — Lesson 2

## 1) What a network is

A network is a group of connected devices that can communicate and share resources. That can be as small as a laptop and a printer on Wi-Fi, or as large as thousands of servers inside a company network.

## 2) Why an ISP is needed

An Internet Service Provider connects your local network to the public Internet. Your home router can talk to devices inside your home, but the ISP is what gives your network a route to websites, cloud servers, and external services.

## 3) Router vs switch

A switch connects devices inside the same local area network. It is used for local communication, such as laptops, printers, and servers in an office.

A router connects different networks. It decides where packets should go next and sends local traffic toward the ISP or toward another network.

## 4) Private IP addresses

Private IPs are used only inside local networks. Examples include ranges like `192.168.x.x`, `10.x.x.x`, and `172.16.x.x` to `172.31.x.x`.

These addresses are not directly reachable from the public Internet. That is why many homes and offices can reuse the same private IP ranges.

## 5) Public IP addresses

A public IP is reachable from the Internet. Your ISP assigns a public IP to your network, and cloud providers assign public IPs or public endpoints to servers that must be reached from outside.

## 6) NAT / PAT

NAT (Network Address Translation) lets a router convert private IP traffic into a public IP flow before sending it to the Internet.

PAT (Port Address Translation) is a common form of NAT where many private devices share one public IP by using different source ports. This is how a laptop, phone, and TV can all browse the Internet at the same time from one home connection.

## 7) Why private IPs matter in production

Private IPs save public IPv4 addresses and reduce direct exposure of internal devices. Public access is only exposed where needed, such as through a load balancer, reverse proxy, or firewall rule.

## 8) Real MERN request flow

Browser -> laptop private IP -> home router (NAT) -> ISP -> Internet routing -> cloud load balancer -> Nginx / reverse proxy -> Node.js API -> database or cache -> response back to the browser.

## 9) Senior engineer mindset

When debugging network issues, ask:
- Is the device on the right network?
- Is the router translating traffic correctly?
- Is the ISP reachable?
- Is the destination public IP or port open?
- Is the server behind a load balancer or proxy?

## 10) One-line revision

Networking is the path that carries your MERN request from a private device on a local network to a public server on the Internet and back again.

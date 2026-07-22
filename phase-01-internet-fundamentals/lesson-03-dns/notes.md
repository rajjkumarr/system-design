# Lesson 3 — DNS Notes

## What DNS is
DNS (Domain Name System) converts a human-readable domain name into an IP address.

Example:
- `google.com` → `142.250.193.78`
- `api.myapp.com` → server IP

## Why DNS exists
Humans remember names better than numbers.
DNS solves the problem of remembering and managing IP addresses for every website.

## What DNS does not do
- DNS does not return HTML.
- DNS does not host the website.
- DNS does not send the HTTP response.
- DNS only tells the browser where the server is.

## DNS resolution flow
When you type a domain in the browser, the browser tries to find the IP in this order:

1. Browser DNS cache
2. Operating system DNS cache
3. DNS resolver
4. Root DNS server
5. TLD DNS server
6. Authoritative DNS server
7. Final IP address

## Important DNS servers

### DNS Resolver
The resolver performs the lookup on your behalf and often caches results.

### Root DNS Server
The root server does not know every domain. It points the resolver to the correct TLD server.

### TLD Server
TLD means Top-Level Domain. Examples: `.com`, `.org`, `.in`.
It tells the resolver which authoritative server to ask next.

### Authoritative DNS Server
The authoritative server contains the DNS records for the domain and gives the final answer.

## DNS records
DNS servers store records like:
- A record → maps domain to IPv4 address
- AAAA record → maps domain to IPv6 address
- CNAME record → maps one domain to another domain

## Cache and TTL
After a DNS lookup, the result is stored in cache for a limited time called TTL (Time To Live).

Why this matters:
- faster next request
- fewer DNS lookups
- websites can still change IPs after TTL expires

## Real MERN example
When your frontend calls:

`fetch("https://api.myapp.com/login")`

DNS must first resolve `api.myapp.com` to an IP address before the browser can connect to the Node.js API.

## Can one IP host multiple websites?
Yes.
Multiple domains can point to the same IP.
The web server reads the `Host` header to decide which website to serve.

Example:
- `example.com`
- `blog.example.com`
- `shop.example.com`

These can all use the same server IP.

## Can one domain have multiple IPs?
Yes.
This is used for:
- load balancing
- high availability
- faster global routing

## Common mistakes
- DNS is not HTTP.
- DNS is not the website itself.
- DNS does not store the page content.
- DNS is not the same as caching, but it can be cached.

## Trick questions
- Does DNS return the webpage? No.
- Can two sites share one IP? Yes.
- Why does refresh not always trigger DNS lookup? Because the result may already be cached.
- Can one domain point to many IPs? Yes.

## Interview-ready answer
DNS is a distributed naming system that resolves domain names into IP addresses. The browser checks caches first, then queries DNS servers in a hierarchical way until it receives the final IP address. After that, it can establish a connection to the server.

## Senior engineer mindset
When a site is not opening, ask:
- Is the domain resolving?
- Is the DNS cache stale?
- Is the authoritative record correct?
- Is the server IP changed but TTL still active?

## One-line revision
DNS resolves names to IPs so the browser knows where to connect before TCP and HTTP begin.

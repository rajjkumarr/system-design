# Lesson 3 — DNS (Domain Name System)

## Introduction

DNS stands for Domain Name System. It translates a human-readable domain name like `google.com` into an IP address that computers can use.

## Why DNS Exists

Humans remember names much better than numbers. DNS solves the problem of remembering IP addresses for every website, API, or service.

## Problem It Solves

Without DNS, every user would need to type the IP address of every website directly. That is impractical and hard to maintain.

## Core Idea

- Domain name = human-friendly name
- IP address = machine-friendly address
- DNS = system that resolves one into the other

## DNS Resolution Flow

Browser DNS cache → OS DNS cache → DNS resolver → Root server → TLD server → Authoritative DNS server → IP address

## Important DNS Servers

### 1) DNS Resolver
The resolver does the lookup on your behalf and can cache results.

### 2) Root Server
Points the resolver to the correct top-level domain server.

### 3) TLD Server
Handles domains such as `.com`, `.org`, and `.in`.

### 4) Authoritative DNS Server
Contains the DNS records for the domain and returns the final answer.

## Cache and TTL

Once a domain is resolved, the result is cached for a period called TTL (Time To Live). This makes future requests faster.

## Real MERN Example

When your frontend calls `https://api.myapp.com/login`, DNS must first resolve `api.myapp.com` to an IP address before the browser can connect to your Node.js server.

## Common Mistakes

- DNS does not return HTML.
- DNS is not the same as HTTP.
- DNS does not host the website; it only tells the browser where to go.

## Trick Questions

- Can one IP host multiple websites? Yes.
- Can one domain have multiple IPs? Yes.
- Why does refresh not always trigger DNS lookup? Because the result may be cached.

## Interview Ready Answer

DNS is a distributed naming system that converts domain names into IP addresses. The browser checks caches first, then uses DNS resolution to find the correct server, and only after that does it connect to the server.

## Revision Summary

- DNS resolves domain names to IP addresses.
- Browsers use DNS before TCP and HTTP.
- DNS is distributed and scalable.
- Caching and TTL make DNS fast.
- Authoritative servers hold the final DNS records.

# Lesson 2 — Networking Basics

## Introduction

This lesson explains how a request leaves a device, how local networks work, and how routers, switches, IP addresses, and NAT enable Internet communication.

## Problem Statement

A device on a local network must reach public services on the Internet, even though private IPs cannot be routed publicly.

## Why This Exists

Networking exists so devices can share data, share resources, and communicate across local and global networks.

## Core Concepts

### 1) Network
A network is a group of connected devices that can communicate and share resources.

Example:

Laptop ↔ Printer ↔ Router ↔ Mobile

### 2) ISP
An ISP connects your local network to the public Internet.
Without an ISP, your home devices can talk to each other, but they cannot reach public websites or cloud servers.

### 3) Router
A router connects different networks and forwards packets to the next hop.
It works between your local network and the ISP / Internet.

### 4) Switch
A switch connects devices inside the same LAN.
It is used for local communication inside an office, home, or data center.

### 5) Public IP
A public IP is reachable from the Internet.
Cloud servers or routers use public IPs or public endpoints so outside users can reach them.

### 6) Private IP
A private IP is used only inside a local network.
Common ranges are `192.168.x.x`, `10.x.x.x`, and `172.16.x.x` to `172.31.x.x`.
Private IPs are not directly routable on the public Internet.

### 7) NAT / PAT
NAT converts private IP traffic into public IP traffic before it leaves the local network.
PAT is the common home-router version of NAT where many devices share one public IP using different source ports.

## Simple Request Flow

Browser → Laptop Private IP → Home Router (NAT/PAT) → ISP → Internet → AWS Load Balancer → Nginx → Node.js API → Response

## Example

Your phone, laptop, and TV may all use private IPs like `192.168.1.10`, `192.168.1.11`, and `192.168.1.12`.
They can all browse the Internet at the same time because the router translates their traffic into one public IP and tracks each flow using ports.

## Common Mistakes

- Private IP does not mean encrypted.
- Router and switch are not the same.
- NAT is not the same as encryption.
- Private IPs can repeat in different homes.

## Interview Ready Answer

Networking is the process that lets a device on a local private network reach public services on the Internet through an ISP, router, and NAT translation.

## Trick Questions

- Can two homes use the same private IP range? Yes.
- Why cannot Google send directly to `192.168.1.10`? Because private IPs are not routed publicly.
- How can many devices share one public IP? Through NAT/PAT using different ports.

## Senior Engineer Mindset

When a request fails, ask:
- Is the device on the right network?
- Is the router translating correctly?
- Is the ISP reachable?
- Is the destination port open?
- Is there a load balancer or reverse proxy in front of the API?

## Real MERN Relevance

Every login request, API call, webhook, and database request depends on network routing and address translation.

## Revision Summary

- Network = connected devices
- ISP = Internet access provider
- Router = connects networks
- Switch = connects devices in one LAN
- Private IP = internal only
- Public IP = Internet reachable
- NAT/PAT = private to public translation

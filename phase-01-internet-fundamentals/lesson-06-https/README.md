# Lesson 6 — HTTPS (HTTP + TLS)

## Introduction

HTTPS stands for HyperText Transfer Protocol Secure. It is HTTP protected by TLS.

## Why HTTPS Exists

HTTP sends data in plain text. Passwords, tokens, and personal data can be read or changed if traffic is intercepted.

HTTPS solves this by giving us:
- Encryption
- Integrity
- Authentication

## How HTTPS Fits in the Flow

DNS → TCP → TLS handshake → HTTPS request → server → HTTPS response

## What HTTPS Is

HTTPS is not a different protocol from HTTP. It is HTTP running over TLS.

## What TLS Does

TLS (Transport Layer Security) protects communication by:
- Encrypting the data
- Preventing tampering
- Verifying the server identity using a certificate

## Certificate

A certificate is like a digital ID card for the server.
It tells the browser:
- which domain it belongs to
- which public key to trust
- which CA issued it
- when it expires

## Certificate Authority

A Certificate Authority (CA) is a trusted organization that issues certificates.
The browser trusts known CAs.

## HTTPS Flow

1. Browser resolves the domain using DNS
2. Browser establishes a TCP connection
3. TLS handshake starts
4. Server sends its certificate and public key
5. Browser verifies the certificate
6. Browser generates a random session key
7. Browser encrypts the session key using the server's public key
8. Server decrypts it using its private key
9. Both sides now share the same session key
10. All HTTP data is encrypted with fast symmetric encryption

## Why HTTPS Uses Both Encryption Types

### Asymmetric encryption
Used during the handshake to safely exchange the session key.

### Symmetric encryption
Used after the handshake because it is fast and efficient.

## Why Not Only Symmetric Encryption

Symmetric encryption needs a shared secret key. The difficult part is sharing that key safely over the Internet.

## Why Not Only Asymmetric Encryption

Asymmetric encryption is slower. Using it for every image, CSS file, and API response would make websites too slow.

## Real MERN Example

When React calls `fetch("https://api.myapp.com/orders")`, the browser first resolves DNS, then connects with TCP, then performs the TLS handshake, and only after that sends the encrypted HTTP request.

## Common Mistakes

- HTTPS is not the same as HTTP.
- HTTPS is not encryption by itself; it uses TLS.
- The private key stays on the server.
- HTTPS secures data in transit, not the whole application.

## Trick Questions

- Does HTTPS secure the database directly? No.
- Is HTTPS slower than HTTP? Slightly, but the security benefit is worth it.
- Can a website have HTTPS without a certificate? No.
- Does HTTPS change HTTP methods like GET and POST? No.

## Interview Ready Answer

HTTPS is HTTP running over TLS. TLS encrypts the communication, verifies the server through a certificate, and prevents tampering. During the handshake, asymmetric cryptography is used to exchange a shared session key, and after that, symmetric encryption is used for fast data transfer.

## Revision Summary

- HTTP is plain text.
- HTTPS = HTTP + TLS.
- TLS gives encryption, integrity, and authentication.
- Certificates prove server identity.
- Private key stays on the server.
- Asymmetric crypto helps exchange the key safely.
- Symmetric crypto is used for fast encrypted traffic.

# Lesson 9 — JWT

## What is JWT?

JWT stands for JSON Web Token. It is a signed token that contains user information.

## Why JWT Exists

Sessions store data on the server. JWT was created so the server does not need to look up session data for every request.

## JWT Parts

A JWT has three parts:
- Header
- Payload
- Signature

## Important Point

The payload is Base64 encoded, not encrypted. So do not store passwords or sensitive secrets in it.

## Why JWT Is Trusted

If someone changes the payload, the signature will not match. The backend verifies the signature before trusting the token.

## Simple Flow

1. User logs in
2. Server creates JWT
3. Server sends JWT to the client
4. Client sends JWT in future requests
5. Server verifies the signature
6. Server allows or rejects the request

## Real MERN Example

Login response:

```json
{
  "token": "eyJhbGciOi..."
}
```

Next request:

```http
Authorization: Bearer eyJhbGciOi...
```

## Cookie vs Session vs JWT

- Cookie = browser storage
- Session = server storage
- JWT = signed token often stored on the client

## Common Mistakes

- JWT is not always encrypted.
- JWT payload can be decoded.
- JWT should not store passwords.
- A valid JWT can still contain outdated data.

## Interview Ready Answer

JWT is a signed token used to identify the user without storing session data on the server. The backend verifies the signature and then trusts the token only if it is valid.

## Revision Summary

- JWT means JSON Web Token.
- It has header, payload, and signature.
- Signature prevents tampering.
- Payload is not encrypted.
- The backend verifies the token before using it.

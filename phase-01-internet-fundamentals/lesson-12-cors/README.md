# CORS (Cross-Origin Resource Sharing)

## 1) Origin

An origin has 3 parts:
- protocol
- domain
- port

Example:
- `http://localhost:5173`
- `http://localhost:5000`

If any one part changes, it becomes a different origin.

## 2) Same-Origin Policy

Browsers use the Same-Origin Policy to protect users.
A webpage from one origin should not freely read responses from another origin.

## 3) Why CORS Exists

CORS exists because browsers block cross-origin JavaScript access unless the server allows it.

This helps protect sensitive sites from malicious websites trying to read private data through the browser.

## 4) Who Enforces CORS

The browser enforces CORS.
Not React.
Not Node.js.
Not Express.

## 5) Simple Requests and Preflight Requests

Some cross-origin requests go directly.
Some requests first send a preflight request.

### Preflight request
The browser sends an automatic `OPTIONS` request first to ask the server for permission before sending the real request.

This usually happens for requests like:
- `PUT`
- `DELETE`
- some `POST` requests
- requests with custom headers

## 6) CORS Headers

### `Origin`
Sent by the browser.
It tells the server where the request is coming from.

### `Access-Control-Allow-Origin`
Sent by the server.
It tells the browser which origin is allowed to read the response.

Example:
```http
Access-Control-Allow-Origin: http://localhost:5173
```

### `Access-Control-Allow-Methods`
Tells the browser which HTTP methods are allowed.

### `Access-Control-Allow-Headers`
Tells the browser which request headers are allowed.

### `Access-Control-Allow-Credentials`
Used when cookies or other credentials are involved.

## 7) Cookies and Credentials

Cross-origin cookies are not sent automatically.
To send cookies:
- frontend must use `credentials: "include"`
- backend must use `credentials: true`

## 8) Important Point

CORS is a browser security feature, not backend authentication.

It does not protect your API by itself.
You still need:
- JWT
- sessions
- OAuth
- API keys

## 9) Real MERN Example

React app:
`http://localhost:5173`

Backend:
`http://localhost:5000`

The browser sends the request with an `Origin` header.
If the server allows that origin, the browser lets JavaScript read the response.

## 10) Common Mistakes

- CORS is not the same as authentication.
- Postman does not enforce CORS.
- The browser, not React, checks CORS.
- `200 OK` does not always mean the frontend can read the response.
- `origin: "*"` cannot be used with `credentials: true`.

## 11) Interview Ready Answer

CORS is a browser mechanism that controls whether a frontend from one origin can read a response from another origin. The browser checks the server's CORS headers, and if the server allows the origin, method, and headers, the response is exposed to the JavaScript code.

## 12) Revision Summary

- Origin = protocol + domain + port
- Different origin if any one part changes
- Browser enforces CORS
- Preflight uses `OPTIONS`
- Server allows origin using CORS headers
- Cookies need `credentials: include` and `credentials: true`
- `origin: "*"` cannot be used with credentials
- CORS is not a backend security system

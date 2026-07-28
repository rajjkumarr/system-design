# Lesson 7 — Cookies

## What is a Cookie?

A cookie is a small piece of data that the server asks the browser to store.

## Why Cookies Exist

We do not want to send the username and password with every request. Cookies help the browser remember the logged-in state.

## Simple Flow

1. User logs in
2. Server verifies credentials
3. Server sends `Set-Cookie`
4. Browser stores the cookie
5. Browser sends the cookie with the next request
6. Server identifies the user

## Example

Server response:

```http
Set-Cookie: sessionId=abc123
```

Next request:

```http
Cookie: sessionId=abc123
```

## Important Point

A cookie is not the user. It is only an identifier.

## Real MERN Example

After login, the browser automatically sends the cookie when calling protected routes like `/profile`.

## Common Mistakes

- Cookie is not the same as session.
- Cookie does not contain the full user data.
- Browser stores the cookie, not the server.

## Interview Ready Answer

A cookie is data stored in the browser and sent automatically with requests so the server can identify the user after login.

## Revision Summary

- Cookie is stored in the browser.
- Server creates it using `Set-Cookie`.
- Browser sends it automatically.
- It helps maintain login state.
- It usually contains a session ID or token.

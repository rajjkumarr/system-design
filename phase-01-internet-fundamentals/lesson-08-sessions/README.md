# Lesson 8 — Sessions

## What is a Session?

A session is data stored on the server for a logged-in user.

## Cookie vs Session

- Cookie = stored in the browser
- Session = stored on the server

## Why Sessions Exist

The cookie usually stores only a session ID. The server uses that ID to find the user data.

## Simple Flow

1. User logs in
2. Server creates a session
3. Server sends a cookie with the session ID
4. Browser stores the cookie
5. Browser sends the cookie on the next request
6. Server looks up the session and identifies the user

## Example

```text
sessionId = abc123
```

Server session data:

```json
{
  "userId": 101,
  "name": "Rajkumar",
  "role": "Admin"
}
```

## Why Sessions Are Useful

- Easy to log out users
- Easy to expire inactive users
- Easy to store roles and permissions

## Scaling Issue

If sessions are stored on only one server, another server may not know about them. This becomes a problem when the app has multiple servers.

## Interview Ready Answer

A session is server-side login state. The browser stores only the session ID in a cookie, and the server uses that ID to find the user's data.

## Revision Summary

- Cookie is in the browser.
- Session is on the server.
- Cookie usually contains session ID.
- Session stores user data.
- Multiple servers need shared session storage or another solution.

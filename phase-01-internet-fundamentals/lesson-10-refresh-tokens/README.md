# Lesson 10 — Refresh Tokens

## What is a Refresh Token?

A refresh token is a long-lived token used to get a new access token.

## Why Refresh Tokens Exist

Access tokens are short-lived for security. Refresh tokens help the user stay logged in without entering the password again and again.

## Token Pair

- Access Token = short-lived, used for normal API calls
- Refresh Token = long-lived, used only to get a new access token

## Simple Flow

1. User logs in
2. Server sends access token and refresh token
3. Client uses access token for API calls
4. Access token expires
5. Client sends refresh token to `/refresh`
6. Server verifies refresh token
7. Server issues a new access token
8. Client retries the request

## Why Two Tokens

If only one long-lived token is stolen, the attacker gets long access. With a short-lived access token, damage is limited.

## Important Point

The refresh token should be treated as highly sensitive.

## Common Storage Choice

Refresh token is often stored in an HttpOnly Secure Cookie.

## Real MERN Example

Login returns:

- Access Token for API requests
- Refresh Token for renewing access

## Common Mistakes

- Refresh token is not used for every request.
- Access token should not be too long-lived.
- Refresh token does not directly call protected APIs.

## Interview Ready Answer

A refresh token is used to obtain a new access token after the access token expires, so the user can stay logged in without repeated logins.

## Revision Summary

- Access token is short-lived.
- Refresh token is long-lived.
- Access token is used for APIs.
- Refresh token is used only for renewal.
- Refresh token must be protected carefully.

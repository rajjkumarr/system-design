# Lesson 11 — OAuth 2.0

## What is OAuth 2.0?

OAuth 2.0 is a way to let a user sign in using another trusted provider like Google without sharing the password with your app.

## Why OAuth Exists

Your app should never see the user's Google password. OAuth lets Google authenticate the user and then tells your app that the user is verified.

## Main Idea

- User logs in with Google
- Google verifies the user
- Google sends an authorization code
- Your backend exchanges the code for a Google token
- Your backend gets the user's profile
- Your app creates its own session or JWT

## Important Point

Your app should not use Google's token as its own login token. Google only confirms identity. Your app still needs its own login state.

## Simple Flow

1. User clicks `Continue with Google`
2. Browser goes to Google login page
3. User enters Google credentials on Google
4. Google asks for permission
5. Google sends an authorization code back
6. Backend exchanges the code for a Google token
7. Backend fetches user info from Google
8. Backend finds or creates the user in your database
9. Backend creates its own JWT or session
10. User is logged in to your app

## First Login vs Returning Login

- First time: create a new user in the database
- Next time: find the user and log them in

## Real MERN Example

The frontend shows a Google login button. After Google verifies the user, the backend maps the Google identity to the app's own user record and issues the app's JWT.

## Common Mistakes

- Your app never gets the Google password.
- The authorization code is not the password.
- Google token is not automatically your app token.
- Your database remains the source of truth for your app's users.

## Interview Ready Answer

OAuth 2.0 lets a user log in through a trusted provider like Google without sharing their password with my application. Google authenticates the user, sends an authorization code, and my backend exchanges it for user info. Then my app creates its own session or JWT.

## Revision Summary

- OAuth 2.0 is delegated login.
- The app never sees the Google password.
- Google sends an authorization code.
- Backend exchanges code for Google user info.
- App creates its own JWT or session.
- DB is still the source of truth.

# BoostLoop

BoostLoop - credit-based follow-for-follow, sub-for-sub, like-for-like exchange for all platforms, with campaigns, credits, referrals, wallet and admin panel.

## Live site

This repository is published with GitHub Pages. The site is a single static file, `index.html`, with no build step.

## Database: Firebase

- Firebase project: **Kinza Digital Hub**
- Sign-in: **Google only** (Firebase Authentication, Google provider).
- Database: **Firestore** (default database).
- The Firebase web configuration is embedded in `index.html` as the web app config for the Kinza Digital Hub web app.

## First-time setup

1. In the Firebase console, open Kinza Digital Hub > Firestore Database > Rules, and paste the contents of `firestore.rules`, then publish.
2. In Firebase Authentication > Settings > Authorized domains, make sure `guest52256.github.io` is listed (it is required for Google sign-in from the GitHub Pages site).
3. In GitHub, enable Pages for this repository: Settings > Pages > Build and deployment > Source: Deploy from a branch, Branch: main, Folder: / (root).

## What the site starts with

Production starts empty: no test campaigns, no test users, no sandbox rows. The first sign-in seeds only the default settings document and the editable example plans (Free, Pro, Creator) and gateways. Everything else is created by real users.

## Admin

Admin is not in the bottom navigation and is not linked anywhere user-side. It opens only from the secret hash route. See the Admin Overview note inside the app: at launch, restrict admin data to a designated admin Google account in Firestore rules, and rotate the secret route word, because a secret URL is hiding, not locking.

## Screenshots

Firebase Storage has no bucket provisioned on this project's Spark plan (Storage requires a Blaze billing upgrade). Screenshot uploads in this static version are therefore compressed client-side and stored as data URLs in their Firestore record, not in Firebase Storage.

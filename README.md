# संस्था श्री सक्षम — Cloud Login version

## What this version does
- Email + password signup/login using Supabase Auth.
- A unique account User ID (Supabase UUID) is shown after login.
- Cashbook data is stored in Supabase and syncs between devices when the **same account** logs in.
- Each account has its own private data protected by Row Level Security (RLS).
- Black/gold UI, round logo, edit/delete entries, CSV/JSON exports remain.

## Important
This ZIP is a static web app template. Cloud login will not work until you create a free Supabase project and configure it. Do not share your password or Supabase service_role key. Only use the anon/public key in config.js.

## Setup using only Android mobile
1. Open https://supabase.com in Chrome and create/sign in to an account. Create a new project and wait until it is ready.
2. In Supabase, open Project Settings > API (or Connect) and copy the Project URL and `anon` / publishable key. Never copy the `service_role` secret.
3. In this GitHub repository, upload/replace `config.js`. Edit it and replace `YOUR_SUPABASE_PROJECT_URL` and `YOUR_SUPABASE_ANON_KEY` with the values you copied. Commit.
4. In Supabase, open SQL Editor > New query. Copy all contents of `supabase_setup.sql` from this ZIP, paste and Run. This creates a private table with row-level security.
5. In Supabase Authentication settings, set your Site URL to the GitHub Pages URL. Signup may require email verification; verify the email before login.
6. Upload all files in this folder to the repository root, replacing same-named files, and commit. Keep `config.js`, `index.html`, `manifest.webmanifest`, `sw.js`, `logo-round.png`, `icon.svg`, `icon-192.png`, `icon-512.png` and `supabase_setup.sql` at root.
7. Open the published HTTPS website. Sign up with email and a password of at least 8 characters. Verify email if asked, then log in.
8. On another mobile, open the same published website and log in with the **same email/password** to see the same cashbook data.

## User ID and multiple users
A unique Supabase UUID is displayed as User ID. In this version, each login account owns its own private cashbook. To allow separate operator/viewer accounts to access one shared institution, a further membership/invitation system and role policies must be added; do not share a login password as a substitute.

## Existing local records
First successful login on a device uploads that browser's current local records if that account has no cloud record yet. If the account already has cloud data, the cloud data replaces the local view. Export a JSON backup before first login. Avoid first-login from multiple devices with different local records, because the first upload wins.

## Offline behavior
The interface files can be cached for offline opening, but login and cloud sync require internet. Changes made offline are currently saved locally and are not guaranteed to merge into cloud automatically. Reconnect and verify sync before relying on offline-entered records.

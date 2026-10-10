# My Cashbook (offline-first Android-friendly app)

A lightweight installable web app for personal income/expenses and business customer khata. Interface supports Hindi and English. Records are stored locally in the browser on the device.

## Features
- Dashboard with income, expense, and net balance
- Income, expense, udhar given, and udhar received transactions
- Customer list, phone field, customer balance, and transaction history
- Search and filter transaction history
- Today / this month / all-time reports
- Export CSV and JSON backup; restore JSON backup
- Hindi/English toggle
- Service worker cache for offline use after the first successful load

## Install on Android (recommended: install as an app)
1. Upload the contents of this folder to a static HTTPS host. Examples: GitHub Pages or another static web host. Keep all files in the same folder.
2. Open the hosted `index.html` URL in Chrome on Android while online.
3. In Chrome, open the ⋮ menu and choose **Install app** or **Add to Home screen**. The exact wording depends on your Chrome version.
4. Launch **My Cashbook** from your home screen. After the first load and service-worker caching, the app shell can open offline.
5. Make a JSON backup regularly using **Export backup** and store it somewhere safe.

## Important offline/data notes
- This package is a Progressive Web App (PWA), not a signed native APK. Android Chrome can install it to the home screen.
- A service worker requires HTTPS (or localhost); opening `index.html` directly from a file manager will not enable PWA installation/offline caching.
- The data is kept in local browser storage. It does not sync to other devices. Clearing Chrome/site data, uninstalling, or device failure may remove records. Export backups regularly.
- This starter app is not encrypted and has no login/PIN. Do not use it to store sensitive financial information on a shared phone.
- Income and “udhar received” increase the calculated net balance; expenses and “udhar given” decrease it. Customer balance is based only on udhar given minus udhar received.

## Files
- `index.html` — app UI and logic
- `manifest.webmanifest` — install metadata
- `sw.js` — offline app-shell cache
- `icon.svg`, `icon-192.png`, `icon-512.png` — app icons

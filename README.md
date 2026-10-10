# संस्था श्री सक्ष — Offline Cashbook

A mobile-friendly installable Progressive Web App (PWA) for managing separate institutions/businesses, cash-in, cash-out, opening balances, current balances, date-filtered entries and reports. Hindi and English are supported.

## Features
- Starts with an institution named **संस्था श्री सक्ष**
- Create multiple institutions; each institution has separate records and balances
- Opening balance for each institution
- Cash In / Cash Out entries with amount, date, description, person/party and payment mode
- Automatic total cash-in, total cash-out and remaining balance calculations
- Search entries and filter by type and date range
- Today / this month / all-time summaries
- CSV report export and JSON backup/restore
- Local storage; no account or cloud required
- PWA manifest and service worker for installation and offline app shell

## Update your existing GitHub Pages app from Android
1. Open the GitHub repository where the current app is published.
2. For each file below, open the file in the repository, tap the pencil/edit menu or upload replacement file, replace it with the file from this folder, and commit the change:
   - `index.html`
   - `manifest.webmanifest`
   - `sw.js`
   - `icon.svg`
   - `icon-192.png`
   - `icon-512.png`
3. Make sure all these files are at the repository root, next to each other (not inside an extra folder).
4. Wait for GitHub Pages to deploy, then open your same Pages URL in Chrome.
5. If the old version remains: Chrome > Settings > Site settings > All sites > your GitHub Pages site > Clear & reset, then reopen the site online. **Export a backup first if you have entered records.**
6. If already installed, launch it while online once to let the new service worker update. If necessary remove the old home-screen shortcut and install again from Chrome's menu.

## Important data notes
- Data is stored locally in the browser/device, not on GitHub or in a cloud database.
- Do not clear browser/site data or uninstall before exporting a JSON backup.
- GitHub Pages files are public if the repository is public; your financial records are not uploaded to GitHub by this app.
- This is a PWA, not a native APK. It can be installed to the Android home screen from Chrome over HTTPS.

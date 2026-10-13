# संस्था श्री सक्षम — Cashbook PWA

This is a mobile-friendly installable Progressive Web App for institution cashbook, income/expense entries, reports, Excel import/export, backup, logo crop, and Supabase login/cloud sync.

## Files
- `index.html` — app UI and functionality
- `config.js` — Supabase project URL and public anon/publishable key
- `supabase_setup.sql` — create the per-account cloud data table and RLS policies
- `sw.js`, `manifest.webmanifest`, `icon.svg`, `icon-192.png`, `icon-512.png` — install/offline support
- `logo-round.png` — default logo

## Password reset setup (required)
1. In Supabase Dashboard open **Authentication → URL Configuration**.
2. Set **Site URL** to your GitHub Pages app URL (for example `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`).
3. Add that exact app URL to **Redirect URLs**. If your GitHub Pages app is under a repository path, add the full path URL too. The app sends password reset links back to the current app URL.
4. Under **Authentication → Email**, make sure the password recovery email template contains `{{ .ConfirmationURL }}` as the reset link. Supabase's standard recovery template normally already does this.
5. For real use, configure SMTP under Supabase Auth email settings; the default email service is rate-limited and best-effort.
6. Test **Forgot password?** from the login screen. Enter the account email, open the message in Inbox/Spam on the same device/browser if possible, follow the link, then enter and confirm the new password.

Password reset uses Supabase Auth's `resetPasswordForEmail()` and `updateUser({ password })`. The app will not tell you whether an email address has an account, to avoid exposing registered accounts.

## Supabase config
`config.js` must contain your own project URL and public anon/publishable key:

```js
window.SANSTHA_CONFIG = {
  SUPABASE_URL: 'https://YOUR-PROJECT.supabase.co',
  SUPABASE_ANON_KEY: 'YOUR_PUBLIC_ANON_OR_PUBLISHABLE_KEY'
};
```

Use the correct existing config from your GitHub repository. Never put a `service_role` or secret key in a browser app.

## Upload to GitHub Pages
1. Download and extract the ZIP.
2. Upload/replace all files in the repository root.
3. **Keep your existing `config.js`** if it already contains your actual Supabase URL and public key; the ZIP's config is intentionally a placeholder.
4. Commit the changes and wait for GitHub Pages to publish.
5. Open the website online once, refresh, then reopen the installed PWA.

## Important notes
- The login account and cloud data row are per Supabase user. Different accounts do not automatically share records.
- The current role dropdown is a local UI preference only, not secure team permissioning. Do not use it as a security boundary.
- Back up records before replacing files or clearing browser data.
- The reset email may not arrive if SMTP/email delivery is not configured, the address is wrong, or provider limits are reached.

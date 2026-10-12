# Sanstha Shri Saksh Cashbook

Mobile-first Hindi cashbook PWA with black/gold theme, Supabase login/cloud sync, cash-in/cash-out entries, reports, JSON backup/restore, CSV export and Excel import.

## This update
- Added Account tab with login email, user UUID, copy User ID and logout.
- Added institution rename form.
- Restored adjustable logo crop controls (zoom and horizontal/vertical position) with Apply Logo.
- Updated service worker cache version and network-first handling for app/config files.

## Deploy
1. Download a JSON backup from the app before replacing files.
2. Upload the updated files to the existing GitHub Pages repository.
3. **Keep your existing configured `config.js`** if it already contains the correct Supabase project URL and public anon/publishable key. The `config.js` included in this ZIP is a template with placeholders.
4. Run `supabase_setup.sql` in Supabase SQL Editor if not already run.
5. Open the GitHub Pages URL in Chrome with internet, refresh, then close/reopen the installed PWA.

## Important limitations
Secure sharing with different permissions for four separate people is **not yet implemented** by this update. A local role dropdown is not a security boundary. Real team access requires institution membership records, server-side Row Level Security policies, and app logic that restricts each user to only the institutions/summary they are allowed to see. Do not claim or use local-only roles as secure access control.

Never put a Supabase `service_role` key in `config.js`. Use only the public anon/publishable key.

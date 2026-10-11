# संस्था श्री सक्षम

- Multiple institutions with separate cash-in/cash-out transactions.
- Automatic total in, total out, opening balance and remaining balance.
- Hindi/English UI, offline device storage, JSON backup/restore and CSV report.
- Excel (`.xlsx`, `.xls`) and CSV import. Reads the first worksheet and recognizes common English/Hindi headings for amount, date, type, description, party and payment mode.
- Uses the uploaded logo artwork for app icons.

## Import older Excel records
1. Select the institution where records should be imported.
2. Open Home → Backup & Data → Excel आयात करें.
3. Select an Excel/CSV file and confirm the number of rows.
4. Check totals and export a backup afterwards.

The Excel reader loads from jsDelivr, so internet is needed once to load the library when importing Excel. Normal cashbook use remains offline after the app is cached.

## GitHub Pages
Upload all files from this folder directly to repository root, replacing old files. Do not upload only the ZIP. In Settings → Pages, select `main` and `/(root)`.

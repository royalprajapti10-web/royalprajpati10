# संस्था श्री सक्षम

Offline-first installable cashbook PWA. Features include separate institutions, cash in/out, running totals, local JSON backup/restore, CSV report, Excel/CSV import (requires loading SheetJS once online), editing and deleting entries, and changing the institution logo in-app.

## GitHub Pages update
Upload the contents of this folder to the repository root, replacing files with the same names. Commit changes and enable Pages from `main` / root. Keep a JSON backup before updating. Browser local data is stored on the device and does not sync across devices.

## Notes
The logo change is saved in that device's local browser. Image selection uses a centered square crop. Excel import currently reads the first worksheet; review imported records carefully.

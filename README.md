# Cath Lab Inventory Manager

Offline-first, single-user cath lab stock and batch manager. Designed for use on a phone and computer with manual JSON backup/import between devices.

## Files
- `index.html` — application structure
- `styles.css` — responsive interface
- `app.js` — IndexedDB storage and application logic
- `manifest.json` — installable PWA settings
- `sw.js` — offline app shell cache
- `icon-192.png`, `icon-512.png` — app icons

## Deploy to GitHub Pages
1. Open your `Cath-Lab-Inventory` repository.
2. Choose **Add file → Upload files**.
3. Upload all files in this folder (not the ZIP itself).
4. Commit to the `main` branch.
5. Go to **Settings → Pages**.
6. Under Build and deployment, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then Save.
7. Wait for the Pages URL to become available.

## Use on devices
Open the published HTTPS URL in Chrome. On Android, use Chrome menu → **Add to Home screen** or **Install app**. On desktop Chrome/Edge, use the install icon or browser menu.

## Data and synchronisation
All data is stored locally in the browser's IndexedDB. GitHub Pages hosts only the application files. No inventory records are uploaded to GitHub and there is no automatic cloud sync.
- Export JSON backup from the device with the latest data.
- Transfer it to the other device.
- Import it using **Merge** to add records not already present.
- Use **Replace** only when you intentionally want to overwrite all data on the receiving device.

Avoid simultaneous independent edits on both devices. Merge skips matching record IDs; it does not reconcile conflicting edits to the same record.

## Important
- Do not store patient names, MRNs, dates of birth, or other patient-identifiable information.
- This is an inventory record tool, not a validated hospital ERP or regulatory traceability system. Verify batch and expiry details against original packaging and purchase records.
- Keep regular backups in a secure location.

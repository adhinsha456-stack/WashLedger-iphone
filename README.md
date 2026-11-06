# WashLedger iPhone PWA

This package wraps the supplied WashLedger HTML app as an installable Progressive Web App (PWA), preserving its interface and localStorage-based records.

## Files
- `index.html` — original app with PWA metadata and service-worker registration
- `manifest.json` — install metadata and icons
- `service-worker.js` — caches the app shell and best-effort caches external assets
- `icons/` — app icons

## Publish free using GitHub Pages
1. Create/sign in to GitHub.
2. Create a new repository (for example `washledger`).
3. Upload all files and the `icons` folder from this package (not the ZIP itself).
4. In repository **Settings → Pages**, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
5. Wait for the published Pages URL.

## Install on iPhone
1. Open the published URL in Safari while connected to the internet.
2. Wait for the app to load fully once (this lets the service worker cache the app shell and external icon/font resources where possible).
3. Tap Safari's **Share** button → **Add to Home Screen** → **Add**.
4. Launch WashLedger from its Home Screen icon. After the first successful cache, the app shell can open offline.

## Important
- Attendance/salary records use browser `localStorage` on that device. They do not automatically sync between iPhone and other devices.
- Keep using the same Home Screen app/browser storage. Clearing Safari website data may erase locally stored records.
- Use the app's Backup feature regularly and save the JSON backup somewhere safe.
- The current HTML has pre-filled sample records for the current date and a simple login screen. Review those before using real records.
- Offline availability of Google Fonts/Lucide CDN assets is best-effort; core app shell is cached.

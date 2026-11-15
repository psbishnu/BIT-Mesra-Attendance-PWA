# BIT Mesra Student Attendance — PWA

This project packages the supplied HTML attendance app as an installable Progressive Web App. It does **not** generate an APK.

## Publish using GitHub Pages

1. Create a **new public** GitHub repository named `BIT-Mesra-Attendance-PWA` (the project files are public, so never upload student records or backups).
2. Extract this ZIP and upload the **contents**: `index.html`, `manifest.webmanifest`, `service-worker.js`, and the `icons` folder. Keep their paths exactly as shown.
3. Commit changes.
4. Go to **Settings → Pages → Build and deployment**; select **Deploy from a branch** → branch **main** → folder **/(root)** → **Save**.
5. Open the HTTPS GitHub Pages address in Android Chrome; choose **⋮ → Add to Home screen / Install app**.
6. Open the app online once to cache it. Then test it with mobile data/Wi-Fi off. Back up attendance data often.

## Storage and privacy

- Student attendance data is stored on the local device in browser IndexedDB, with localStorage fallback, as provided by the original app.
- GitHub Pages hosts the **application code** publicly, not your attendance database. Do not commit real student data or export files.
- Data can be lost if browser site data is cleared, app storage is cleared, or the device is lost/reset. Export Excel/backup regularly.
- This PWA's stored data is separate from data previously saved in an HTML file opened directly with `file://`, in another browser, or in an Android WebView APK. Import from an export/backup when migrating.
- Offline support needs an initial online visit. App shell caching does not guarantee successful recovery of every kind of device failure.
- Changing `service-worker.js`'s `CACHE_NAME` (e.g. v1 to v2) is recommended when publishing updated application files; deployed edits otherwise may remain cached.
- Browser installation options vary across devices.

## Source

`index.html` is based on the supplied `BIT_Mesra_Student_Attendance_Late_Registration(1).html`. Only PWA head tags and service-worker registration were added.

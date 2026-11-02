# PhotoCurator Studio (GitHub Pages package)

## Upload
Upload/replace these files in the **root of your existing GitHub repository**:
- `index.html`
- `styles.css`
- `app.js`
- `manifest.webmanifest`
- `sw.js`
- `README.md`

Do not put them inside an extra nested folder. GitHub Pages should publish from the repository root (or the same folder your current site uses).

## Important before replacing
1. Download a ZIP/backup of your current repository first.
2. The app stores client/project/SSD records and selection metadata in IndexedDB in the current browser profile.
3. Do not clear site data if you need those records. This update does not migrate the previous PhotoCurator browser database automatically.
4. This is a static local-first app. Records do not synchronize across computers or browsers. Use **Backup workspace JSON** to export dashboard records and **selection backup JSON** for a project's selected filenames.

## Workflow
1. Add clients (the starter workspace includes Baba, She, and He).
2. Create projects and set client, start/end date, package limit, and status.
3. Add shoot days and activities.
4. Add SSD records in the SSD Inventory.
5. Assign a drive to a project, then mark it Sent with recipient/date/expected return.
6. When it comes back, mark Received and record the return date.
7. Select the project, load its source photo folder, and use slideshow / Like / Unlike / Undo.
8. My Likes lets the client review selection and export copies or selection JSON.

## Photo safety
- The app does not upload photo bytes to GitHub or any server.
- Original source photos are not intentionally modified, moved, renamed, or deleted.
- Export with a selected output directory creates a `Liked` subfolder and copies photos there. Existing files are given a suffix rather than overwritten.
- If using browser downloads, the browser controls the destination and duplicate-name behavior.
- Always choose an output destination separate from your originals. Check the exported folder before delivery.

## Browser notes / limitations
- Recommended: Windows Chrome or Edge, because File System Access API support is strongest there.
- Folder import reads files recursively (Chromium directory picker) or through the browser's folder input.
- JPEG/PNG/WebP/GIF/BMP/TIFF and several RAW filename extensions are recognized, but RAW rendering is not guaranteed. Many RAW files do not contain browser-displayable previews; use JPEG previews or convert/sidecar JPGs for selection until RAW preview support is tested.
- This version treats same-name files as the same selection key in Like/Unlike; avoid duplicate identical filenames in different subfolders or check selection manifests carefully.
- Slideshow timer and file handling require the app to be open. It does not run as a background client agent.
- SSD tracking is a manual record. PhotoCurator cannot physically detect whether a drive is plugged in or returned.
- No public client gallery/link sharing or online activity tracking is included.

## Offline/PWA
The service worker caches the app shell after first load. GitHub Pages must be served over HTTPS for PWA and folder picker features.

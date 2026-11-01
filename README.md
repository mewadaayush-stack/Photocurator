# PhotoCurator Web/PWA prototype

## Run on Windows
Extract the ZIP. In this folder run `python -m http.server 8000` and open `http://localhost:8000` in Chrome/Edge. Folder selection and folder export work best in Chromium on localhost/HTTPS.

## Android
Deploy these static files to an HTTPS host such as GitHub Pages. Open the URL in Chrome, choose photos (folder picker availability varies), then use browser menu > Install app/Add to Home screen.

## Features
- Dark responsive UI; folder or multiple-file import.
- Like & Next, Next, Previous, Undo, automatic sequential playback and speed selection.
- Target achievement can exceed 100%.
- Liked gallery and export copies to a chosen folder where File System Access API is supported; otherwise downloads files individually.
- IndexedDB persists liked image copies and project counters locally.
- Manual Google Drive backup: export then upload via Drive. No Drive API, login or automatic cloud upload.

## Important limitations
- Prototype source files are not a compiled APK. This is a web app/PWA.
- Source files are held in memory for the active session; re-import the source folder after a browser restart. Liked image blobs and counters are stored in IndexedDB. Clearing browser storage may erase them.
- On Android, folder selection/writing support varies by browser. Multi-file picker and individual downloads are fallback.
- If you choose a writable liked-copy folder before reviewing (supported Chromium browsers), each Like immediately writes a separate copy there and also stores the blob in IndexedDB. If folder writing is unavailable, likes are saved in IndexedDB and can be exported later.
- Auto mode advances sequentially and does not auto-like. Tap Like to save.
- Test with a small folder before using a 10,000-photo library. Browser memory/storage quotas vary.
- HEIC previews may not work in every browser.
- No external libraries or network photo upload are used.

# Course Completion Tracker — PWA

This is a self-contained web app (no build tools, no React needed at runtime). It works fully offline once loaded and installs to an Android home screen like a native app.

## Files
- `index.html` — the entire app
- `manifest.json` — app name/icons/colors for install
- `sw.js` — service worker, caches everything for offline use
- `icon-*.png` — app icons

## Why it needs hosting first
Android's "Add to Home Screen" install prompt requires the app be served over **HTTPS** (or `localhost`) — opening the HTML file directly from your phone's file system (`file://`) won't trigger a real install. You only need to host it once; after that it works offline.

### Easiest option: GitHub Pages (free, ~2 minutes)
1. Create a new GitHub repo, upload these 7 files to the root.
2. Repo Settings → Pages → Deploy from branch → `main` / root.
3. Visit the given `https://yourname.github.io/reponame/` URL on your Android phone in Chrome.

### Also easy: Netlify Drop
1. Go to https://app.netlify.com/drop in a browser.
2. Drag this folder in. You get an instant `https://...netlify.app` URL.
3. Open that URL on your phone.

### Or: any static host you already use
Any static file host works (Vercel, Cloudflare Pages, Firebase Hosting, your own server) — just upload all 7 files to the same folder and visit the URL.

## Installing on Android
1. Open the hosted URL in **Chrome** on your Android phone.
2. Tap the **⋮** menu → **Add to Home screen** (or Chrome may show an automatic "Install app" banner).
3. Confirm — it now launches full-screen from your home screen, with no browser bar, and works offline.

## Notes
- All your data (course setup, sessions, streaks) is saved in the phone's local browser storage — it stays on-device and persists across closes/reopens.
- If you ever want a "real" installable `.apk` (for the Play Store or sideloading outside a browser), this same `index.html` can be wrapped in Capacitor — say the word and I'll generate that project too.

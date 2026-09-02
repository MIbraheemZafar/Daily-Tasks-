# Ibraheem's Tracker

A Deen + Freelancer daily tracker (prayers, non-negotiables, tasks, streaks, weekly/monthly progress) — installable as an app via PWABuilder.

## 1. Upload to GitHub

1. Create a new GitHub repo (e.g. `ibraheem-tracker`).
2. Upload **all files in this folder** keeping the structure:
   ```
   index.html
   manifest.json
   sw.js
   icons/icon-192.png
   icons/icon-512.png
   icons/icon-512-maskable.png
   ```
3. Commit to the `main` branch.

## 2. Turn on GitHub Pages

1. In the repo: **Settings → Pages**.
2. Under "Build and deployment", set **Source: Deploy from a branch**.
3. Branch: `main`, folder: `/ (root)` → **Save**.
4. Wait ~1 minute, then GitHub gives you a live URL like:
   `https://<your-username>.github.io/ibraheem-tracker/`
5. Open that URL and confirm the tracker loads correctly.

## 3. Build the app with PWABuilder

1. Go to **https://www.pwabuilder.com**.
2. Paste your GitHub Pages URL from step 2 and click **Start**.
3. PWABuilder will scan the site and should report the manifest, service worker, and icons as ✅ (all included here).
4. Click **Package for stores** to generate an Android (Google Play), Windows, or iOS package, or just use **"Install"** directly from Chrome/Edge for a quick installable app.

## Notes

- All progress data is stored locally in the browser (`localStorage`), so it stays on whichever device installs the app.
- Tasks are fully editable in-app: Settings (⚙️) → **Manage Tasks** to add or remove tasks — no code changes needed.
- If you update `index.html` later, bump the `CACHE_NAME` value in `sw.js` (e.g. `v5` → `v6`) so installed apps pick up the changes.

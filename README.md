# Ibraheem's Tracker

A Deen + Freelancer daily tracker (prayers, non-negotiables, tasks, streaks, weekly/monthly progress) — installable as an app via PWABuilder.

## File structure (flat — no subfolders)

```
index.html
manifest.json
sw.js
icon-48.png
icon-72.png
icon-96.png
icon-128.png
icon-144.png
icon-152.png
icon-192.png
icon-384.png
icon-512.png
icon-512-maskable.png
```

All icons sit at the **root** of the repo, next to `index.html`. This matches how drag-and-drop uploads land on GitHub, so there's no `icons/` subfolder to worry about.

## Fixing your existing repo (`Daily-Tas...`)

Your repo currently has a leftover `icon` file/folder and the PNGs sitting loose at root while `manifest.json` still pointed at `icons/...`. To fix it:

1. Open your repo on GitHub → click into the stray **`icon`** item → use the **⋯ / trash icon** to delete it (it's not used).
2. Click **Add file → Upload files**, then drag in every file from this package **at once** — select all of them together so they all land at the root (not inside a folder). Make sure `manifest.json`, `sw.js`, and `index.html` overwrite the existing ones.
3. Commit directly to `main`.
4. Give GitHub Pages a minute to redeploy, then re-run your site through **pwabuilder.com** — the icon errors should be gone.

## 1. Upload to GitHub (fresh repo)

1. Create a new GitHub repo (e.g. `ibraheem-tracker`).
2. Click **Add file → Upload files** and drag in **all files from this package together** (so everything lands flat at the root — see structure above).
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
3. PWABuilder should now report the manifest, icons, and service worker as ✅.
4. Click **Package for stores** to generate an Android (Google Play), Windows, or iOS package, or just use **"Install"** directly from Chrome/Edge for a quick installable app.

## Notes

- All progress data is stored locally in the browser (`localStorage`), so it stays on whichever device installs the app.
- Tasks are fully editable in-app: Settings (⚙️) → **Manage Tasks** to add or remove tasks — no code changes needed.
- If you update `index.html` later, bump the `CACHE_NAME` value in `sw.js` (e.g. `v6` → `v7`) so installed apps pick up the changes.

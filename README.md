# Kit Log — Camera Gear Tracker

A self-contained web app for tracking your camera gear, condition photos, service history, and combo kits (Wedding Kit, Sports Kit, etc). No account, no server, no internet connection required — everything is stored privately on your own phone.

## What's in this folder
- `index.html` — the app itself
- `manifest.json`, `service-worker.js`, `icon*.png/svg` — make it installable as a home-screen app with an offline-capable icon

## Option A — Zero setup, use it right now
1. Copy this whole folder onto your Android phone (e.g. via a USB cable, Google Drive, or emailing it to yourself).
2. Open `index.html` with **Chrome**.
3. Tap Chrome's ⋮ menu → **Add to Home screen**. You now have an app icon on your home screen.

This works fully — adding gear, taking photos, building kits, everything persists on the device. The only limitation is the "Add to Home Screen" shortcut opens inside a regular Chrome tab rather than a fully chrome-less standalone window, since `file://` pages skip some installability checks.

## Option B — True installable PWA (recommended)
Host the folder somewhere with a real URL, then it installs like a proper app (own window, works offline, icon matches your phone's other apps). Any static host works and all of these have free tiers:
- **GitHub Pages** — create a repo, upload these files, enable Pages in Settings.
- **Netlify Drop** — netlify.com/drop, literally drag this folder in, get a URL instantly.
- **Vercel** — similar drag-and-drop / CLI deploy.

Once hosted, open the URL in Chrome on your phone → you'll see an **Install app** prompt (or ⋮ menu → **Install app**). It'll behave exactly like a native app from then on, including offline use.

## Using the app

**Inventory tab** — your full gear list. Tap **+** to add a camera body, lens, SD card, or any accessory: brand/model, serial number, condition, photos of its current condition, storage location, purchase info, and a running service history log (dates, what was done, cost). Tap any item to see full details or edit it. Search and category chips at the top help you find things fast.

**Kits tab** — build combos of gear for specific shoots (e.g. "Wedding Kit," "Sports Kit," "Indoor Studio Kit"). Pick any items from your inventory and save. Each kit shows a **READY** badge that warns you if something in that kit is currently on loan, in repair, or retired — so you know before you pack the bag.

**Overview tab** — a quick snapshot: total items, estimated total value, items by category, and anything that currently needs attention (on loan / in repair).

**Settings (gear icon, top right)** — export a full JSON backup (including photos) or import one back in. Since all data lives only in this browser/device, it's worth exporting a backup occasionally — especially before clearing browser data or switching phones.

## Notes on photos
Tapping "Add" on a photo opens your camera directly (or your gallery, depending on your phone). Photos are automatically resized and compressed before saving so your gear list stays fast even with lots of items.

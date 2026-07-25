# Camera-tory — Camera Gear Tracker

A self-contained web app for tracking your camera gear, condition photos, service history, and combo kits (Wedding Kit, Sports Kit, etc). No account, no server, no internet connection required — everything is stored privately on your own phone.

## What's in this folder
- `index.html` — the app itself
- `manifest.json`, `service-worker.js`, `icon*.png/svg` — make it installable as a home-screen app with an offline-capable icon

## Option A — Use the hosted version (recommended for most people)
Camera-tory is already hosted on GitHub Pages, so there's nothing to set up.
1. Open this link on your phone: **https://xavierpang32.github.io/cameratory-free/**
2. **On Android (Chrome):** you'll see an **Install app** prompt, or use the ⋮ menu → **Install app**.
3. **On iPhone/iPad (Safari):** tap the **Share** button (square with an arrow) → **Add to Home Screen** → confirm the name and tap **Add**. Chrome/Edge on iOS can do this too, but Safari is the most reliable path. There's no automatic install prompt on iOS — it's a couple of manual taps every time on a new device, and Apple doesn't offer a way to shortcut that.

Either way, it installs like a native app from then on — its own home-screen icon, full-screen with no browser address bar, and works offline once it's loaded the first time. All your gear, photos, and kits are still stored only on your device, never uploaded anywhere.

## Option B — Zero setup, run it locally on your own phone
For Android only, and only worth it if you'd rather not depend on GitHub being reachable, or want the app fully offline from the very first launch.
1. Copy this whole folder onto your Android phone (e.g. via a USB cable, Google Drive, or emailing it to yourself).
2. Open `index.html` with **Chrome**.
3. Tap Chrome's ⋮ menu → **Add to Home screen**. You now have an app icon on your home screen.

This works fully — adding gear, taking photos, building kits, everything persists on the device. The only limitation is the "Add to Home Screen" shortcut opens inside a regular Chrome tab rather than a fully chrome-less standalone window, since `file://` pages skip some installability checks.

**This local-file approach isn't reliable on iOS** — Safari's handling of local files doesn't consistently support the storage and offline features this app needs. iPhone/iPad users should use Option A or C instead.

## Option C — Host your own separate copy
Only needed if you want to customize or fork the app, or just don't want to rely on the link in Option A. Any static host works and all of these have free tiers:
- **GitHub Pages** — create a repo, upload these files, enable Pages in Settings.
- **Netlify Drop** — netlify.com/drop, literally drag this folder in, get a URL instantly.
- **Vercel** — similar drag-and-drop / CLI deploy.

Once hosted, installation works exactly like Option A — open your own URL in Chrome on Android or Safari on iOS and follow the same install steps above.

## Using the app

**Inventory tab** — your full gear list. Tap **+** to add a camera body, lens, SD card, film stock, or any accessory: serial number, condition, photos of its current condition, storage location, purchase info, and a running service history log (dates, what was done, cost — supports multi-line notes that grow as you type). Tap any item to see full details or edit it.
- **Search** by name, serial number, or location — pick which field with the small dropdown next to the search box. Search is fuzzy, so a few letters in the right order (like "cnr5" for "Canon EOS R5") still finds it.
- **Category chips** filter by gear type; **status filter** (All Statuses / In Storage / In Use / On Loan / In Repair / Retired-Sold) and **sort** (Newest / Oldest / Custom / Name A–Z / Name Z–A) sit together below the chips and can be combined with search and category freely.
- **Swipe left on any item** to reveal a drag handle — press and drag it up or down to reorder your list. The new position saves automatically and the sort dropdown switches to **Custom** so your arrangement actually sticks (picking a different sort later won't lose it — your custom order is remembered and comes right back when you switch back to Custom).
- **Swipe right on any item** to select it — this puts the whole list into selection mode, where tapping any other item (no swiping needed) adds or removes it from the selection. A **Delete** button appears in that same row (next to where the status/sort dropdowns were) showing how many items are selected; tap it and confirm to remove them all at once, or tap **Cancel** to back out without deleting anything.

**Kits tab** — build combos of gear for specific shoots (e.g. "Wedding Kit," "Sports Kit," "Indoor Studio Kit"). Pick any items from your inventory and save. Each kit shows a **READY** badge that warns you if something in that kit is currently on loan, in repair, or retired — so you know before you pack the bag. Kits get their own **sort** control (Newest / Oldest / Custom / Name A–Z / Name Z–A), and the same swipe gestures as gear: swipe left to drag-reorder your kits, swipe right to multi-select and bulk-delete them.

**Overview tab** — a quick snapshot: total items, estimated total value, items by category, and anything that currently needs attention (on loan / in repair).

**Settings (☰ icon, top right)** — switch the app's language (English or 简体中文 Simplified Chinese), export a full JSON backup (including photos), or import one back in. Since all data lives only in this browser/device, it's worth exporting a backup occasionally — especially before clearing browser data or switching phones. This matters a bit more on iOS: Safari is historically stricter than Chrome about evicting site storage after long inactivity, though apps added to the home screen are exempted from its more aggressive cutoffs. Either way, an occasional backup is cheap insurance.

**About tab** — app info, version, and a credits section linking to this project's page ([xavierpang32.github.io/cameratory-free](https://xavierpang32.github.io/cameratory-free/)).

## Notes on photos
Tapping "Add" on a photo opens your camera directly (or your gallery, depending on your phone). Photos are automatically resized and compressed before saving so your gear list stays fast even with lots of items.

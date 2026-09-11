# Planner

A 15-minute day planner. Works offline, installs to the Android home screen.

## Put it online

1. Create a repository and upload all six files to the root: `index.html`, `sw.js`, `manifest.json`, `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`.
2. Settings → Pages → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`. Save.
3. Wait a minute, then open `https://<user>.github.io/<repo>/` on the phone in Chrome.
4. Chrome menu → **Add to Home screen**. It installs as a standalone app.

HTTPS is required for the service worker, and GitHub Pages provides it.

## Using it

- **Tap a row** to type. Enter jumps to the next row. Everything saves as you type.
- **Long-press a row** to write a note. A black triangle marks rows that have one; tap the triangle to reopen it.
- **‹ ›** move between days. Tap the date for a calendar.
- Rows with the same text in a row are drawn as one block.
- Menu (☰): copy another day over this one, clear the day, change which hours are shown, save or load a backup file.

## Where the data lives

In the browser's local storage on that one device. Nothing is uploaded anywhere. Clearing Chrome's site data deletes it, so use **Save backup file** now and then.

## After you edit the app

Change `var CACHE = "planner-v1"` in `sw.js` to `v2`, `v3`, and so on. Without that, installed phones keep serving the old cached copy.

# Planner

A 15-minute day planner. Works offline, installs to the Android home screen.

## Put it online

1. Create a repository and upload these six files to the root: `index.html`, `sw.js`, `manifest.json`, `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`. (This README is optional.)
2. Settings → Pages → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`. Save.
3. Wait a minute, then open `https://<user>.github.io/<repo>/` on the phone in Chrome.
4. Chrome menu → **Add to Home screen**. It installs as a standalone app.

HTTPS is required for the service worker, and GitHub Pages provides it.

## Using it

Two views, switched with the tabs along the bottom.

### Day

- **Tap a row** to type. Enter jumps to the next row. Everything saves as you type.
- **×** blanks the slot. If the slot has a note, it asks first.
- **↓** copies the slot into the one below it. Tap it down the column to stretch a task over an hour.
- Both buttons appear only on slots that have something in them.
- **Long-press a row** to write a note. A black triangle marks rows that have one; tap the triangle to reopen it.
- **‹ ›** move between days. Tap the date for a calendar.
- Repeated text is shown once: a block of identical slots reads as a single entry with no dividing lines. Tap any slot in the block to see and edit its own copy of the text.
- Menu (☰): copy another day over this one, clear the day, change which hours are shown, save or load a backup file.

### List

Everything you owe, all dates at once — assignments, reading, errands.

- **+** adds an item: title, due date, subject, status, notes.
- **Tap the box** to cycle its status: empty (not started) → filled (scheduled) → ✓ (done).
- **Tap the row** to edit or delete it.
- Items sort themselves into Overdue, Due today, Next 7 days, Later, No due date and Done. Overdue shows in red.
- The red number on the List tab counts unfinished items due today or already late.
- Menu (☰) → **Delete finished items** clears out the Done section.

The two views are independent. Marking something *scheduled* is your own call — it does not check the day grid.

## Where the data lives

In the browser's local storage on that one device. Nothing is uploaded anywhere. Clearing Chrome's site data deletes it, so use **Save backup file** now and then. The backup covers both the day plans and the list.

## After you edit the app

Change `var CACHE = "planner-v4"` in `sw.js` to `v5`, `v6`, and so on. Without that, installed phones keep serving the old cached copy.

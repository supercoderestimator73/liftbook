# Liftbook

A push / pull / legs logbook that runs as a home-screen app on an iPhone. No account, no server:
everything is stored on the phone, and backups are files you keep yourself.

## Publish (GitHub Pages)

1. Put every file in this folder at the root of a repository (or in its own folder), including `fonts/`.
2. Settings → Pages → deploy from the main branch.
3. Open the page URL in Safari on the phone → Share → **Add to Home Screen**.

After you change `index.html`, bump `CACHE` in `sw.js` (`v1` → `v2`) so phones pick up the new version.
On the phone, More → **Check for updates** reloads from the web.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app. The program lives at the top of the script (`DEFAULT_PROGRAM`); it can also be edited in the app. |
| `sw.js` | Service worker: works offline, page is network-first so updates arrive. |
| `manifest.webmanifest`, `icon-*.png`, `apple-touch-icon.png` | Home-screen install. |
| `fonts/` | Bungee and Permanent Marker (SIL Open Font License, licenses included). |

## Load notation

`P` is a 45 lb plate per side. `1P` = 45, `2P+25` = 115, `25P` = a single 25. In the weight sheet you can
type `2p+25`, `25p`, `2x45` or plain pounds. Lifts set to "Pounds" take plain numbers.

## Goal logic

Each lift has a rep range (defaults to the planned reps up to +1/+2/+3). Looking at the last time it was done:

- every set at or above the top of the range → weight goes up one step, reps back to the bottom
- every set at or above the bottom → one more rep
- a set below the bottom → repeat the same goal
- well below → back off one step

Blocks: the week counter runs from the block start (More → Training block). With the volume ramp on, every lift
gets +1 set in the back half of the block. In week 1 of a new block every lift's goal bumps the weight.

## Backups

More → Back up shares a `.json` file (save it to Files or iCloud Drive). Restore merges a backup into the phone.
Export CSV gives one row per logged set for a spreadsheet.

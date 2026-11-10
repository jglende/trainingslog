# Trainingslog
 
A simple offline workout tracker for Push/Pull/Legs training. Log sets, reps, weight and rest times per day, mark rest days, and see your progress compared to the previous week.
 
The app runs entirely in the browser, can be installed as a Progressive Web App (PWA), and keeps all data on your device.
 
> The interface is in German.
 
## Features
 
- **Push/Pull/Legs days**: Assign each day a type (Push, Pull, Legs or Rest). Exercises belong to a type and only appear on matching days.
- **Rotation suggestion**: The app suggests the next day type based on your last training day.
- **Sets, reps, weight and rest**: Log every set individually, including the rest time after it.
- **Rest timer**: A built-in stopwatch measures your rest and fills in the time automatically. The screen stays on while it runs.
- **Weekly comparison**: Each exercise is compared with the matching session from the previous week (volume, max weight, total reps). Last week’s values appear as placeholders in the input fields.
- **Weekly overview**: Total volume, volume per Push/Pull/Legs, training days, rest days and how many exercises improved.
- **8-week trend**: A small sparkline per exercise shows its weekly volume.
- **Bodyweight exercises**: Exercises without weight (e.g. pull-ups) are compared by reps and sets instead of volume.
- **Offline support**: After the first load, the app works without an internet connection.
- **Light and dark mode**: Follows your system setting.
## Installation
 
1. Open the app’s URL in Chrome on your Android phone.
2. Tap the menu (⋮) and choose **Install app** (or **Add to Home screen**).
3. The app now appears in your app drawer and opens without the browser bar.
The app must be served over HTTPS for installation and offline support to work.
 
## Data storage
 
- All entries are stored **locally on your device** in the browser’s IndexedDB. Nothing is sent to a server.
- When installed, the app requests persistent storage so Chrome won’t clear the data when space runs low.
- **Uninstalling the app or clearing Chrome’s site data deletes all entries.** Make regular backups.
## Backup and export
 
Found in the app under **Daten & Backup**:
 
| Option | Format | Purpose |
|---|---|---|
| Backup speichern | JSON | Full backup saved to *Downloads*, used for restoring |
| Backup teilen | JSON | Share the backup, e.g. to Google Drive or email |
| Backup wiederherstellen | JSON | Restore a backup (replaces current data) |
| Als Tabelle exportieren | CSV | One row per set for Google Sheets or Excel |
 
The app reminds you when your last backup is older than 14 days.
 
To move to a new phone, install the app there, then use **Backup wiederherstellen** with your latest JSON backup.
 
## Files
 
| File | Description |
|---|---|
| `index.html` | The complete app (HTML, CSS and JavaScript) |
| `sw.js` | Service worker for offline use and caching |
| `manifest.webmanifest` | App name, icons and display settings for installation |
| `icon-192.png`, `icon-512.png` | App icons |
| `icon-maskable-512.png` | Adaptive icon for Android launchers |
| `apple-touch-icon.png` | Icon for iOS home screens |
| `ANLEITUNG.txt` | Short installation guide in German |
 
## Updating
 
After the files are replaced with a new version, the installed app picks up the changes the next time it’s opened with an internet connection. When changing cached files, increase the `CACHE` version in `sw.js` so the update is detected reliably.

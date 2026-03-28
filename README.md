# YouTube's Recycle Bin - KVN AUST

A single-file interactive web tool for [KVN AUST](https://www.youtube.com/@KVNAUST)'s "YouTube's Recycle Bin" video series.

**Live Version**: [falcontechnix.com/KVN_AUST](https://falcontechnix.com/KVN_AUST/kvnaust-recyclebin.html) - always up to date, live Google Doc format sync, and password-backed game history saving.

YouTube hosts over 20 billion videos. 93% have under 1,000 views. 30% have under 100. This tool helps explore that vast, forgotten graveyard of content by generating random search strings based on default device filenames (IMG 3201, DSCF0042, MOV 0001, etc.) that surface zero-view uploads.

## What It Does

1. **Slide-Puzzle Bingo Card** - Generates a randomized bingo card with video categories, revealed as a mosaic slide puzzle that solves itself. 50 unique SVG daub stamps per game.
2. **Format Spinner** - 3D-textured spinning wheel of filename formats pulled from KVN AUST's [Recycle Bin Map](https://docs.google.com/document/d/1mV5PhumaIJ8mtH8XmohqXkk5fjK_HlqcineMccPQm5A/) (loaded live when hosted, cached locally).
3. **Rainbow Number Generator** - Randomly generates the variable portion with a character-by-character rainbow shuffle animation.
4. **Search String** - Produces the final YouTube search query. Click to copy. Re-randomize or save & re-roll without leaving the screen.
5. **Multi-Metric Video Tracking** - Rate videos on Entertainment, Weirdness, Gem Factor, and "I Just Liked It". Track across rounds with persistent history.
6. **Game Summary** - End-of-session recap with YouTube thumbnails, titles, per-metric breakdowns, and averages.

## Features

- **Live Google Doc sync** - When hosted, auto-fetches KVN AUST's [Recycle Bin Map Google Doc](https://docs.google.com/document/d/1mV5PhumaIJ8mtH8XmohqXkk5fjK_HlqcineMccPQm5A/) to pull the latest filename formats discovered by the community. Cached locally and refreshes every 30 minutes. When running offline from a file, 75+ formats are hardcoded in the app.
- **Password-backed game history** - On the hosted version at [falcontechnix.com](https://falcontechnix.com/KVN_AUST/kvnaust-recyclebin.html), returning users can save and load their game history, bingo state, and settings with a simple password. Access your data from any device.
- Bingo categories editable, exportable/importable as JSON, cached in localStorage
- Game > Round history persisted with multi-metric scoring
- Bingo card exportable as SVG with KVN AUST social links
- Mosaic of KVN AUST's profile image visible through bingo cells
- 50 unique SVG daub stamp designs (no repeats per game)
- 3D-textured spinning wheel with embedded audio (tick/retro/casino presets)
- BINGO detection with confetti, screen shake, and random easter egg messages
- Customizable daub colors, opacity, and image settings
- Auto-update checking against this repo
- Works offline from `file://` or live from any web server
- Single monolithic HTML file - no build step, no dependencies, no server required

## Usage

### Online (recommended)
Visit [falcontechnix.com/KVN_AUST](https://falcontechnix.com/KVN_AUST/kvnaust-recyclebin.html) - always up to date, live Google Doc format sync enabled, and password-backed game history saving.

### Offline
Download `kvnaust-recyclebin.html` and open it in any browser. Works on Windows, Mac, and Linux. All core features work offline. The app shows a version badge in the footer and checks for updates when online.

## Live Google Doc Sync

KVN AUST maintains a [Google Doc](https://docs.google.com/document/d/1mV5PhumaIJ8mtH8XmohqXkk5fjK_HlqcineMccPQm5A/) (the "Recycle Bin Map") listing all known default filename formats that surface zero-view YouTube uploads. The community continuously adds new formats to this doc.

When the app is hosted on a web server, it automatically fetches the latest formats from this Google Doc every 30 minutes and caches them locally. New formats appear on the spinner without any code changes. When running offline from a file, the app uses 75+ formats hardcoded in the HTML.

## Credits

- **[KVN AUST](https://www.youtube.com/@KVNAUST)** ([@MingKasterMK](https://x.com/MingKasterMK)) - Creator of YouTube's Recycle Bin concept and the Maps
- **Justin / [BASH & BRASS](https://www.youtube.com/@BASHnBRASS) / [FalconTechnix](https://www.falcontechnix.com)** - Tool development
- All contributors listed in the [Google Doc](https://docs.google.com/document/d/1mV5PhumaIJ8mtH8XmohqXkk5fjK_HlqcineMccPQm5A/) who helped discover filename formats

## License

GPL-3.0. See [LICENSE](LICENSE).

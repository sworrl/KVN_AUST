# YouTube's Recycle Bin - KVN AUST

A single-file interactive web tool for [KVN AUST](https://www.youtube.com/@KVNAUST)'s "YouTube's Recycle Bin" video series.

**Live Version**: [falcontechnix.com/KVN_AUST](https://falcontechnix.com/KVN_AUST/kvnaust-recyclebin.html)

YouTube hosts over 20 billion videos. 93% have under 1,000 views. 30% have under 100. This tool helps explore that vast, forgotten graveyard of content by generating random search strings based on default device filenames (IMG 3201, DSCF0042, MOV 0001, etc.) that surface zero-view uploads.

## What It Does

1. **Slide-Puzzle Bingo Card** - Generates a randomized bingo card with video categories, revealed as a mosaic slide puzzle that solves itself. 50 unique SVG daub stamps per game.
2. **Format Spinner** - 3D-textured spinning wheel of filename formats pulled from KVN AUST's [Recycle Bin Map](https://docs.google.com/document/d/1mV5PhumaIJ8mtH8XmohqXkk5fjK_HlqcineMccPQm5A/) (loaded live, cached locally).
3. **Rainbow Number Generator** - Randomly generates the variable portion with a character-by-character rainbow shuffle animation.
4. **Search String** - Produces the final YouTube search query. Click to copy. Re-randomize or save & re-roll without leaving the screen.
5. **Multi-Metric Video Tracking** - Rate videos on Entertainment, Weirdness, Gem Factor, and "I Just Liked It". Track across rounds with persistent history.
6. **Game Summary** - End-of-session recap with YouTube thumbnails, titles, per-metric breakdowns, and averages.

## Features

- Formats auto-fetched from the Google Doc and cached locally (refreshes every 30 min when hosted)
- Bingo categories editable, exportable/importable as JSON, cached in localStorage
- Game > Round history persisted in localStorage with multi-metric scoring
- Bingo card exportable as SVG with KVN AUST social links
- Mosaic of KVN AUST's profile image visible through bingo cells
- 50 unique SVG daub stamp designs (no repeats per game)
- 3D-textured spinning wheel with embedded audio (tick/retro/casino presets)
- BINGO detection with confetti, screen shake, and random easter egg messages
- Customizable daub colors, opacity, and image settings
- Auto-update checking against this repo
- Works offline from `file://` or live from any web server
- Single HTML file - no build step, no dependencies, no server required

## Usage

### Online (recommended)
Visit [falcontechnix.com/KVN_AUST](https://falcontechnix.com/KVN_AUST/kvnaust-recyclebin.html) - always up to date, live doc sync enabled.

### Offline
Download `kvnaust-recyclebin.html` and open it in any browser. Works on Windows, Mac, and Linux. The app checks for updates and shows a version badge in the footer.

## File Structure

```
kvnaust-recyclebin.html  - The entire app (single file)
version.json             - Version info for update checking
img/                     - Image assets (FT logos, favicon)
LICENSE                  - GPL-3.0
README.md                - This file
```

## Version Checking

The app embeds a version number. When hosted, it checks `version.json` in this repo:
- **Live (falcontechnix.com)**: Auto-checks and can auto-reload when updates are available
- **Offline (file://)**: Shows current version with a note to check the live URL
- **Bump version**: Update `APP_VERSION` in the HTML and `version` in `version.json`

## Credits

- **[KVN AUST](https://www.youtube.com/@KVNAUST)** ([@MingKasterMK](https://x.com/MingKasterMK)) - Creator of YouTube's Recycle Bin concept and the Maps
- **Justin / [BASH & BRASS](https://www.youtube.com/@BASHnBRASS) / [FalconTechnix](https://www.falcontechnix.com)** - Tool development
- All contributors listed in the [Google Doc](https://docs.google.com/document/d/1mV5PhumaIJ8mtH8XmohqXkk5fjK_HlqcineMccPQm5A/) who helped discover filename formats

## License

GPL-3.0. See [LICENSE](LICENSE).

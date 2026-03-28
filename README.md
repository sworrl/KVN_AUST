<h1 align="center">
  <br>
  YouTube's Recycle Bin
  <br>
  <sub>Interactive Game Tool for KVN AUST</sub>
  <br>
</h1>

<p align="center">
  <a href="https://falcontechnix.com/KVN_AUST/kvnaust-recyclebin.html"><img src="https://img.shields.io/badge/PLAY_NOW-falcontechnix.com-e74c3c?style=for-the-badge" alt="Play Now"></a>
</p>

<p align="center">
  <a href="https://www.youtube.com/@KVNAUST"><img src="https://img.shields.io/badge/YouTube-@KVNAUST-red?style=flat-square&logo=youtube" alt="YouTube"></a>
  <a href="https://x.com/MingKasterMK"><img src="https://img.shields.io/badge/X-@MingKasterMK-black?style=flat-square&logo=x" alt="X"></a>
  <a href="FORMAT-MAP.md"><img src="https://img.shields.io/badge/FORMAT_MAP-View_All_Formats-2ecc71?style=flat-square" alt="Format Map"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-GPL_3.0-blue?style=flat-square" alt="GPL-3.0"></a>
</p>

---

YouTube hosts over **20 billion videos**. **93%** have under 1,000 views. **30%** have under 100. This tool helps explore that vast, forgotten graveyard of content by generating random search strings based on default device filenames that surface zero-view uploads.

> **[The Complete Format Map](FORMAT-MAP.md)** - All filename patterns, sources, ranges, and community credits in one place.

---

## What It Does

| Step | Feature | Description |
|:----:|:--------|:------------|
| 1 | **Slide-Puzzle Bingo** | Randomized bingo card with 101 video categories. Revealed as a mosaic slide puzzle. 50 unique SVG daub stamps per game. |
| 2 | **Format Spinner** | 3D-textured wheel with filename formats from the [Recycle Bin Map](FORMAT-MAP.md). No-repeat by default. Red dots mark used formats. |
| 3 | **Rainbow Number Gen** | Character-by-character rainbow shuffle animation generates the search variable. |
| 4 | **Search & Rate** | Copy, open in YouTube, or re-randomize. Rate videos on 4 metrics. Save & re-roll without leaving the screen. |
| 5 | **Game Summary** | End-of-session recap with thumbnails, per-metric breakdowns, averages. Export as SVG. |

---

## Features

<table>
<tr><td>

**Core**
- Single monolithic HTML file
- Works offline from `file://` or any web server
- No build step, no dependencies, no server required
- Auto-update checking against this repo
- Embedded Web Audio (tick/retro/casino presets)

</td><td>

**Online (Hosted)**
- Live [Google Doc](https://docs.google.com/document/d/1mV5PhumaIJ8mtH8XmohqXkk5fjK_HlqcineMccPQm5A/) format sync (every 30 min)
- GitHub [Format Map](FORMAT-MAP.md) as secondary source
- Password-backed game history saving
- Always up to date

</td></tr>
<tr><td>

**Bingo**
- 101 categories (KVN originals + community)
- Mosaic of KVN AUST's face through cells
- Slide-puzzle reveal animation
- BINGO detection with confetti & screen shake
- Customizable daub colors & 50 unique SVG stamps
- Export as SVG with social links

</td><td>

**Tracking & Scoring**
- 4 rating metrics: Entertainment, Weirdness, Gem Factor, "I Just Liked It"
- Game > Round history in localStorage
- Browsed/clicked/rated video tracking
- Per-game and all-time averages
- Export game summary as SVG

</td></tr>
</table>

---

## Usage

### Online (Recommended)

> **[Play at falcontechnix.com/KVN_AUST](https://falcontechnix.com/KVN_AUST/kvnaust-recyclebin.html)** - always up to date, live Google Doc format sync, password-backed game history.

### Offline

Download `kvnaust-recyclebin.html` and `bingo-categories.json`, place in the same folder, open in any browser. Works on **Windows**, **Mac**, and **Linux**.

---

## The Format Map

> **[VIEW THE COMPLETE FORMAT MAP](FORMAT-MAP.md)**

The community-maintained list of every known default filename keyphrase that accesses YouTube's video graveyard. All 3 maps, all ranges, all sources, all contributor credits with YouTube links.

---

## Bingo Categories

`bingo-categories.json` contains 101 categories as a flat list. Compiled from KVN AUST's original bingo cards and community fan variants.

- **Hosted**: app fetches the JSON at load time
- **Offline**: place the JSON next to the HTML (embedded fallback if missing)
- **Editable**: via Setup Bingo panel or directly in the JSON file

---

## Contributing

1. **New formats**: Add to [FORMAT-MAP.md](FORMAT-MAP.md) via PR
2. **New bingo categories**: Add to `bingo-categories.json` via PR
3. **Code changes**: Edit `kvnaust-recyclebin.html` and bump the version:

```html
<script type="application/json" id="app-version-data">
{
  "version": "1.7.1",    <-- bump this
  "build": "2026-03-28",  <-- update date
  ...
}
</script>
```

---

## Credits

- **[KVN AUST](https://www.youtube.com/@KVNAUST)** ([@MingKasterMK](https://x.com/MingKasterMK)) - Creator of YouTube's Recycle Bin & the Maps
- **Justin** ([@Chegnus](https://x.com/Chegnus)) / [BASH & BRASS](https://www.youtube.com/@BASHnBRASS) / [FalconTechnix](https://www.falcontechnix.com) - Tool Development
- **[70+ community contributors](FORMAT-MAP.md#contributors)** - Format discovery

---

<p align="center">
  <sub>GPL-3.0 | <a href="https://github.com/sworrl/KVN_AUST">GitHub</a> | <a href="https://falcontechnix.com/KVN_AUST/">Live App</a></sub>
</p>

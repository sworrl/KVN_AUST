# Changelog

All notable changes to YouTube's Recycle Bin — KVN AUST Game Tool.

---

## [4.0.3] - 2026-04-20

### Fixed
- **Format cache nuclear bust (v5)**: renamed both cache key (`kvn_fmt_v5`) and timestamp key (`kvn_fmt_ts_v5`) so no stale data from v2/v3/v4 can prevent the full 177-format fetch. Threshold raised to 100 (was 20) to force re-fetch until all formats are cached.
- **Nautical sound persistence**: `'nautical'` can no longer persist to localStorage. On load, stale `'nautical'` values are detected and removed. Deep Dive sets sound in-memory only.
- **Invidious instances**: replaced 4 dead instances with `iv.melmac.space` (confirmed working). YouTube oEmbed added as fallback for video existence check.

### Added
- **Auto-fetch video metadata**: pasting a YouTube URL auto-fills date posted, views when found (with today's date+time), and channel video count via Invidious API
- **Anchor drop screen wipe**: toggling Deep Dive plays a full-screen transition — anchor icon falls from top, ocean background slides down, theme switches at midpoint. Includes chain rattle + descending tone + splash sound. Reverse wipe on toggle off.

---

## [4.0.0] - 2026-04-20

### Fixed
- **Format cache bug**: date-based and static formats were added to `ALL_FORMATS` in memory but never pushed to the `fetched[]` array that gets saved to localStorage. On reload without network, only 62-78 numbered formats survived. Now all 177 formats are cached and available offline.
- Cache key bumped to v4 to invalidate stale caches

### Added
- **Community Finds API**: live leaderboard from `finds.php` with 14+ seeded discoveries. Clickable detail overlays with thumbnails, rarity badges, channel info, and attribution. Plotted on the Records timeline as community dots.
- **Deep Dive mode**: underwater bubble physics, nautical sonar sounds, whale-call win fanfare, ocean teal theme with 30+ CSS overrides, `Before:2010` search filter for targeting VERY RARE and older videos
- **Video metadata fields**: date posted, views when found, channel video count — saved to history, SVG cards, and Discord copy
- **Copy for Discord**: formatted markdown message with ✮ metadata, star ratings, and @KVNAUST branding
- **Hosted vs Standalone comparison table** and Finds API documentation in README

---

## [3.4.0] - 2026-04-20

### Added
- **Deep Dive mode**: toggle on the wheel screen activates a teal/ocean color theme, auto-selects old-video formats (Ancient YouTube, early date formats, classic numbered formats), and appends `Before:2012` to all YouTube searches and copies. Deep ocean wheel colors, pulsing "DEEP DIVE" badge in header.
- Semantic `<section aria-labelledby>` wrappers on Results, Format Browser, and Game History panels for proper heading hierarchy restart

### Changed
- Panels promoted from `<div>` to `<section>` with `aria-label`/`aria-labelledby`
- Panel headings promoted to `<h2>` (were `<h3>` skipping from `<h1>`)
- Log heading promoted to `<h3>` (was `<h4>` skipping from `<h2>`)

---

## [3.3.0] - 2026-04-20

### Added
- **Video metadata fields**: date posted, views when found, channel video count — captured on the result screen, saved to history, included in SVG share cards and Discord copy
- **Copy for Discord**: purple button generates a formatted markdown message with ✮ metadata, star ratings, and @KVNAUST branding — ready to paste in any Discord channel
- **177 format parser**: static keyphrases, file extensions, and Ancient YouTube entries now load from FORMAT-MAP.md as playable spinner formats (was 62, now 177)

### Changed
- Share card SVG dynamically resizes to fit metadata fields
- Game history shows date posted, views, and channel video count per round

### Fixed
- Heading hierarchy: single `<h1>`, BINGO demoted to `<h2>`
- Lighthouse accessibility: alt attrs, aria-labels, font preconnect, image dimensions
- GitHub Action: fixed detached HEAD checkout

---

## [3.1.0] - 2026-04-19

### Added
- **Share Card**: SVG export button on result screen generates a branded card with search string, format, star ratings, YouTube link, and @KVNAUST/@MingKasterMK social links
- **Stats Dashboard**: header button opens a modal with total games/rounds, per-metric averages, most-used format, unique format count, and best-rated video from all game history
- **Keyboard Shortcuts Help**: `?` button in header opens a modal listing all shortcuts (Ctrl+Enter, Space, R, B, arrows, Escape)
- **Dramatic BINGO fanfare**: 7-note ascending C major scale (C5→C7) with crescendo, separate from the standard 4-note win sound

### Changed
- Win sound upgraded from basic sine wave to triumphant triangle-wave fanfare (C5-E5-G5-C6)

---

## [3.0.0] - 2026-04-19

### Added
- **Searchable format browser**: search bar in the format panel filters formats in real-time, shows type badges (numbered/date/static/special) and ranges per format, displays count of selected/total/visible
- **Community leaderboard**: Records timeline has My Finds / Community tabs. Community tab fetches shared records from falcontechnix.com with medal rankings. Falls back gracefully when offline or on file://
- **PWA manifest**: `manifest.json` allows installing the app as a standalone app on phones and desktops with KVN AUST's avatar as the icon
- **GitHub Actions CI**: auto-counts formats in FORMAT-MAP.md on every push and updates badge numbers in both README and FORMAT-MAP

---

## [2.6.0] - 2026-04-19

### Fixed
- **Spinner accuracy**: format is now read from the pointer position AFTER the wheel stops — what you see is what you get
- **esc() missing quote escaping**: bingo categories with `"` in the name no longer break the setup panel
- **R key on result screen**: no longer destroys the game without warning (only works on summary screen now)
- **Number generator keyboard spam**: space/enter during rainbow animation no longer starts overlapping animations
- **Free space clickable during puzzle**: invisible free space can't be clicked before the puzzle solve finishes

### Added
- **Settings persistence**: daub color, opacity, and sound preference now save to localStorage across reloads
- **Records timeline upgrade**: larger modal (960px), 55vh canvas, gradient zone fills, glowing dots with ambient halos, metallic rings, gradient beam lines, pill-backed labels
- **Progressive daub intensity**: stamps glow brighter as you approach BINGO (4 tiers: basic → glow → pulse → rainbow)
- **KVN's Bingo Picks**: red "KVN Picks" button in format panel — 19 formats KVN AUST personally recommends
- **Date year limits**: `VID YYYYMMDD` >2008, `Capture YYYYMMDD` >2008 <2018, `WIN YYYYMMDD` >2013, `WP YYYYMMDD` >2011 <2018

### Changed
- Wheel rendering rewritten to multi-pass (fills → depth overlay → dividers → text) — eliminates artifacting behind labels
- Metallic outer bezel with diagonal gradient, center orb with specular highlight
- Spinner easing: quintic ease-out `(1-p)^5` for smooth deceleration
- Confetti wobbles laterally with 4-keyframe drift + ease-in timing
- Slide puzzle tiles use `ease` instead of `linear`
- Screen exits use accelerating ease-out
- Bingo wave reduced from 3px to 1.5px
- Toast notifications pop with scale bounce
- All buttons have `:active` press states
- Star rating hover preview (all stars light up to hovered position)
- `will-change` hints on screens and puzzle tiles
- Screen shake moved from `<body>` to `.main`
- HiDPI canvas rendering at `devicePixelRatio`
- Slot count locks once the first spin happens (no changing mid-game)

### Removed
- Dead code: `setImgWithFallback()`, `reSpinSameFormat()`
- Debug `console.log` statements

---

## [2.0.0] - 2026-04-17

### Added
- **SEO meta tags**: description, keywords, canonical URL, Open Graph, Twitter Card, JSON-LD structured data
- **GitHub repo topics**: kvn-aust, youtube, recycle-bin, zero-view-videos, format-map, youtube-search, bingo, game-tool
- **Format counter badges**: 192 total across 5 categories shown on README and FORMAT-MAP
- **17 new format leads** credited to @Chegnus: Snapchat-, .MKV, .WEBM, .MTS, .TS, Screencast from, zoom_0, Replay, R001XXXX, VIRB0XXX, STE_XXXX, Screencast YYYY-MM-DD, PANO_YYYYMMDD, vlc-record-YYYY-MM-DD, Qik, Made with One True Media, Jing
- **Oldest Zero-View Record modal**: canvas timeline with rarity zones, date/view/URL tracking, localStorage persistence
- **Screenshots section** in README: 8 screenshots with descriptive alt text

### Changed
- FORMAT-MAP.md restructured: one unified map with era sections (Search Keyphrases, File Extensions, Numbered Formats, Date-Based, Ancient YouTube) instead of Map 1/2/3
- Recently Added section at top of FORMAT-MAP with detailed descriptions for all new formats
- Google Doc fetching replaced with GitHub FORMAT-MAP.md as sole format source
- MD parser updated to handle backtick-wrapped keyphrases
- Cache key busted to invalidate old broken-regex caches
- Format labels preserve spaces (`IMG XXXX` not `IMGXXXX`)
- README SEO-optimized with natural keyword density
- All play links resolve to `/KVN_AUST/` not direct HTML

### Fixed
- Spinner slot count bug: controls now re-show each round, input responds to `oninput`
- Format cache stale guard: re-fetches if fewer than 20 formats loaded
- Contributor example in FORMAT-MAP uses lowercase to avoid being parsed by spinner

---

## [1.8.0] - 2026-03-28

### Changed
- Replaced Google Doc fetching with GitHub FORMAT-MAP.md as sole format source
- Removed all CORS proxy logic (allorigins, corsproxy)
- Formats now sync from GitHub raw (works from both `file://` and hosted)

---

## [1.7.2] - 2026-03-28

### Fixed
- Version check regex self-match: now searches from end of file using `lastIndexOf('app-version-data')` to find the version JSON block, not the regex pattern itself earlier in the file

---

## [1.7.1] - 2026-03-28

### Fixed
- FT footer icons: relative paths with absolute URL fallback for cross-origin loading

---

## [1.7.0] - 2026-03-27

### Added
- Credits modal fetches contributor list from FORMAT-MAP.md on GitHub
- 70+ contributors displayed with unique colors, profile pics, pulse animations
- @Chegnus added to credits

---

## [1.6.0] - 2026-03-26

### Added
- FORMAT-MAP.md: complete format map with all entries from KVN AUST's Google Doc
- Credits modal with contributor list from GitHub
- Removed all base64 image embeds
- Fancy README with shield badges, feature tables

---

## [1.5.2] - 2026-03-25

### Added
- Game summary exports as SVG with video thumbnails, per-metric star ratings, and averages

---

## [1.5.0] - 2026-03-24

### Changed
- Bingo categories restructured to flat list (101 categories)
- Removed per-letter bingo mode
- Added "Potential undiscovered 9/11 video" category

---

## [1.4.4] - 2026-03-23

### Added
- No-repeat spinner with red dots marking used formats
- SVG bingo card export with social links
- Web Audio sound effects (tick, retro, casino presets)
- Audio indicator only shows after first user click

### Fixed
- SVG export corruption: `&middot;` replaced with `&#183;` numeric entity
- Save & re-randomize staying on result screen
- Export game summary button creating new game instead of downloading

---

## [1.3.0] - 2026-03-21

### Added
- Random bingo categories from `bingo-categories.json`
- In-app YouTube search via Invidious API
- Build timestamps in version block

---

## [1.2.0] - 2026-03-20

### Added
- Version checking against GitHub repo
- Mobile layout improvements

### Fixed
- Spin not advancing to format screen after wheel stop

---

## [1.0.0] - 2026-03-19

### Initial Release
- Single monolithic HTML file
- 3D-textured format spinner wheel
- Slide-puzzle bingo card reveal with mosaic
- 50 unique SVG daub stamp generators
- Rainbow character shuffle animation for number generation
- 4-metric video rating (Entertainment, Weirdness, Gem Factor, I Just Liked It)
- Game > Round history in localStorage
- Google Doc format sync (when hosted)
- Works offline from `file://` or any web server

---

<sub>[KVN AUST](https://youtube.com/@KVNAUST) | [Play Now](https://falcontechnix.com/KVN_AUST/) | [GitHub](https://github.com/sworrl/KVN_AUST)</sub>

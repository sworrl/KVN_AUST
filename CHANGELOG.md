<h1 align="center">
  <br>
  YouTube's Recycle Bin
  <br>
  <sub>Changelog</sub>
  <br>
</h1>

<p align="center">
  <a href="https://www.youtube.com/@KVNAUST"><img src="https://img.shields.io/badge/YouTube-KVN_AUST-red?style=for-the-badge&logo=youtube" alt="YouTube"></a>
  <a href="https://x.com/MingKasterMK"><img src="https://img.shields.io/badge/X-@MingKasterMK-black?style=for-the-badge&logo=x" alt="X/Twitter"></a>
  <a href="https://falcontechnix.com/KVN_AUST/"><img src="https://img.shields.io/badge/PLAY_NOW-falcontechnix.com-e74c3c?style=for-the-badge" alt="Play Now"></a>
</p>

---

## [5.3.0] - 2026-04-23

### Added
- **Unified record modals**: all finds (community AND local) open the same premium detail modal with thumbnail, rarity pill badge, color-coded metadata, prominent finder attribution box, and added-at date
- **Share SVG from modal**: generates a branded find card with rarity header, metadata, finder credit, and KVN AUST footer
- **Discord copy from modal**: formatted markdown with rarity emoji, ✮ metadata lines, finder attribution, and app link
- All timeline dots and local record list entries are now clickable (open modals)

---

## [5.2.0] - 2026-04-23

### Changed
- **Deep Dive pointer**: CSS override uses `var(--pointer-glow)` for stroke — segment colors flash correctly through deep ocean palette during spin
- **Anchor wipe major upgrade**: water caustics texture (SVG fractalNoise with screen blend), water surface line, 8 splash droplets with gravity arc, 25 rising particles, 3 sonar rings, taller splash pad, "SEARCHING THE ABYSS" subtitle

---

## [5.1.0] - 2026-04-23

### Added
- **Holiday easter eggs**: automatic detection for 10 holidays — New Year, Valentine's, St. Patrick's, April Fools, 4th of July, KVN AUST's Birthday (Oct 18), Halloween, Christmas Eve, Christmas, New Year's Eve
- Each holiday: themed tagline, toast greeting, holiday-colored confetti, custom free space phrases (Halloween/Christmas)
- **KVN AUST Day** (Oct 18): auto-confetti + birthday greeting
- **April Fools**: reversed bingo letters
- **Poppable bubbles**: click any Deep Dive bubble to burst it — spawns 6-16 HSL particles with gravity + pop sound (high-pass noise + sine ping)
- **Bubble visual upgrade**: per-bubble HSL hue, outer ring rainbow refraction, prismatic refraction arc on large bubbles, pop particles inherit parent hue
- **Deep Dive background**: swaps to underwater dot texture pattern

### Changed
- Visual sweep: 17 elements upgraded with premium treatment — bingo flash, bingo win, bingo cells, confetti, error panels, spin label, format banner, click hint, range display, wheel controls, summary screen/title/cards, plus transitions on all interactive elements
- Confetti uses holiday colors when a holiday is active

---

## [5.0.0] - 2026-04-23

### Changed — Full Visual Overhaul
- **Header**: deeper gradient, bottom border glow `rgba(231,76,60,.12)`, 2px animated accent line with breathing keyframes, backdrop blur on buttons
- **Start screen**: animated gradient title (white→red→gold shifting), stronger avatar glow, tagline with letter-spacing, buttons with inset highlights and bottom shadow
- **Bingo card**: cells have inner shadow for depth + bottom highlight, hover glow, grid gets dark background pad, mosaic desaturated slightly
- **Number screen**: gradient number box, multi-layer shadow, rolling digits with blue text-glow, GENERATE button with gloss + inset highlight + border
- **Result screen**: pill with inset bottom shadow, stronger hover glow, lit stars have text-shadow glow, inputs recessed with inset shadow
- **All modals**: gradient backgrounds, inset edge highlights, stronger overlay blur, improved dividers
- **Format/History panels**: gradient backgrounds, inner edge lines, improved search inputs, hover depth on items
- **Footer**: stronger gradient, top border line
- **Custom scrollbars**: 8px webkit scrollbars with dark track, semi-transparent thumb, hover state
- **Selection colors**: `::selection` themed red (default) / teal (Deep Dive)
- **Nav arrows**: deeper shadows, primary buttons get accent glow
- **Toasts**: subtle border added
- **Spin button**: inset white highlight
- **Summary cards**: shadow + hover border
- **Bingo setup**: matches format panel treatment

---

## [4.7.0] - 2026-04-23

### Fixed
- **All 192 FORMAT-MAP entries now parse** — zero skips, zero hardcoded fallbacks
- **4XXX / Trim 4XXX**: properly detected as hex format (generates AAA-FFF range)
- **"HHMMSS"**: generates valid time-of-day strings (000000-235959)
- **Video0XX, Vid0XX, MOV000XX, muuvee00XX, 0_VIDEO_0XX**: small-range Ancient YouTube formats now parse from parenthetical `(00-10)` notation
- **XXXX.MP4, 0XXXX.MTS, MOVXXXXA**: formats with X at start or suffixes after X now parse correctly
- **GX01XXXX, YDXJXXXX**: formats with X in the prefix (like GoPro `GX01`) now parse — regex uses lookahead to distinguish prefix-X from variable-X
- **Date formats in Search Keyphrases section**: now caught without requiring `>YYYY` column
- **Spacebar ghost spin**: spacebar on non-number screens no longer activates focused buttons (was triggering spin sounds in background)
- **OG/Twitter meta image**: fixed broken `screenshots/spinner.png` reference to `screenshots/05-spinner.png`

### Changed
- **All hardcoded formats removed** — `ALL_FORMATS=[]`, everything comes from FORMAT-MAP.md fetch + cache
- Numbered regex: `(?:[^X]|X(?!X))*` prefix allows X in format names while correctly identifying the trailing variable X run
- Cache key bumped to v6

### Added
- `sp:'time'` format type — generates HHMMSS with valid hour/minute/second ranges
- Small-range parser for Ancient YouTube formats in `(XX-YY)` parenthetical notation

---

## [4.6.0] - 2026-04-23

### Added
- **Visual overhaul**: bespoke button colors per action (copy/youtube/save/skip/end/share/discord/records), background diamond texture with slow drift animation, gloss overlays on all buttons
- **"Add to Records" button** on result screen — grabs current video data and opens Records with highlighted entry
- **"Submit a Find" button** on start screen — opens Records modal directly, no game required

### Changed
- Buttons use named CSS classes instead of inline styles
- Result pill has gradient background with inset highlight
- Records canvas delayed 350ms after modal open (fixes smaller-than-viewport on first render)
- Community leaderboard entries show finder name prominently (white, bold, rarity text-shadow) with discovered_at date

---

## [4.5.0] - 2026-04-20

### Changed
- **Records form redesigned**: YouTube link is now required (not optional). Paste a URL and metadata auto-fetches via videometa.php → Invidious → CORS proxy chain
- **Duplicate prevention**: can't add the same video ID twice to your records
- **Add button**: disabled until valid metadata is populated

---

## [4.4.0] - 2026-04-20

### Added
- **Zero-view emphasis on timeline**: zero-view finds render large/bright/glowing, non-zero fade and shrink proportionally
- **Filter toggle**: "All Finds" / "Zero Views Only" buttons above the timeline
- **Discord Integration Guide**: [DISCORD_INTEGRATION.md](DISCORD_INTEGRATION.md) with Node.js, Python, and bash bot code
- **Solved Mysteries**: moved to own file [SOLVED_MYSTERIES.md](SOLVED_MYSTERIES.md)
- **11 new screenshots** in user flow order (landing through find detail)
- **README leaderboard**: auto-updates every 3 hours via GitHub Actions with top 10 finds
- **Hash routing**: `#records`, `#stats`, `#shortcuts`, `#credits` open modals from URL
- **Record Holder banner**: scored by oldest date + lowest views + lowest channel videos
- **Back to Home / New Game** split buttons on game summary screen

### Changed
- End game sets `gameActive=false` and returns to landing after summary
- Standard centered headers on all markdown files (CHANGELOG, DISCORD_INTEGRATION, SOLVED_MYSTERIES)
- Removed "Note from KVN AUST: WORKING ON A FIX" from FORMAT-MAP
- Leaderboard submission note: submit via hosted tool or Records timeline, no full game required

---

## [4.3.0] - 2026-04-20

### Added
- **Hover tooltips on timeline dots**: mouseover shows rarity, date, views, source, finder
- **Click detail modal**: full-screen overlay with thumbnail, all metadata, "Watch on YouTube" button (window.open, works correctly)
- **Record Holder banner**: trophy banner at top of Records modal showing the winning find. Scoring: oldest date (heaviest weight) + lowest view count + lowest channel videos
- **Hash routing**: `#records`, `#stats`, `#shortcuts`, `#credits` open modals directly from URL
- **GitHub README leaderboard**: auto-updated every 6 hours via GitHub Action fetching from `finds.php` API
- **Direct links table** in README for all hash routes

### Fixed
- Zone labels no longer overlap — font scales with zone width, hides when too narrow
- Detail modal now uses `window.open()` for YouTube links instead of `<a>` inside pointer-events:none container
- Source attribution symbols (D/G/GD/M/K) rendered inside community dots

---

## [4.1.0] - 2026-04-20

### Fixed
- **Video metadata fetch**: CORS was blocking all Invidious requests from browser. Added `allorigins.win` CORS proxy as fallback. Fetch chain: hosted proxy → direct Invidious → CORS-proxied Invidious. Uses `AbortController` instead of `AbortSignal.timeout` for wider browser support.

### Changed
- **Wheel pointer**: upgraded from flat triangle to 3D gradient pointer with metallic gradient fill, specular highlight, idle bob animation, and segment-color glow pulse during spin. Locks to landed segment color after spin.
- **Bubble z-index**: lowered from 5 to 1 — bubbles now properly render behind all game UI, spinner, and buttons
- **Anchor wipe**: added teal splash radial gradient at bottom when anchor lands, reverse splash on exit
- **README**: updated YouTube stats — estimated 6 billion videos with <10 views, 1 billion+ with exactly zero views

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

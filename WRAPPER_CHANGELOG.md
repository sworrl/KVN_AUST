<h1 align="center">
  <br>
  YouTube's Recycle Bin
  <br>
  <sub>Hosted Wrapper Changelog</sub>
  <br>
</h1>

<p align="center">
  <a href="https://www.youtube.com/@KVNAUST"><img src="https://img.shields.io/badge/YouTube-KVN_AUST-red?style=for-the-badge&logo=youtube" alt="YouTube"></a>
  <a href="https://x.com/MingKasterMK"><img src="https://img.shields.io/badge/X-@MingKasterMK-black?style=for-the-badge&logo=x" alt="X/Twitter"></a>
  <a href="https://falcontechnix.com/KVN_AUST/"><img src="https://img.shields.io/badge/PLAY_NOW-falcontechnix.com-e74c3c?style=for-the-badge" alt="Play Now"></a>
</p>

---

The hosted version at [falcontechnix.com/KVN_AUST](https://falcontechnix.com/KVN_AUST/) wraps the open-source game HTML from this repo with additional server-side features. This changelog tracks what the wrapper adds on top of the standalone game.

> The wrapper source is not open-source. This changelog documents the **public-facing features and API surface** only.

---

## 1.12.0 — "Network Effects" (2026-04-27)

### New Features
- **Co-watching** — realtime synchronized video playback on every discovery page. SSE-driven play/pause/seek sync, presence pills, in-band chat.
- **Find verification** — server validates videos exist and view count is plausible at submission time. Verified finds get a badge.
- **Video frame extraction** — server-side frame capture from any YouTube video at any timestamp.
- **Web Push notifications** — subscribe to record-broken, season events, verified finds, and broadcasts.
- **Daily challenges** — format-of-the-day with streak tracking and public leaderboard.
- **KVN AUST channel scraper** — hourly auto-import of @KVNAUST's uploads as official verified finds.
- **Pattern recommendations** — "users who found X also found Y" co-occurrence analysis with personalized lead suggestions.
- **Date heatmap** — year × month matrix of finds by video upload date.
- **Per-user Atom feeds** — personal RSS feed of a user's finds.
- **13 wrapper-exclusive badges** — achievements that require server verification: globetrotter, speedrunner, first responder, verified milestones, streak milestones, co-watch host, party starter, tip of the iceberg, era-spanning.
- **Random discovery** — redirect to a random find, scoped by user optionally.
- **Personal webhooks** — register Discord/Slack/generic webhook URLs for notifications on new finds, verifications, and streaks.
- **Embed widget** — iframe-ready latest-finds widget for embedding on any third-party page.
- **JavaScript SDK** — `sdk.js` (3 KB) with typed wrappers for every public endpoint.
- **Anti-clone redirect** — clones serving the raw HTML get a banner directing users to the canonical hosted version.

---

## 1.11.0 — "Security Sweep" (2026-04-27)

### Security
- Enhanced encryption for stored credentials
- Login protection with timing-safe comparison and exponential backoff
- CORS restricted to FalconTechnix domains only
- Service worker never caches authenticated endpoints
- TLS 1.2/1.3 enforced
- Per-request token rotation on admin endpoints

---

## 1.10.0 — "Service Worker" (2026-04-27)

### New Features
- **Layered service worker** — 4 named caches (static, html, runtime, api) with strategy routing
- Network-first for API calls, stale-while-revalidate for HTML, cache-first for static assets
- Offline fallback page
- Background sync replay for failed requests
- Push notification handler

---

## 1.9.0 (2026-04-27)

### New Features
- **Player profiles** — XP, levels, 15 server-side badges, lifetime rank, streaks
- **Profile cards** — 1200×630 SVG share cards
- **Player comparison** — side-by-side stats
- **Seasons** — 90-day competitive windows with season-filtered leaderboards
- **Multiplayer** — SSE-based co-op rooms with presence and chat
- **Discovery pages** — permanent shareable URL per find with OG cards
- **Atom feed** + **iCalendar season feed**
- **OpenAPI 3.0 spec** for the full API surface
- **Dynamic sitemap** including all discoveries and profiles
- **Display names** — public alias separate from login
- **Records bridge** — in-game records auto-submit to the public leaderboard
- **Live status endpoint** — online users, find counts, active season

---

## 1.6.0 and earlier

### Core Features
- Cloud save (localStorage sync across devices)
- Welcome-back modal with in-progress game detection
- Version badge with sync countdown
- Bingo card capture and deduplication
- Credits enhancement (X/Twitter avatar resolution)
- Format count badge in header
- Game count in History button
- Auto-updates within 5 minutes of upstream push
- SEO layer (JSON-LD, meta tags, 110+ URL aliases, IndexNow)

---

<p align="center">
  <sub><a href="https://github.com/sworrl/KVN_AUST">GitHub</a> | <a href="https://falcontechnix.com/KVN_AUST/">Play Now</a> | <a href="FORMAT-MAP.md">Format Map</a> | <a href="CHANGELOG.md">Game Changelog</a></sub>
</p>

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
  <a href="https://kvnaust.falcontechnix.com/"><img src="https://img.shields.io/badge/PLAY_NOW-kvnaust.falcontechnix.com-e74c3c?style=for-the-badge" alt="Play Now"></a>
</p>

---

## [7.0.12] — 2026-06-02 — Leaderboard: list is now the default view with full verbose cards

### ✨ Changed / Fixed
- **Community list is now the default view** — the records modal opens directly to the full verbose list instead of hiding it behind a toggle. The list loads community data immediately on open (no tab-click required). "⬜ Timeline" button toggles to the canvas graphic; "☰ List" toggles back.
- **Verbose card layout** — each list entry now shows: thumbnail (linked to YouTube), full date (weekday + month + year), rarity badge, zero-views badge if applicable, views when found, search lead, channel name + video count, subscriber count, date added to leaderboard, source/server, video title, and finder name. Watch / SVG / Discord / ★ Both buttons on every card.
- **"Submit a Find" renamed** to "🏆 Community Leaderboard" on the start screen — the old label implied it was submission-only when it actually opens the full leaderboard.
- **Modal title** changed to "Community Leaderboard" with subtitle clarifying it shows all community finds.
- **Timeline controls** (All Finds / Zero Views / Reset Zoom / scroll hint) are hidden by default and only appear when the Timeline view is active.

---

## [7.0.11] — 2026-06-02 — Records: share buttons on strip, list rows, and record holder

### ✨ Added
- **Inline share buttons on every list-view row** — each row in the ☰ List view has three mini-buttons: `SVG` (exports a shareable card), `D` (copies Discord-formatted text), `★` (does both). Buttons stop propagation so the find-detail modal doesn't open unless you click the row itself.
- **Share buttons on the recently-added strip cards** — each "🆕 New" strip card now shows the same SVG / D / ★ trio beneath the date/finder line.
- **Share buttons next to the Record Holder line** — in the timeline/graphic view, the record holder summary bar (🏆 Record Holder: …) now shows SVG / D / ★ inline, targeting the current top-ranked community find. Appears only when community data is loaded.

---

## [7.0.10] — 2026-06-02 — Records: recently-added strip + list/timeline toggle

### ✨ Added
- **"🆕 New" strip above the timeline** — when community finds load, the 10 most recently submitted entries (sorted by `discovered_at` desc) appear as a compact horizontal strip of clickable cards above the timeline graphic. Each card shows the added date, posted date, and finder name in the entry's rarity colour. Clicking opens the full find-detail modal.
- **List ↔ Timeline toggle button** — a "☰ List" button in the records controls row swaps the canvas timeline for a full card-list view of all community finds. Each row shows rank/medal, date (in rarity colour), view count, search lead, channel name, and finder. Clicking any row opens the detail modal. Toggle back with "⬜ Timeline". The All Finds / Zero Views / Reset Zoom buttons hide automatically while in list mode and restore on toggle back.

---

## [7.0.9] — 2026-05-25 — Setup Bingo button fix + format cache bust

### 🐛 Fixed
- **"Setup Bingo" header button rendered as cramped two-line text** inside the 30×30 `.hdr-btn-icon` container, with the SVG bingo-card icon missing. Root cause: `updateBingoBtn()` called `btn.textContent = 'Setup Bingo'` on every state change, which destroyed the inline SVG and replaced the entire button body with raw text that then wrapped to two lines because the icon-button class is sized for a single glyph. Fix: button now carries the existing `is-formats` widen-class (auto-width + 8px padding + 4px icon→text gap, the same pattern the formats counter uses) and an explicit `<span class="lbl">` for the label. `updateBingoBtn()` only swaps the inner `.lbl` text (`"Setup Bingo"` ⇄ `"Bingo"`) plus the `title` / `aria-label` / `.active` class — never the SVG. Idle and active states now render as **icon + label** on one line and the active state lights up via the existing `.active` red gradient instead of a label rewrite.

- **Format counter pill showed only 118 formats** when the live `FORMAT-MAP.md` actually parses to 266. Root cause: stale `localStorage` cache under the `kvn_fmt_v6` key holding a snapshot from an older buggy parser; the in-app guard `cacheSize >= 100 && !isCacheStale()` happily skipped the network refresh, so existing users never saw the corrected parse. Fix: cache key bumped to `kvn_fmt_v7` (and the matching timestamp key to `kvn_fmt_ts_v7`), invalidating every cached snapshot worldwide on next page load. Subsequent fetches now re-parse `FORMAT-MAP.md` from GitHub fresh — and any future parser-shape changes are a one-line key bump away from the same guaranteed cache-flush.

---

## [7.0.8] — 2026-05-06 — Share buttons unclipped + 3D button pass

### 🐛 Fixed
- **"Watch on YouTube" / "Share SVG" / "Discord" buttons in the find-detail modal were clipped** to "Wa" / "Sh" / "Di". Inline `style="flex:0"` on the buttons combined with the `.vt-btn` class's `min-width:0` expanded to `flex:0 1 0%` (don't grow, *do* shrink, basis 0%) — flexbox happily collapsed each button to fit only the first character that didn't overflow. Inline style is now `flex:0 0 auto;min-width:auto`, so they render their full label.

### ✨ 3D button pass
Every interactive button in the UI got the same lifted-and-pressable treatment — the kind that responds when you touch it.
- **`.vt-btn`** (share/save/skip/end/etc. — the wide pills) — top inner highlight, bottom inner shadow, hard offset shadow underneath (the "lift"), soft ambient bloom, glossy top-half overlay. Hover lifts it 1px and brightens it. Active presses it down 2px and dulls it.
- **`.hdr-btn-icon`** (the small icon row in the page header) — same pattern at compact scale. Active state (e.g. open Format Browser) gets a colour-tinted hard shadow.
- **`.wheel-mode-btns button`** (game-mode chips next to the wheel) — depth + lift + press, with the active variant getting an accent-coloured deep shadow.
- **`.wheel-count-wrap button`** (count adjusters) — same depth pattern, accent-coloured.

Press-and-release feels physical now instead of a 2D opacity flicker. No layout changes — sizes/spacing identical.

---

## [7.0.7] — 2026-05-06 — Records: "Added Invalid Date" fixed

The find detail modal showed `Added Invalid Date` because the API returns `discovered_at` as a string of Unix-seconds (e.g. `"1777816805"`), and `new Date("1777816805")` is `Invalid Date` (JS only auto-detects ISO-ish strings, not numeric epoch strings). Patched both render sites (records list row + find detail modal) to coerce the value: parse to Number, treat values < `1e11` as seconds and `*1000`, fall back to passing the original string for ISO inputs, and skip rendering if the result is still NaN. Existing reseeded entries with epoch-seconds discovered_at now render correctly.

---

## [7.0.6] — 2026-05-03 — Bingo icon, take three

The v7.0.5 bingo SVG used quadratic-curve `Q` paths to draw the letter "B"; in some browsers / size combos the path collapsed and the button fell back to rendering the `aria-label` text ("Setup Bingo"). Replaced with a path-free design: outer ball, inner letter window, centre dot, and four small dimples at NW/NE/SW/SE — pure circles only, no `<path>`, no per-element stroke override. Reads as a bingo ball at every size.

---

## [7.0.5] — 2026-05-03 — Bingo icon + repo hygiene pass

- **Bingo button finally reads as bingo.** Replaced the 3×3 mini-card SVG (which most testers still read as a generic grid) with a classic **bingo ball** — outer circle, inner letter window, and a stroked **B** in the centre. Universally recognised lottery/bingo iconography at any size.
- **CHANGELOG scrubbed.** Removed server-internal references that had crept into earlier 7.0.x entries (filesystem paths, the explicit table list, systemd hardening directive names, the install path of the binary). Entries now describe the symptoms and resolutions in product terms, which is what readers of a public changelog actually need. The proprietary wrapper layer should not be discoverable from this repo's text artefacts.
- **Wrapper modal — license line gets a colour-cycle pulse.** The "© Justin / Falcon Technix — All Rights Reserved" line in the wrapper-changelog modal now flows through a soft rainbow gradient with a slow brightness breath. Honours `prefers-reduced-motion`. *(Wrapper-only visual change; no GPL HTML touched beyond the version bump.)*

---

## [7.0.4] — 2026-05-03 — Changelog modal: actually serve the markdown

The v7.0.3 fix made the parser robust enough to handle the file — but the file was never reaching the parser. Caddy's `handle_path /KVN_AUST/CHANGELOG.md` directive strips the **entire matched prefix** (not just the leading `/KVN_AUST` portion as I'd assumed), which left an empty path. `file_server` then served the directory index — the **938-byte placeholder** `index.html` — with `Content-Type: text/markdown` because the header was already set. Result: the in-app modal received the placeholder HTML, treated it as markdown, the parser found 0 entries (no `## [version]` lines in HTML), and fell through to the `<pre>` raw dump.

Switched to `handle` + `rewrite *  /CHANGELOG.md` (and the same for WRAPPER-CHANGELOG.md) so the request gets internally rerouted to the actual file in the doc root before `file_server` looks it up. All 4 URL variants (`/CHANGELOG.md`, `/KVN_AUST/CHANGELOG.md`, `/WRAPPER-CHANGELOG.md`, `/KVN_AUST/WRAPPER-CHANGELOG.md`) now serve their real bytes (43755 and 8587 on disk, both match served sizes exactly).

*(Caddy-only fix. shim.js parser improvements from v7.0.3 already shipped — they were correct, the upstream just wasn't feeding them real data.)*

---

## [7.0.3] — 2026-05-03 — Changelog modal renders properly

- **In-app version modals were dumping raw markdown.** The `parseChangelog` regex required a literal ASCII hyphen between `## [version]` and the date, but our CHANGELOG entries use ` — ` (em-dash), and Markdown editors silently auto-correct that on save. Result: parser found 0 entries → fallback dumped the raw `.md` text into a `<pre>` block in both the source-changelog modal and the wrapper-changelog modal. Now matches `-`, `–` (en-dash), and `—` (em-dash). Captures any "— Title" suffix as the entry title.
- **`renderMarkdown` rewrite** — was minimum-viable, missing links, blockquotes, fenced code, tables, italic, em-dash horizontal rules, and the dedented "block element inside `<p>`" cleanup. Now handles all of those, plus pulls fenced ` ```code``` ` blocks out before other regex transforms so their content survives intact. Tables render as a real styled `<table>` (collapsed borders, monospace cells), blockquotes get a left-bar treatment, links open in new tabs.
- *(Wrapper-only change — `shim.js` deployed direct to the server. No GPL HTML in this fix beyond the version bump.)*

---

## [7.0.2] — 2026-05-03 — Header polish

- **Icon row stacks instead of pushing the title.** `.header-right` now caps at `max-width:280px` (200px on mobile) — when the 9 icons + sound picker exceed that, they wrap to a second row underneath instead of squeezing the **Sonder** title off-screen.
- **Bingo button gets a real bingo icon.** Was a generic 5×5 grid that read as "spreadsheet". Now a 3×3 card outline with the centre cell visibly daubed (filled circle stroke-removed) — reads as *"a bingo card, with one marked space"* at any size, matching what the panel actually does.
- **Slightly slimmer icons.** 32×32 → 30×30 with 5px gap (was 6px). Saves ~12% horizontal space, fits more on the first row before wrapping.

## [7.0.1] — 2026-05-03 — **Stabilization pass after the Go rewrite**

Catches every loose end the Go cutover surfaced in the first 24 hours of production traffic.

### 🆘 Recovered

- **Records leaderboard reseeded.** The cutover left the public-finds list empty because the on-disk backup script had been pointing at a stale path. All 21 finds from the most recent README leaderboard snapshot in git history (`b7acb25`) were idempotently re-imported. Missing per-find fields will backfill on the next scheduled channel scrape. Reseeded entries are tagged so they remain distinguishable from organic submissions.

### 🐛 Bug fixes

- **Login was broken** (network error). The Go router only matched bare `/sync.php` for cloud-save; the front-end posts to `/KVN_AUST/sync.php` (legacy bookmark prefix). Added the prefixed path variants. Login + cloud save work again.
- **Channel-videos count** returned 502. The previous fix only enriched single-video metadata; the channel handler still relied on Invidious-only and 502'd when all instances were dead. Added `tryScrapeChannel()` that hits `/channel/<id>/about` and pulls `videoCountText`. Verified live: channels return `videoCount` correctly via scrape.
- **In-app changelog modals** ("Couldn't load CHANGELOG.md / WRAPPER-CHANGELOG.md") were 403'd by Caddy's `block_sensitive` (which globs all `.md`). Added explicit `handle_path` blocks BEFORE `block_sensitive` for both files at `/CHANGELOG.md`, `/WRAPPER-CHANGELOG.md`, `/KVN_AUST/CHANGELOG.md`, `/KVN_AUST/WRAPPER-CHANGELOG.md` — all 4 URL variants the shim might fetch. All HTTP 200 now.
- **Embedded `app-version-data` JSON block** wasn't bumped when v7.0.0 was cut, so the version pill kept showing 6.0.0. Bumped to 7.0.0 + added a workflow (below) so it never desyncs from a release tag again.
- **`statusRecorder` middleware** in the Go backend masked `http.Flusher` (and now `http.Hijacker`) — caused `/version-stream.php` SSE to return HTTP 500 every 6 seconds for every open game tab. Fixed by delegating both interfaces to the wrapped writer.
- **YT metadata `published` timestamp** was being missed because YouTube reshuffled the watch-page HTML. Added `datePublished` and `uploadDate` scrape fallbacks alongside the existing `publishDate` regex. Date-posted field now auto-fills on the rating screen.

### 🛡️ Operational

- **Backup cron path corrected.** Was pointing at a legacy location wiped during the Go cutover; now points at the current backup script location. Created the missing backups directory so the next scheduled run produces the first real on-disk SQLite snapshot.
- **`WRAPPER_VERSION` bumped to 7.0.0** to match the Go binary's release line. Was stale at `1.12.0` from the pre-rewrite era.

### 🤖 Auto-bump on release tag

- New workflow [`bump-version.yml`](.github/workflows/bump-version.yml) fires on `release: published`, parses the SemVer tag, updates the embedded `app-version-data` block in `kvnaust-recyclebin.html`, and commits back. Stops the v7.0.0-style mistake where the tag and the embedded block can drift. Pre-release tags (`v7.0.1-rc1`) are skipped so the production app version only follows real releases.
- This release is the workflow's first dogfood run — when v7.0.1 publishes, the auto-bump should land a follow-up commit "Auto-bump app-version-data to 7.0.1" within ~30 seconds.

### 🤝 Wrapper

- Removed the maintainer's last name from the wrapper's version modal copyright notice. The version modal and copyright footer now read "Justin / Falcon Technix" instead of the full name. *(Wrapper is proprietary — change is server-side only, mentioned here for completeness.)*

---

## [7.0.0] — 2026-05-03 — **The Go Rewrite**

> **The single biggest backend change in the project's history.** The hosted community wrapper at `kvnaust.falcontechnix.com` is now a single statically-linked Go binary (~23 MB) replacing the previous PHP layer that powered every dynamic endpoint behind the GPL game tool. Same product, same URLs, same data — completely different engine underneath.

### 🦫 Why we did this

The PHP wrapper served us well from v3 → v6 — fast to iterate, easy to deploy, no build step. By v6.1 it had accumulated **~150 KB across 28 files**, a nontrivial dependency surface (php-fpm, php-curl, php-sqlite3, php-mbstring, php-json, php-xml, OPcache config, FPM pool tuning), and a debugging story that was getting harder to reason about as endpoints multiplied. Specific pains that pushed us over:

- **Cold path latency.** Even with OPcache hot, every request paid a per-request bootstrap (autoloader, security gate include, PDO open, PDO prepare). Profiling showed steady-state requests spending 40-60% of wall-clock time on framework overhead before the handler even ran.
- **Concurrency model.** PHP-FPM workers are process-per-request. Our SSE endpoints (`version-stream.php`, `multiplayer.php` long-polling) tied up a worker for up to 4½ minutes. Under burst load — especially around new release announcements — workers exhausted and queued.
- **Type drift.** PHP's runtime typing meant entire categories of bugs (typo'd field names, off-by-one column indices, nil-vs-empty-string ambiguity) only surfaced in production. Adding strict types everywhere helped but was inconsistent.
- **Deployment surface.** Apache mod_php → PHP-FPM → Caddy reverse proxy → Apache vhost rules → .htaccess → 28 PHP files = a lot of moving parts to keep in sync. A single misconfigured allowlist anywhere was a vuln.
- **No build-time guarantees.** `php -l` only checks syntax. Dead code, broken refactors, missed callers — all silent until exercised.

### ⚡ What Go gave us

- **Single static binary.** ~23 MB, no runtime dependencies, no interpreter, no opcache, no autoloader. Deploys are a single service restart. Rolls back in <2 seconds.
- **Steady-state latency dropped ~10×.** Median p50 for `finds.php` (now an in-binary handler) went from **18ms → 1.6ms**. Cache-warm SQLite queries serve in <1ms because the connection lives for the binary's lifetime instead of being reopened per request.
- **True concurrency.** Goroutines + `context.Context` cancellation. SSE endpoints now hold one goroutine (a few KB of stack) instead of one PHP-FPM worker (12-32 MB resident). The same hardware handles ~30× more concurrent SSE clients.
- **Compile-time guarantees.** `go vet`, `staticcheck`, and `go build` catch nil derefs, unused variables, wrong types, dead code, and mismatched interfaces *before* the binary even gets uploaded. We removed an entire class of "production-only" bugs.
- **Pure-Go SQLite (`modernc.org/sqlite`).** No CGO. The binary compiles with `CGO_ENABLED=0` and runs on any Linux x86_64 with no shared libraries. SQLite WAL mode, prepared statements, and schema migrations all live in code we own.
- **Strict OS-level sandbox at the binary level.** The service runs unprivileged with a tightly restricted syscall set, no home access, isolated temp space, locked-down namespaces and address families, and a small explicit allowlist of writable directories. The blast radius of a hypothetical RCE is dramatically smaller than the previous PHP-FPM surface.
- **One language for everything.** Auth, rate-limit, sqlite, SSE, hCaptcha verification, WebAuthn, ratelimit, video-frame extraction, the Invidious/oEmbed/scrape waterfall — all in `internal/*` Go packages we own. No `composer require`, no transitive dep tree.
- **Observable by default.** Structured `slog.JSON` logging on every request (`{method, path, status, ip, dur_ms}`) flows straight into journald with zero config. No more grep-fu through interleaved Apache + PHP error logs.
- **Safer migrations.** The Go version reads the same SQLite file the PHP version wrote. We did the cutover live with no schema migration, no data loss, no downtime — both versions could run side-by-side reading the same DB during testing.

### 📦 What stayed the same (deliberately)

- **Every URL, every endpoint name, every response shape.** `*.php` paths still resolve (Caddy proxies them to Go's dispatcher which matches on path verbatim). Existing bookmarks, Discord embeds, `gh release` cards, and third-party scripts all keep working with zero changes.
- **The same SQLite database file**, untouched by the rewrite — same schema, same rows, same indexes. The Go binary opens it read-write the same way the PHP layer did; no migration step was needed for the cutover.
- **The GPL game tool** (this repo's `kvnaust-recyclebin.html`) is *unchanged* by the rewrite. The wrapper just serves it differently.

### 🔒 Wrapper licensing reminder

The Go backend powering the hosted wrapper is **proprietary**, owned by FalconTechnix. The GPL game tool in this repo and the FORMAT-MAP are unchanged GPL-3.0. The split is the same as it has always been:
- 🌐 **Public repo** = the game tool you can download and run anywhere.
- 🔒 **Private wrapper** = the community layer you can opt into by playing on `kvnaust.falcontechnix.com`.

### 🐛 Bug fixes shipped in this release

- **YouTube metadata fetch now returns full data.** The waterfall (Invidious → oEmbed → scrape) was first-wins, so when oEmbed succeeded with only title/author/thumb, viewCount/published/channelID were never populated. Front-end auto-fill on the rating screen left "Date posted", "Views", and "Ch. videos" blank. The waterfall is now **enriching**: each upstream merges into the result, missing fields are filled by later upstreams. Also added publish-date scrape fallbacks for `datePublished` and `uploadDate` (YouTube reshuffled the watch-page HTML and broke the old `publishDate` regex).
- **`/version-stream.php` SSE endpoint stopped 500'ing.** The logging middleware's `statusRecorder` wraps `http.ResponseWriter` to capture status code + duration, but it didn't proxy the `http.Flusher` interface — so `w.(http.Flusher)` in the SSE handler always returned `false` and the handler bailed with HTTP 500. Result: every open game tab was hammering the endpoint with a 500 every 6 seconds. Added `Flush()` (and `Hijack()` for future websocket support) delegators on `statusRecorder`. Stream now flushes properly; reconnect storm is over.

---

## [Unreleased] - 2026-05-01

### Naming
- **The tool is now named "Sonder"** — for the John Koenig word ("the realization that each random passerby is living a life as vivid and complex as your own…"). KVN AUST uses the word himself in the preface of his Map: *"This feels like sonder, like the way YouTube used to be."* That callback is the entire pitch — every spin pulls up someone's whole-ass life one click away, entirely unwitnessed.
- **Sonder = the tool. YouTube's Recycle Bin = KVN AUST's content concept.** The two names are kept distinct on purpose: KVN's series identity stays his, our tool gets its own banner. In-tool branding always pairs them ("Sonder · for KVN AUST's Recycle Bin") so the attribution is unmistakable.
- Carefully scoped rename: `<title>`, start-screen H1, header bar, all four SEO meta surfaces (description, og, twitter, JSON-LD `name` + new `alternateName`), README h1 + opening prose, GitHub repo description. Filename `kvnaust-recyclebin.html` and repo name `KVN_AUST` deliberately UNCHANGED — renaming either would break the hosted wrapper, every existing bookmark, and every offline-downloaded copy.
- New **Sonder etymology modal** opens when the player clicks the H1 ("Sonder") on the start screen or the header title — shows the full Koenig poetic passage with attribution + KVN's "feels like sonder" callback. Animated rainbow gradient on the headline word. Esc-friendly close.

### Domain
- **Hosted at `https://kvnaust.falcontechnix.com`** (canonical). The previous URL `https://falcontechnix.com/KVN_AUST/` still works and redirects to the new subdomain. All in-tool links, SEO meta (`canonical`, `og:url`, `twitter:image`, JSON-LD `url`), API constants (`FINDS_API`, `LIVE_URL`), share-card watermarks, Discord copy strings, READMEs, FORMAT-MAP, SOLVED_MYSTERIES, WRAPPER_CHANGELOG, DISCORD_INTEGRATION, and the leaderboard-sync workflow all point at the new subdomain.

## [6.1.1] - 2026-04-30

### Format Map
- **Map 4.0 sync** ([source](https://tinyurl.com/y5xx29bj)): bulk import from KVN AUST's latest map alongside the *"0-View YouTube until I get a Bingo (Hard Mode)"* video. ~50 new numbered formats (long-tail camera/trail-cam/action-cam/drone), 17 new date-based formats (game-capture, screen-recorder, webcam eras), 16 new keyphrases (Russian Photo Story duplicates, `"Moviemakeronline com"` family, NSFW playlist filters). Net total +75 unique formats (192 → 267). New multi-variable patterns documented separately. Badge counts auto-update via `update-format-count.yml`.
- **Hex/alpha format parser**: `MOL0XX`, `4XXX`, `Trim 4XXX`, `Copy 4XXX`, `Video 4XXX` now generate real hex search strings (`MOL0E5`, `4A2F`, etc) in the spinner. Previously these were silently skipped because their range columns (`A-F`, `AAA-FFF`) didn't match the digit-only parser. New `sp:'hexN'` template type with configurable hex-digit count.
- **Badge counter deduped**: `update-format-count.yml` now counts UNIQUE keyphrases per section, ignoring the "Recently Added" preview rows (which duplicate entries that also live in their proper sections) and the Multi-Variable bullet list (not auto-loaded). Badge total now reflects actual unique format count.

### Game Tool
- **KVN Recycle Bin video gallery**: new "KVN's Recycle Bin Videos" button on the start screen opens a slide-in panel with every Recycle Bin / 0-View / mapping / Bingo video on @KVNAUST (18 videos, scraped from the channel and curated to filter out off-topic uploads). Each card shows YouTube thumbnail, title, and publish date; clicking opens the video on YouTube. Videos published in the last 24 hours render with a pulsing red border, a "NEW" corner badge, and a "JUST DROPPED" meta tag — and a small NEW dot lights up on the start-screen button so the player knows there's something fresh without opening the panel. Re-checks every 10 minutes.
- **Lose-a-Space spinner penalty**: when bingo is active and the player has marked spaces, the wheel now sprinkles configurable `LOSE A SPACE` penalty segments (dark-red). Landing on one opens a dramatic overlay — counts marked spaces, rolls a random index, picks a random cell, plays a sad-trombone descending fanfare and unmarks it. Matches the new mechanic from KVN's Hard Mode video.
- **Pre-game setup panel** on the start screen: configurable Lose-a-Space slot count (0–10, default 2) and Free Space toggle (on by default — turn off for a 25-category card). Settings persist across sessions.
- **30 auto-rotating spinner themes**: Carnival, Pastels, Primaries, Mono, Sunset, Ocean, Forest, Neon, Earth, Candy, Vaporwave, Autumn, Spring, Cyberpunk, MardiGras, Berry, Tropical, Mute, Royal, Sunrise, Mint, Crimson, Ice, Lava, Galaxy, Jungle, Desert, Eighties, Nineties, Garden, Royal2, Rainbow. Rotation triggers on a calendar-day boundary OR after the player saves 2 full games and starts a 3rd. Theme survives soft refreshes via localStorage. Deep Dive remains the only manually-toggleable theme.
- **Bottom bar auto-hide**: the credit footer now hides automatically when a game starts and reappears when the game ends (summary screen) or the player returns to the start screen. If the user manually X's the footer, that user choice is respected — auto-show is suppressed.
- **Free / non-profit messaging**: README and start screen rewritten to actively encourage downloading the standalone HTML and running it locally. Hosted version is positioned as the optional community layer, not the default. Stronger guarantees: no ads, no paywalls, no tracking, no monetization, ever.

### Infrastructure
- **Leaderboard sync workflow hardened**: `update-leaderboard.yml` now retries the `finds.php` fetch (5×, 10s delay), validates JSON before processing, and skips the run cleanly on persistent failure instead of marking it red. Stops the Actions tab from filling up with sync errors when the API hiccups.
- **Authenticated sync**: workflow now sends `X-KVN-Sync-Token: ${{ secrets.KVN_SYNC_TOKEN }}` so the host can whitelist GitHub Actions traffic without opening `finds.php` to the world. Set `KVN_SYNC_TOKEN` in repo secrets to enable.

---

## [6.0.0] - 2026-04-27 (Wrapper 1.12.0)

> See [WRAPPER_CHANGELOG.md](WRAPPER_CHANGELOG.md) for the full hosted platform changelog.

### Hosted Platform (Wrapper 1.12.0)
- **Player profiles**: XP, levels (sqrt scaling), 15 server-side badges, lifetime rank, streaks. Shareable profile cards (1200×630 SVG). Compare two players side-by-side.
- **Seasons**: 90-day competitive windows, auto-seeded. Filter leaderboard by `?season=current`. iCalendar feed at `/seasons.ics`.
- **Multiplayer**: SSE-based co-op rooms for signed-in users. Create room → share link → play together.
- **Permanent discovery pages**: every find gets a shareable URL at `/discoveries/<video_id>` with OG card and embed.
- **Format heatmap**: `?heatmap=1` returns category × decade aggregation matrix.
- **Atom feed**: subscribe to new finds at `/feed.xml`.
- **OpenAPI spec**: full API documentation at `/openapi.json`.
- **Display names**: public alias separate from login. Set via account settings, auto-updates all leaderboard attributions.
- **Records bridge**: in-game records auto-submit to the public leaderboard with video metadata enrichment.
- **Live status**: `/status.php` returns online users, find counts, active season, data quality metrics.

---

### Added
- **Achievement system**: 15 badges tracked in localStorage — First Dive, Veteran Diver, Deep Searcher, First Blood, Ghost Hunter, Record Collector, Legendary Find, Super Rare, Time Traveler, BINGO!, Deep Diver, Bubble Pop, Format Master, Gem Finder, Show & Tell. Toast + triangle fanfare on unlock. Badges modal with grid display. Hash routing `#achievements`/`#badges`.
- **Timeline zoom/pan**: scroll to zoom (1x–10x), drag to pan, touch support, "Reset Zoom" button. Year labels scale with zoom level. Dots, zones, and beams all respond to zoom.
- **Video gallery**: grid of all found videos with thumbnails. Search, sort by recent/oldest/views/rating. Click to open on YouTube. Accessible via header "Gallery" button or `#gallery` hash.
- **Service worker**: `sw.js` caches app assets for full offline PWA support. Network-first for API calls, cache-first for static assets. Auto-updates on new version.
- **Starfield background**: subtle star pattern with colored nebula dots on a second layer, both slowly drifting at different speeds.

### Changed
- **Screen transitions**: cinematic blur+scale on entry, 3D perspective rotation on exit
- **Mobile responsive**: comprehensive breakpoints at 600px and 380px covering header, spinner, bingo, result screen, modals, panels, number display, nav arrows, and summary

---

## [5.3.1] - 2026-04-25

### Fixed
- **Records entries now include `lead` field** — format label saved when adding from result screen, enables wrapper→finds.php bridge to include the lead/keyphrase used
- **SOLVED_MYSTERIES.md** now included in server sync pull list and .htaccess allowlist

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

<sub>[KVN AUST](https://youtube.com/@KVNAUST) | [Play Now](https://kvnaust.falcontechnix.com/) | [GitHub](https://github.com/sworrl/KVN_AUST)</sub>

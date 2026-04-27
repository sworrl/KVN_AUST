<h1 align="center">
  <br>
  Discord Integration Guide
  <br>
  <sub>KVN AUST Community Finds Leaderboard</sub>
  <br>
</h1>

<p align="center">
  <a href="https://www.youtube.com/@KVNAUST"><img src="https://img.shields.io/badge/YouTube-KVN_AUST-red?style=flat-square&logo=youtube" alt="YouTube"></a>
  <a href="https://falcontechnix.com/KVN_AUST/#records"><img src="https://img.shields.io/badge/LEADERBOARD-Live_Records-ffd700?style=flat-square" alt="Leaderboard"></a>
  <a href="https://falcontechnix.com/KVN_AUST/"><img src="https://img.shields.io/badge/PLAY_NOW-falcontechnix.com-e74c3c?style=flat-square" alt="Play"></a>
</p>

---

Everything a Discord bot or server owner needs to pull the live zero-view finds leaderboard from the [Finds API](https://www.falcontechnix.com/KVN_AUST/finds.php) and post it into their channel.

**Read-only.** The public API only supports GET. All writes go through the [hosted game tool](https://falcontechnix.com/KVN_AUST/) or the admin ingest pipeline. Discord bots can pull, display, track, and react to new finds — but cannot alter or delete them.

---

## API at a Glance

```
GET https://www.falcontechnix.com/KVN_AUST/finds.php
```

- Public, no auth required
- Rate limit: **3 requests per 60 seconds per IP**
- Conditional GET with `If-None-Match: <etag>` — 304 responses are free (don't count against the budget)
- `Cache-Control: public, max-age=60` + `ETag` headers

## Query Parameters

| Param | Example | Effect |
|:------|:--------|:-------|
| `since` | `2026-04-20T00:00:00` | Only finds ingested after this timestamp — use this to detect new additions |
| `category` | `camera-mvi` | Filter by lead category |
| `source` | `discord` | Filter by submission source |
| `order` | `desc` | `asc` (default) or `desc` by `date_posted` |
| `limit` | `10` | Cap results (max 500, default 500) |

## Response Shape

```json
{
  "ok": true,
  "total": 21,
  "returned": 21,
  "oldest_post_date": "2005-09-05",
  "newest_post_date": "2025-12-10",
  "last_ingest_at": "2026-04-20 03:45:09",
  "rate_limit": { "remaining": 2, "resets_in": 60, "max": 3, "window": 60 },
  "rarity_colors": {
    "LEGENDARY": "#ffd700",
    "SUPER RARE": "#e74c3c",
    "VERY RARE": "#e67e22",
    "RARE": "#2ecc71",
    "COMMON": "#3498db"
  },
  "finds": [
    {
      "id": 7,
      "video_id": "ExMSFNh7Sp0",
      "video_url": "https://www.youtube.com/watch?v=ExMSFNh7Sp0",
      "video_title": "Testing",
      "channel_name": "Maxwang",
      "channel_videos": 1,
      "channel_subs": 4,
      "date_posted": "2005-09-05",
      "views_when_found": 197,
      "lead": "testing before:2007",
      "lead_category": "time-filter",
      "rarity": "LEGENDARY",
      "found_by": "fivezies",
      "source": "discord",
      "server": "KVN AUST Discord",
      "thumbnail_url": "https://img.youtube.com/vi/ExMSFNh7Sp0/mqdefault.jpg",
      "note": null,
      "discovered_at": "2026-04-20 03:45:09"
    }
  ]
}
```

---

## Rarity Tiers

The API returns the color palette with every response so embeds match the game's theme:

| Tier | Color | Hex | Video Posted |
|:-----|:------|:----|:-------------|
| LEGENDARY | Gold | `#ffd700` | 2005 or earlier |
| SUPER RARE | Red | `#e74c3c` | 2006 |
| VERY RARE | Orange | `#e67e22` | 2007-2008 |
| RARE | Green | `#2ecc71` | 2009-2012 |
| COMMON | Blue | `#3498db` | 2013+ |

---

## Ready-to-Run Discord Bot (Node.js)

Requires [discord.js](https://discord.js.org/) v14+.

```bash
npm install discord.js
```

```js
const { Client, GatewayIntentBits, EmbedBuilder } = require('discord.js');
const https = require('https');

const DISCORD_TOKEN = process.env.DISCORD_TOKEN;
const LEADERBOARD_CHANNEL_ID = process.env.LEADERBOARD_CHANNEL_ID;
const FINDS_API = 'https://www.falcontechnix.com/KVN_AUST/finds.php';
const POLL_INTERVAL_MS = 90_000; // 90s — safe under 3/60s limit

let lastSeenIngest = null;
let lastEtag = null;

const client = new Client({ intents: [GatewayIntentBits.Guilds] });

function fetchFinds() {
  return new Promise((resolve, reject) => {
    const headers = lastEtag ? { 'If-None-Match': lastEtag } : {};
    const url = lastSeenIngest
      ? `${FINDS_API}?since=${encodeURIComponent(lastSeenIngest)}&order=desc`
      : `${FINDS_API}?order=desc&limit=5`;

    https.get(url, { headers }, res => {
      if (res.statusCode === 304) return resolve({ unchanged: true });
      if (res.statusCode === 429) return reject(new Error('rate_limited'));
      if (res.statusCode !== 200) return reject(new Error('http_' + res.statusCode));
      lastEtag = res.headers.etag || lastEtag;
      let data = '';
      res.on('data', c => data += c);
      res.on('end', () => { try { resolve(JSON.parse(data)); } catch (e) { reject(e); } });
    }).on('error', reject);
  });
}

function buildEmbed(find, palette) {
  return new EmbedBuilder()
    .setTitle(find.video_title || 'Untitled')
    .setURL(find.video_url)
    .setColor(parseInt((palette[find.rarity] || '#888').slice(1), 16))
    .setThumbnail(find.thumbnail_url)
    .addFields(
      { name: 'Rarity', value: find.rarity || 'COMMON', inline: true },
      { name: 'Views', value: String(find.views_when_found ?? '?'), inline: true },
      { name: 'Posted', value: find.date_posted || '?', inline: true },
      { name: 'Channel', value: `${find.channel_name || '?'} (${find.channel_videos ?? '?'} videos)` },
      { name: 'Lead', value: '`' + (find.lead || '?') + '`', inline: true },
      { name: 'Found by', value: find.found_by || '?', inline: true },
    )
    .setFooter({ text: `${find.server || 'Community'} · KVN AUST Leaderboard` })
    .setTimestamp(new Date(find.discovered_at));
}

async function poll() {
  try {
    const payload = await fetchFinds();
    if (payload.unchanged) return;
    const channel = await client.channels.fetch(LEADERBOARD_CHANNEL_ID);
    const newFinds = (payload.finds || []).filter(f =>
      !lastSeenIngest || new Date(f.discovered_at) > new Date(lastSeenIngest)
    );
    for (const find of newFinds.reverse()) {
      await channel.send({ embeds: [buildEmbed(find, payload.rarity_colors)] });
    }
    if (payload.last_ingest_at) lastSeenIngest = payload.last_ingest_at;
  } catch (e) { console.warn('[kvn-finds] poll error:', e.message); }
}

client.once('ready', () => {
  console.log(`Logged in as ${client.user.tag}`);
  poll();
  setInterval(poll, POLL_INTERVAL_MS);
});

// /leaderboard slash command
client.on('interactionCreate', async (ix) => {
  if (!ix.isChatInputCommand() || ix.commandName !== 'leaderboard') return;
  await ix.deferReply();
  try {
    const res = await new Promise((resolve, reject) =>
      https.get(FINDS_API + '?order=asc&limit=5', r => {
        let d = ''; r.on('data', c => d += c); r.on('end', () => resolve(JSON.parse(d)));
      }).on('error', reject)
    );
    const embeds = (res.finds || []).slice(0, 5).map(f => buildEmbed(f, res.rarity_colors));
    await ix.editReply({ content: `**Oldest zero-view finds** (${res.total} total)`, embeds });
  } catch (e) { await ix.editReply('Leaderboard fetch failed: ' + e.message); }
});

client.login(DISCORD_TOKEN);
```

```bash
DISCORD_TOKEN=xxx LEADERBOARD_CHANNEL_ID=xxx node bot.js
```

---

## Python Alternative (discord.py)

```python
import os, asyncio, aiohttp, discord

FINDS_API = 'https://www.falcontechnix.com/KVN_AUST/finds.php'
TOKEN = os.environ['DISCORD_TOKEN']
CHANNEL_ID = int(os.environ['LEADERBOARD_CHANNEL_ID'])

intents = discord.Intents.default()
client = discord.Client(intents=intents)
last_etag, last_seen = None, None

async def fetch_finds(session):
    global last_etag, last_seen
    headers = {'If-None-Match': last_etag} if last_etag else {}
    params = {'order': 'desc', 'limit': 5}
    if last_seen: params['since'] = last_seen
    async with session.get(FINDS_API, params=params, headers=headers) as r:
        if r.status == 304: return None
        if r.status != 200: return None
        last_etag = r.headers.get('etag', last_etag)
        return await r.json()

def build_embed(f, palette):
    color = int(palette.get(f.get('rarity'), '#888888').lstrip('#'), 16)
    e = discord.Embed(title=f.get('video_title', 'Untitled'), url=f['video_url'], color=color)
    e.set_thumbnail(url=f['thumbnail_url'])
    e.add_field(name='Rarity', value=f.get('rarity', 'COMMON'), inline=True)
    e.add_field(name='Views', value=str(f.get('views_when_found', '?')), inline=True)
    e.add_field(name='Posted', value=f.get('date_posted', '?'), inline=True)
    e.add_field(name='Channel', value=f"{f.get('channel_name','?')} ({f.get('channel_videos','?')} videos)")
    e.add_field(name='Lead', value=f"`{f.get('lead','?')}`", inline=True)
    e.add_field(name='Found by', value=f.get('found_by', '?'), inline=True)
    e.set_footer(text=f"{f.get('server','Community')} · KVN AUST Leaderboard")
    return e

async def poll_loop():
    global last_seen
    await client.wait_until_ready()
    channel = client.get_channel(CHANNEL_ID)
    async with aiohttp.ClientSession() as session:
        while not client.is_closed():
            try:
                data = await fetch_finds(session)
                if data:
                    for f in reversed(data.get('finds', [])):
                        if last_seen and f['discovered_at'] <= last_seen: continue
                        await channel.send(embed=build_embed(f, data['rarity_colors']))
                    last_seen = data.get('last_ingest_at', last_seen)
            except Exception as e: print('[kvn-finds] poll error:', e)
            await asyncio.sleep(90)

@client.event
async def on_ready():
    print(f'Logged in as {client.user}')
    client.loop.create_task(poll_loop())

client.run(TOKEN)
```

---

## Bash / Webhook Only (Simplest)

Post the current top 5 to a channel via an incoming webhook — no bot needed, just a cron job:

```bash
#!/usr/bin/env bash
WEBHOOK="https://discord.com/api/webhooks/XXXXX/YYYYY"
curl -s "https://www.falcontechnix.com/KVN_AUST/finds.php?order=asc&limit=5" \
  | jq -c '{
      content: ("**KVN AUST Oldest Finds** (" + (.total|tostring) + " total)"),
      embeds: [.finds[] | {
        title: .video_title,
        url: .video_url,
        color: 15790080,
        thumbnail: {url: .thumbnail_url},
        fields: [
          {name: "Rarity", value: .rarity, inline: true},
          {name: "Views", value: (.views_when_found|tostring), inline: true},
          {name: "Date", value: .date_posted, inline: true},
          {name: "Channel", value: .channel_name},
          {name: "Found by", value: .found_by, inline: true},
          {name: "Lead", value: .lead, inline: true}
        ]
      }]
    }' \
  | curl -s -H "Content-Type: application/json" -X POST "$WEBHOOK" -d @-
```

---

## Rate Limiting

| Scenario | Safe? |
|:---------|:------|
| Poll every **90 seconds** | Always safe |
| Poll every **20 seconds with ETag** | Safe (304s are free) |
| Poll every **20 seconds without ETag** | Will hit 429 |
| Burst 3 requests at once | OK, but budget is spent for 60s |

If you get a 429, respect the `Retry-After` header and back off.

---

## Detecting New Finds

Each find has `discovered_at` — the timestamp when the server ingested it (not when the video was posted). Track the highest `discovered_at` you've seen, then pass it as `?since=<timestamp>` on the next poll. Only new entries come back. Both bot examples above use this pattern.

---

## Submission Attribution

Every find includes:
- **`found_by`** — the Discord username or player handle who submitted it
- **`source`** — where it came from (`discord`, `game`, `manual`)
- **`server`** — which Discord server or context

Credit finders in your embeds:

> **MVI 02581** (1 view, posted 2009-04-24) — found by **soph** in KVN AUST Discord

---

<p align="center">
  <sub><a href="https://github.com/sworrl/KVN_AUST">GitHub</a> | <a href="https://falcontechnix.com/KVN_AUST/">Play Now</a> | <a href="https://falcontechnix.com/KVN_AUST/#records">Live Leaderboard</a> | <a href="FORMAT-MAP.md">Format Map</a></sub>
</p>

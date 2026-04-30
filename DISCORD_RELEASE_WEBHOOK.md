# Auto-post KVN AUST tool releases to Discord

A request to the Discord server owner — **5 minute, set-once-forget-forever** wiring.

## What this does

Right now every time a new release ships to <https://github.com/sworrl/KVN_AUST>, someone has to manually paste the CHANGELOG link into the update channel. The Discord embed often shows stale info (it gets cached, the README description lags, etc).

GitHub has a native Discord webhook integration. Once it's configured, **every new GitHub release auto-posts to the Discord channel** with:

- The release title (e.g. *"v6.1.0 — Map 4.0 sync, Lose-a-Space, 30 themes, video gallery"*)
- The full release notes (formatted)
- A direct link to the release page
- The repo's avatar

No more manual posts, no more stale embeds.

## What I need from you (the server owner)

### 1. Create a Discord webhook in the update channel

1. Right-click the channel where releases should land (e.g. `#update-reports` or `#yrb-game`).
2. **Edit Channel → Integrations → Webhooks → New Webhook**.
3. Name it something like `KVN AUST GitHub` and pick an avatar (the KVN logo works well).
4. Click **Copy Webhook URL**. It'll look like:
   ```
   https://discord.com/api/webhooks/<numeric-id>/<token>
   ```
5. **Append `/github` to the end** of that URL — this tells Discord to use GitHub-flavored formatting:
   ```
   https://discord.com/api/webhooks/<numeric-id>/<token>/github
   ```

### 2. Send the URL to the repo owner

DM the URL to whoever runs `sworrl/KVN_AUST` (don't post it in a public channel — anyone with the URL can post messages as the webhook).

That's it on your end. The repo owner does the GitHub-side wiring.

---

## What the repo owner does (FYI — already documented for them)

In `sworrl/KVN_AUST` → **Settings → Webhooks → Add webhook**:

- **Payload URL**: the `/github`-suffixed URL from step 1
- **Content type**: `application/json`
- **Secret**: leave blank (Discord ignores it)
- **Which events**: select **"Let me select individual events"** → check only **"Releases"** (uncheck everything else, otherwise every push/PR/issue will spam the channel)
- **Active**: yes
- Click **Add webhook**

GitHub will send a ping immediately. If it shows ✓ green in the webhook list, it's working.

## What you'll see in Discord

When the next release ships, a card like this lands in the channel:

> **[Released v6.1.0 — Map 4.0 sync, Lose-a-Space, 30 themes, video gallery](https://github.com/sworrl/KVN_AUST/releases/tag/v6.1.0)**
>
> Justin published a release for sworrl/KVN_AUST.
>
> *(release notes preview...)*

Clean, automatic, never out of date.

## If you want to remove it later

Same path: **Edit Channel → Integrations → Webhooks → click the webhook → Delete Webhook**. The repo side stops receiving 200s and just retries quietly until it gives up. No drama.

---

## Why this beats the current flow

| | Manual paste (current) | Auto webhook (proposed) |
|:---|:---|:---|
| Effort per release | Open repo, copy CHANGELOG link, paste, hope embed is fresh | Zero — happens automatically |
| Embed accuracy | Often shows cached/stale repo description | Pulls live release notes every time |
| Formatting | Plain link with whatever Discord scraped | GitHub-styled embed with notes preview |
| Risk if forgotten | Players don't know about the update | Impossible to forget — it's automatic |
| Setup time | — | ~5 minutes, one time |

If you have any concerns or want a different channel, just say so and we'll wire it up wherever makes sense. Thanks!

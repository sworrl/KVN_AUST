Hey — quick favor, takes ~5 min.

Every time I ship a new release for the Recycle Bin tool, I'm manually pasting the changelog into `#update-reports` and the Discord embed often pulls a stale repo description. GitHub has a native Discord webhook that auto-posts releases as a clean formatted card — title, notes preview, link — but I can't set it up without a webhook URL from your server.

If you're cool with it:

1. Right-click the channel you want updates in (probably `#update-reports` or `#yrb-game`) → **Edit Channel → Integrations → Webhooks → New Webhook**.
2. Name it whatever, KVN avatar if you want.
3. **Copy Webhook URL** — looks like `https://discord.com/api/webhooks/<id>/<token>`.
4. **Add `/github` to the end** so it becomes `…/<token>/github`. That's the magic suffix that tells Discord to format release posts properly.
5. DM me the URL (don't post it publicly — anyone with it can post as the bot).

I'll wire up the GitHub side and from the next release on it just works. Hit Delete Webhook anytime to kill it, no drama.

Different channel or any tweaks, just say.

Thanks 🙏

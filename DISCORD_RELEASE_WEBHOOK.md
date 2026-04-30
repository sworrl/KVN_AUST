Hey — quick favor, takes maybe 5 minutes on your end.

I run the [KVN AUST Recycle Bin tool repo](https://github.com/sworrl/KVN_AUST) (the bingo + spinner game tool, plus the format map). Right now every time I ship a new release I have to manually paste the changelog into your `#update-reports` channel, and the embed half the time pulls a stale repo description from when Discord first cached it. It's clunky and the players miss updates.

GitHub has a built-in Discord webhook integration that auto-posts new releases — clean formatted card with the title, notes preview, and link. I just can't set it up without your help because I can't make webhooks in your server.

If you're cool with it, here's all you need to do:

1. Right-click the channel you want updates in (probably `#update-reports` or `#yrb-game`) → **Edit Channel → Integrations → Webhooks → New Webhook**.
2. Name it `KVN AUST GitHub` or whatever, give it the KVN avatar if you want.
3. Click **Copy Webhook URL**. It looks like `https://discord.com/api/webhooks/<id>/<token>`.
4. **Add `/github` to the end** of that URL — that's the magic suffix that tells Discord to format release posts properly. So the final URL is `https://discord.com/api/webhooks/<id>/<token>/github`.
5. DM me that URL (don't post it publicly — anyone with it can post messages as the bot).

That's it. I'll wire it up on the GitHub side and from the next release on, it just works. Zero load on you forever.

If you ever want it gone — same path, hit Delete Webhook on the integrations page and it stops. No drama.

Picking a different channel or want any tweaks first, just say the word.

Thanks 🙏

— Justin

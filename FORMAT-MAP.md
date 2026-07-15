<h1 align="center">
  <br>
  YouTube's Recycle Bin
  <br>
  <sub>The Complete Format Map</sub>
  <br>
</h1>

<p align="center">
  <a href="https://www.youtube.com/@KVNAUST"><img src="https://img.shields.io/badge/YouTube-@KVNAUST-red?style=for-the-badge&logo=youtube" alt="YouTube"></a>
  <a href="https://x.com/MingKasterMK"><img src="https://img.shields.io/badge/X-@MingKasterMK-black?style=for-the-badge&logo=x" alt="X/Twitter"></a>
  <a href="https://kvnaust.falcontechnix.com/"><img src="https://img.shields.io/badge/PLAY_NOW-kvnaust.falcontechnix.com-e74c3c?style=for-the-badge" alt="Play Now"></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/TOTAL_FORMATS-427-e74c3c?style=flat-square&labelColor=1a1a2e" alt="432 Total Formats">
  <img src="https://img.shields.io/badge/Search_Keyphrases-151-3498db?style=flat-square&labelColor=1a1a2e" alt="151 Search Keyphrases">
  <img src="https://img.shields.io/badge/File_Extensions-20-9b59b6?style=flat-square&labelColor=1a1a2e" alt="20 File Extensions">
  <img src="https://img.shields.io/badge/Numbered_Formats-169-2ecc71?style=flat-square&labelColor=1a1a2e" alt="169 Numbered Formats">
  <img src="https://img.shields.io/badge/Date--Based-45-e67e22?style=flat-square&labelColor=1a1a2e" alt="45 Date-Based Formats">
  <img src="https://img.shields.io/badge/Ancient_YouTube-42-f39c12?style=flat-square&labelColor=1a1a2e" alt="47 Ancient YouTube Formats">
</p>

---

YouTube currently hosts over **20 billion videos**. **93%** have under 1,000 views. **30%** have under 100. This map helps you access the billions of forgotten, zero-view uploads by searching for **default device filenames** that the algorithm never learned to recommend.

The only way to access these videos is to search for the **keyphrase** associated with the device or application used to record them. These are usually the default filenames given to recorded or downloaded videos.

> **For contributors:** The [Recycle Bin tool](https://kvnaust.falcontechnix.com/) parses this file to populate its format spinner. To ensure new numbered formats are picked up, they **must** follow this exact table format:
>
> ```
> | `formatXXXX` | 0000-9999 | Source | Credit |
> ```
>
> - Keyphrase wrapped in backticks (`` ` ``)
> - Must end with 2-4 `X` characters representing the variable portion
> - Range column must be `MIN-MAX` (digits only, separated by hyphen)
> - Entries without `X` patterns or ranges (search keyphrases, file extensions, etc.) are not parsed for the spinner — those are loaded from the hardcoded list in the HTML

---

## Recently Added (April 2026)

> New format leads discovered by [@Chegnus](https://youtube.com/@BASHnBRASS)

| Keyphrase | Type | Source |
|:----------|:-----|:-------|
| `Snapchat-` | Search | Snapchat camera roll saves |
| `"Screencast from"` | Search | GNOME / ChromeOS screen recorder |
| `"zoom_0"` | Search | Zoom local recording default |
| `"Replay"` | Search | Fortnite / game replay exports |
| `".MKV"` | Extension | OBS, MKVToolNix, media rips |
| `".WEBM"` | Extension | Web video, screen recorders |
| `".MTS"` | Extension | AVCHD camcorders |
| `".TS"` | Extension | DVR / IPTV recordings |
| `R001XXXX` (0001-9999) | Numbered | Ricoh cameras / Theta 360 |
| `VIRB0XXX` (001-999) | Numbered | Garmin VIRB action cameras |
| `STE_XXXX` (0001-9999) | Numbered | Samsung stereo video mode |
| `Screencast YYYY-MM-DD` | Date-Based | ChromeOS / GNOME |
| `PANO_YYYYMMDD` | Date-Based | Android panoramic video |
| `vlc-record-YYYY-MM-DD` | Date-Based | VLC media player recording |
| `"Qik"` | Ancient YT | Qik mobile video (2008-2011) |
| `"Made with One True Media"` | Ancient YT | Online video creator (2005-2014) |
| `"Jing"` | Ancient YT | TechSmith Jing (2007-2013) |

### Format Details

**`Snapchat-`** — When you save a Snapchat memory to your camera roll, the file is named `Snapchat-XXXXXXXXXX.mp4` with a long numeric ID. People upload these directly to YouTube without renaming. Snapchat has 800M+ monthly users, so there's a massive pool of accidental uploads with this prefix.

**`"Screencast from"`** — The default filename from GNOME's built-in screen recorder (used on Fedora, Ubuntu, and other Linux desktops) and ChromeOS. With Chromebooks flooding into schools worldwide, this surfaces a huge number of student screen recordings uploaded with the default title.

**`"zoom_0"`** — When you record a Zoom meeting locally (not to cloud), the video file is saved as `zoom_0.mp4` inside a date-stamped folder. People upload these directly. Given Zoom's explosion during 2020+, this surfaces tons of accidental meeting uploads.

**`"Replay"`** — Games like Fortnite, Rocket League, and others have built-in replay systems that export clips with "Replay" in the filename. Players upload these without renaming. Sort by upload date for a constant stream of new gaming clips.

**`".MKV"`** — The Matroska container format. OBS Studio (the most popular streaming/recording software) defaults to `.mkv` output. Also produced by MKVToolNix, HandBrake rips, and media converters. Missing from the original map despite being one of the most common recording formats.

**`".WEBM"`** — Google's open web video format. Used by browser-based screen recorders, Discord video downloads, and various web tools. Chrome's built-in media recorder outputs `.webm` by default.

**`".MTS"`** — The AVCHD format used by Sony, Panasonic, and Canon camcorders from roughly 2006-2015. Files are named `00001.MTS`, `00002.MTS`, etc. The numbered pattern `0XXXX.MTS` was already on the map, but searching the bare extension `".MTS"` casts a wider net.

**`".TS"`** — Transport Stream format. Used by DVRs, IPTV set-top boxes, and TV capture cards. When people record live TV or rip DVR content, the raw files are `.ts`. These surface a lot of accidental TV recordings uploaded to YouTube.

**`R001XXXX`** (0001-9999) — Ricoh cameras (GR series, GR III, etc.) and the Ricoh Theta 360 cameras all save video as `R0010001.MP4`, `R0010002.MP4`, etc. The `R001` prefix followed by a 4-digit number. Ricoh GR is popular with street photographers who also shoot video; Theta 360 videos are frequently uploaded to YouTube.

**`VIRB0XXX`** (001-999) — Garmin VIRB action cameras (VIRB X, VIRB XE, VIRB Ultra 30, VIRB 360). Popular with cyclists, hikers, and outdoor athletes. Files are saved as `VIRB0001.MP4`, `VIRB0002.MP4`, etc. Niche but produces genuinely forgotten footage.

**`STE_XXXX`** (0001-9999) — Samsung cameras' stereo video mode. When recording in 3D/stereo mode on certain Samsung cameras and phones, the output file is prefixed `STE_` followed by a 4-digit number. Less common than standard Samsung video, making these finds more interesting.

**`Screencast YYYY-MM-DD`** — ChromeOS and GNOME save screen recordings with the exact pattern `Screencast YYYY-MM-DD HH.MM.SS`. The date-based version of `"Screencast from"` — use this with `Before:` filters to find older recordings.

**`PANO_YYYYMMDD`** — Android phones save panoramic videos with the prefix `PANO_` followed by the date. People occasionally upload panoramic videos to YouTube with the default filename intact.

**`vlc-record-YYYY-MM-DD`** — VLC media player's built-in recording function saves files as `vlc-record-YYYY-MM-DD-HHhMMmSSs-[source].mp4`. More specific than the existing `VLC Record` keyphrase and better for date-filtered searches.

**`"Qik"`** — Qik was one of the first mobile live-streaming apps, launching in 2008. It had a direct "upload to YouTube" button that auto-titled videos with "Qik" in the name. Skype acquired it in 2011 and shut it down. Search with `Before:2012` to find ancient zero-view uploads from the early mobile video era.

**`"Made with One True Media"`** — One True Media was an online video editor popular from 2005-2014 (acquired by Verizon, then shut down). It let people make slideshows and montages and upload directly to YouTube. The default title included "Made with One True Media." Search with `Before:2015` for deep graveyard content.

**`"Jing"`** — TechSmith Jing was a free screen capture tool (2007-2013) that could record short screencasts and share them. It had YouTube upload integration. The default upload title included "Jing." Search with `Before:2014` for old tutorial attempts and desktop recordings from the early screen-sharing era.

---

## Map 5.0 Sync (July 2026)

> Bulk import of the **183 new leads** from KVN AUST's Map 5.0 doc (452 total leads) — announced in [this X post by @MingKasterMK](https://x.com/MingKasterMK/status/2077144462589895067). Credits flow back to the original contributors named in the doc.

**Highlights:** the EA Sports console-DVR capture IDs (`501A0001`, `NHL14XBX`, `741A0001`, …), a wave of international default titles (Portuguese, Polish, Thai, Korean, Japanese, Chinese, Czech, Hungarian, Indonesian, Dutch), the `Magisto` / `Wondershare` / `WeVideo` editor families, AI-slop keyphrases (`"PixVerse * Image Text *"`, `"Generated File"`, `"vidu video"`), doorbell/security-camera formats (`"RingVideo"`, `CH000000000000XX`), and the VHS-rip wildcard searches (`"VCD" * "0"`).

**Parser note:** single-variable patterns like `"Screencast X"` and odd date orders like `ScreenRecording MM DD YYYY` are listed in the **manual substitution** bullet lists (not tables) so the spinner never ships a half-substituted search.

---

## Map 4.0 Sync (April 2026)

> Bulk import from KVN AUST's [Map 4.0 Google Doc](https://tinyurl.com/y5xx29bj) — published alongside the *"Exploring 0-View YouTube until I get a Bingo (Hard Mode)"* video. Credits flow back to the original contributors named in the doc.

**~50 new numbered formats** (mostly long-tail camera/trail-cam/action-cam patterns), **17 new date-based formats** spanning game-capture, screen-recorder, and webcam eras, and **a dozen new keyphrases** including the `"копия видео"` Russian Photo Story duplicates, the `"Moviemakeronline com"` family, and the `Clips4Sale` / `XXXp` playlist-filter set.

**Multi-variable patterns** (`P1XX0XXX`, `PAXX0XXX`, `PBXX0XXX`, `VXX0XXX`, `PCXX00XX`, `"Sequence XX X"`) are documented in this map for human reference, but the spinner only auto-parses single-range entries — those need manual substitution at search time.

**NSFW filter-playlist keyphrases** (`240p 400k`, `480p 600k`, `480p 2000k`, `720p 1500k`, `720p 4000k`, `Clips4Sale`) are listed for completeness but should be searched with care and the **Filter: Playlist** option active.

---

## Search Keyphrases

> **Sort by:** Upload Date **(MANDATORY)**
> **Search Tools:** Quotations `" "` (e.g. `".MP4"`)

Generic keyphrases that surface brand new zero-view uploads when sorted by upload date.

| Keyphrase | Source | Info | Credit |
|:----------|:-------|:-----|:-------|
| `Snapchat-` | App | Saved memories to camera roll | [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `"Screencast from"` | Screen Recorder | GNOME / ChromeOS default | [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `"zoom_0"` | App | Zoom local recording default | [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `"Replay"` | Game Capture | Fortnite / game replay exports | [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `IMG` | Smartphone | | |
| `MVI` | Camera | | |
| `YYYYMMDD` | Misc | YMD = YearMonthDay | |
| `WIN YYYYMMDD` | Webcam | | |
| `Capture YYYYMMDD` | Webcam | | [@thevoid6756](https://youtube.com/@thevoid6756) |
| `VID YYYYMMDD` | Misc | | |
| `"My Movie X"` | Misc | e.g. "My Movie 1" | |
| `My Montage MM/DD/YY` | Video Editor | One True Media montage title with a short slash date, e.g. "My Montage 03/14/09" | |
| `"My Edited Video"` | Video editor | | [@CharlesMontgomeryBurns.](https://youtube.com/@CharlesMontgomeryBurns.) |
| `/Storage/Emulated/` | Video editor | | |
| `PXL` | Smartphone | | [@stickmandaninacan](https://youtube.com/@stickmandaninacan) |
| `InShot YYYYMMDD` | App | | |
| `WhatsApp Video YYYY` | App | | |
| `FullSizeRender` | Smartphone | | |
| `RPReplay` | Screen Recorder | | |
| `VTS 01` | DVD | | |
| `DVR` | Game Capture | | |
| `VLC Record` | Game Capture / Misc | | |
| `Robloxapp` | Game Capture | Roblox | [@T1MAGEDDON](https://youtube.com/@T1MAGEDDON) |
| `Recording gvo` | Zoom | | [@zxz41_Kristian](https://youtube.com/@zxz41_Kristian) |
| `Lv 0` | Misc | | [@Oopse47](https://youtube.com/@Oopse47) |
| `bmdjAAAF` | Misc | | |
| `YouCut YYYYMMDD` | Misc | | |
| `"Video YYYYMMDD"` | Misc | | |
| `"Copy of Copy of"` | Misc | | [@TheLimeyDragon](https://youtube.com/@TheLimeyDragon) |
| `"Untitled video"` | Misc | | |
| `"Com Oculus Vrshell"` | VR Headset | | |
| `"Com Oculus Metacam"` | VR Headset | | |
| `Desktop YYYY MM DD` | Game Capture | | [@czechgop7631](https://youtube.com/@czechgop7631) |
| `Videoplayback` | Misc | | [@Daldosbm](https://youtube.com/@Daldosbm) |
| `"Video Output"` | Phone | | |
| `KM YYYYMMDD` | Video Editor | | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `Portrait Video Nanny Canon` | Video Editor | NSFW | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `"Sequence 01 1"` | Video Editor | | [@ZuperDarkk](https://youtube.com/@ZuperDarkk) |
| `"Video Assignment"` | Misc | School Projects | |
| `"Untitled Video Made with Clipchamp"` | Video Editor | | [@Jannik323](https://youtube.com/@Jannik323) |
| `"Bandicam"` | Screen Recording | | |
| `"Untitled Design"` | Video Editor | | [@BladeOscReal](https://youtube.com/@BladeOscReal) |
| `"Javaw"` | Game Capture | Minecraft | |
| `"Injected"` | 360 Video | Filter: 360 Video | [@PnfrmEnm](https://youtube.com/@PnfrmEnm) |
| `"Video_ts.vob"` | DVD | | [@BastienSante1902](https://youtube.com/@BastienSante1902) |
| `"MicrosoftTeams Video"` | Misc | | [@H2knad](https://youtube.com/@H2knad) |
| `"Test upload"` | Misc | | |
| `"Moviemakeronline com"` | Misc | | [@Hrotmaister](https://youtube.com/@Hrotmaister) |
| `"myvideo convert2video com"` | Misc | | [@Hrotmaister](https://youtube.com/@Hrotmaister) |
| `"Myvideo imagetovideo com"` | Misc | | [@Hrotmaister](https://youtube.com/@Hrotmaister) |
| `"копия видео"` | Misc | Russia — Photo Story duplicates | [@sScorpioNn1](https://youtube.com/@sScorpioNn1) |
| `"копия видео Копия видео"` | Misc | Russia — double-duplicate | [@sScorpioNn1](https://youtube.com/@sScorpioNn1) |
| `"My Slideshow"` | Video Editor | | |
| `240p 400k` | NSFW Playlist | Filter: Playlist | |
| `480p 600k` | NSFW Playlist | Filter: Playlist | |
| `480p 2000k` | NSFW Playlist | Filter: Playlist | |
| `720p 1500k` | NSFW Playlist | Filter: Playlist | |
| `720p 4000k` | NSFW Playlist | Filter: Playlist | |
| `Clips4Sale` | NSFW Playlist | Filter: Playlist | |
| `"Sans titre"` | Misc | France — "Untitled" | |
| `"mobizen"` | Screen Recorder | | [@qrde](https://youtube.com/@qrde) |
| `"Made with Clipchamp"` | Video Editor | | [@vvvvvvvvvvvvvvv](https://youtube.com/@vvvvvvvvvvvvvvv) |
| `"Made with Flexclip"` | Video Editor | | [@Paper_Frogg](https://youtube.com/@Paper_Frogg) |
| `"Untitled Project"` | Misc | | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `"ScreenRecording"` | Screen Recorder | | [@mentallystablegaming](https://youtube.com/@mentallystablegaming) |
| `"Meeting Recording"` | Microsoft Teams | | |
| `"Meeting in General"` | Microsoft Teams | | [@volevv_](https://youtube.com/@volevv_) |
| `"New Loom Recording"` | Screen Recorder | Loom | [@volevv_](https://youtube.com/@volevv_) |
| `"PixVerse * Image Text *"` | AI Editor | AI Hell — wildcard search | [@user-yh1dn4nk1r](https://youtube.com/@user-yh1dn4nk1r) |
| `"Generated File"` | AI Editor | AI Hell | [@user-yh1dn4nk1r](https://youtube.com/@user-yh1dn4nk1r) |
| `"mp4 media web"` | AI Editor | AI Hell | [@user-yh1dn4nk1r](https://youtube.com/@user-yh1dn4nk1r) |
| `"vidu video"` | AI Editor | AI Hell | [@user-yh1dn4nk1r](https://youtube.com/@user-yh1dn4nk1r) |
| `"VCD" * "0"` | VHS | VHS burned onto DVD — wildcard search | |
| `"DVD" * "0"` | VHS | Wildcard search | |
| `"MP1" * "0"` | VHS | Wildcard search | |
| `"10000000" * * "n"` | Misc | Wildcard search | |
| `NVEExport` | Misc | | [@yura32tv](https://youtube.com/@yura32tv) |
| `"100MEDIA"` | File Path | | [@Pagenonfound](https://youtube.com/@Pagenonfound) |
| `"VR_MOVIE.VRO"` | Camera | DVD camcorder | [@lezyv3104](https://youtube.com/@lezyv3104) |
| `"DVD_VIDEO_RECORDER"` | Misc | | [@lezyv3104](https://youtube.com/@lezyv3104) |
| `"VIDEO TS"` | DVD | | [@user-hv8pk9kp6h](https://youtube.com/@user-hv8pk9kp6h) |
| `"For ipod video and iphone"` | Misc | | [@coolmancool63](https://youtube.com/@coolmancool63) |
| `"Your Paragraph Text"` | Video Editor | Canva placeholder text | [@cchhey3812](https://youtube.com/@cchhey3812) |
| `"Kava Injected"` | 360 Video | | |
| `"story_fbid"` | File Path | Facebook | [@typeone1704](https://youtube.com/@typeone1704) |
| `"Created with @magisto"` | Video Editor | | [@qrde](https://youtube.com/@qrde) |
| `"By Magisto"` | Video Editor | | [@qrde](https://youtube.com/@qrde) |
| `"Created by Magisto - Magical Video Editor"` | Video Editor | | [@qrde](https://youtube.com/@qrde) |
| `"Film nagrany kamerą internetową w dniu"` | Webcam | Poland | [@qrde](https://youtube.com/@qrde) |
| `"Personal Microsoft Edge"` | Screen Recorder | | [@qrde](https://youtube.com/@qrde) |
| `"Profile 1 Microsoft Edge"` | Screen Recorder | | [@qrde](https://youtube.com/@qrde) |
| `Uploaded with Free Leawo Video Converter` | Misc | | [@reverseflesh](https://youtube.com/@reverseflesh) |
| `"sent from my iphone"` | iPhone | | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `"sent from my ipad"` | iPad | | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `"Video Cache"` | Misc | | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `"Created using the one true media"` | Video Editor | Dead service — use Before:2015 | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `"Movie uploaded from Samsung Intelli-studio"` | Video Editor | | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `"Recovered Autosave"` | Video Editor | | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `"Video cam direct upload"` | Camera | Video Response era | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `"Created with iTimelapse"` | Video Editor | Time-lapse | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `"searchstory"` | Video Editor | | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `"Made with Explain Everything"` | Video Editor | | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `"Video created using fotoslides"` | Video Editor | | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `"H 264 LAN"` | Misc | | [@ethanr_5](https://youtube.com/@ethanr_5) |
| `"Fiz este vídeo com o Criador de slides do YouTube"` | Video Editor | Brazil/Portugal | [@AymonAdren](https://youtube.com/@AymonAdren) |
| `"Este vídeo foi enviado de um telefone Android"` | Phone | Brazil/Portugal | [@AymonAdren](https://youtube.com/@AymonAdren) |
| `"This video was produced with a Swivl!"` | Camera | School lecture capture | [@charlescatyt](https://youtube.com/@charlescatyt) |
| `"Created with Wondershare Video Editor"` | Video Editor | | [@ravioliboy3759](https://youtube.com/@ravioliboy3759) |
| `"Created with Wondershare Filmora"` | Video Editor | | [@youtubersingingmoments4402](https://youtube.com/@youtubersingingmoments4402) |
| `"RingVideo"` | Doorbell Camera | | [@lawnside82](https://youtube.com/@lawnside82) |
| `"Ring FrontDoor"` | Doorbell Camera | | [@magaz](https://youtube.com/@magaz) |
| `"Uploaded using 173434605274"` | Video Editor | | [@thebilabialtrill](https://youtube.com/@thebilabialtrill) |
| `"Slideagram"` | Video Editor | | [@thebilabialtrill](https://youtube.com/@thebilabialtrill) |
| `"vlcsnap"` | Misc | VLC snapshot exports | [@xfdhcdjxfhjjtgj](https://youtube.com/@xfdhcdjxfhjjtgj) |
| `"Видео без названия сделано в Clipchamp"` | Video Editor | Russia | [@xfdhcdjxfhjjtgj](https://youtube.com/@xfdhcdjxfhjjtgj) |
| `"Дизайн без названия"` | Misc | Russia — Canva default | [@xfdhcdjxfhjjtgj](https://youtube.com/@xfdhcdjxfhjjtgj) |
| `Мое измененное видео` | Video Editor | Russia | [@GPLeast](https://youtube.com/@GPLeast) |
| `"Dogbook Movie"` | Video Editor | Dead Facebook pet app | [@chipseed](https://youtube.com/@chipseed) |
| `"Catbook Movie"` | Video Editor | Dead Facebook pet app | [@chipseed](https://youtube.com/@chipseed) |
| `"Horsebook Movie"` | Video Editor | Dead Facebook pet app | [@chipseed](https://youtube.com/@chipseed) |
| `"film wideo z telefonu"` | Phone | Poland | [@mazurthc](https://youtube.com/@mazurthc) |
| `"created at animoto.com"` | Video Editor | | [@diberhaze](https://youtube.com/@diberhaze) |
| `"My Vidrhythm"` | Video Editor | | [@TrashonicLizard](https://youtube.com/@TrashonicLizard) |
| `"swf2avi"` | Misc | Flash conversions | [@TrashonicLizard](https://youtube.com/@TrashonicLizard) |
| `"Shot with Geforce"` | Game Capture | Nvidia | [@vvvvvvvvvvvvvvv](https://youtube.com/@vvvvvvvvvvvvvvv) |
| `"XDCAM EX HQ"` | Camera | | [@SJursa-ey4tt](https://youtube.com/@SJursa-ey4tt) |
| `"35 Mbps VBR"` | Bit Rate | | [@SJursa-ey4tt](https://youtube.com/@SJursa-ey4tt) |
| `"video senza titolo"` | Misc | Italy | [@MilkyBloomet](https://youtube.com/@MilkyBloomet) |
| `"My tagged photos in Pummelvision"` | Video Editor | Dead service | [@phoenixkh93](https://youtube.com/@phoenixkh93) |
| `"Mój edytowany film"` | Video Editor | Poland | [@grobokop2357](https://youtube.com/@grobokop2357) |
| `"のコピー"` | Misc | Japan — "copy of" | [@machine.angel.777](https://youtube.com/@machine.angel.777) |
| `"無題のビデオ"` | Misc | Japan — "untitled video" | [@machine.angel.777](https://youtube.com/@machine.angel.777) |
| `"无题"` | Misc | China — "untitled" | [@machine.angel.777](https://youtube.com/@machine.angel.777) |
| `"My great game My great capture"` | Game Capture | | [@urmom694-X](https://youtube.com/@urmom694-X) |
| `"Video dari ponsel saya"` | Phone | Indonesia | [@h8erssss](https://youtube.com/@h8erssss) |
| `"moje upravené video"` | Video Editor | Czechia | [@whosjozikolnik](https://youtube.com/@whosjozikolnik) |
| `"Sent using a Sony Ericsson mobile phone"` | Phone | | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `"Created with WeVideo"` | Video Editor | | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `"Klip wideo bez tytułu"` | Screen Recorder | Poland | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `"my screencast"` | Screen Recorder | | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `"640x360 - SD MP4.mp4"` | Resolution | Music | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `"My Video HQ"` | Video Editor | | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `"Produced with Cyberlink PhotoDirector"` | Video Editor | | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `"HD 1080p 4 8Mbps"` | Resolution | | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `hd 1920 1080` | Resolution | Stock footage | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `"hd 1280 720"` | Resolution | Stock footage | |
| `"hd 3840 2160"` | Resolution | Stock footage | |
| `"What do you think of this picture?"` | Video Editor | | [@nerks5135](https://youtube.com/@nerks5135) |
| `"Minha apresentação de slides"` | Video Editor | Brazil/Portugal | |
| `"Mijn diavoorstelling"` | Video Editor | Netherlands | [@martijn9560](https://youtube.com/@martijn9560) |
| `"Messenger creation"` | Phone | Facebook Messenger | [@Ancend](https://youtube.com/@Ancend) |

---

## File Extensions

> Search with quotations: `".MP4"`, `".MKV"`, etc.

| Extension | Source | Credit |
|:----------|:-------|:-------|
| `".MKV"` | OBS, MKVToolNix, media rips | [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `".WEBM"` | Web video, screen recorders | [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `".MTS"` | AVCHD camcorders | [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `".TS"` | DVR / IPTV recordings | [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `".MP4"` | Universal | |
| `".3gp"` | Early phones | |
| `".MOV"` | Apple / Camera | |
| `".AVI"` | Legacy | |
| `".WMV"` | Windows | |
| `".FLAC"` | Copyright music | |
| `".WAV"` | User-created music | |
| `".3g2"` | Early phones | [@Pagenonfound](https://youtube.com/@Pagenonfound) |
| `".VOB"` | DVD | [@Chernyat5048](https://youtube.com/@Chernyat5048) |
| `".mpeg"` | MPEG video | |
| `".mpg"` | MPEG / DVD rips | [@AymonAdren](https://youtube.com/@AymonAdren) |
| `".flv"` | Flash video | [@JosephVM2](https://youtube.com/@JosephVM2) |
| `".rmvb"` | RealMedia | [@user-hv8pk9kp6h](https://youtube.com/@user-hv8pk9kp6h) |
| `".hevc"` | H.265 raw video | [@user-hv8pk9kp6h](https://youtube.com/@user-hv8pk9kp6h) |
| `".divx"` | DivX encodes | [@NImportant4u](https://youtube.com/@NImportant4u) |
| `".qt"` | QuickTime | [@NImportant4u](https://youtube.com/@NImportant4u) |

---

## Numbered Formats

> **Sort by:** View Count (Optional)
> **Search Tools:** `Before:(Year)` e.g. `Before:2015`, Quotations `" "`

Device-specific filename patterns with numeric ranges. Best for finding old, forgotten videos.

| Keyphrase | Range | Source | Credit |
|:----------|:------|:-------|:-------|
| `R001XXXX` | 0001-9999 | Camera | Ricoh / Theta 360. [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `VIRB0XXX` | 001-999 | Action Cam | Garmin VIRB. [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `STE_XXXX` | 0001-9999 | Camera | Samsung stereo video. [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `IMG XXXX` | 0000-9999 | Smartphone | |
| `MVI XXXX` | 0000-9999 | Camera | |
| `MOV XXXX` | 0000-9999 | Camera | |
| `100 XXXX` | 0000-9999 | Camera | |
| `SAM XXXX` | 0000-9999 | Camera | |
| `DSC XXXX` | 0000-9999 | Camera | |
| `SDV XXXX` | 0000-9999 | Camera | [@kyle6266](https://youtube.com/@kyle6266) |
| `DSCFXXXX` | 0000-9999 | Camera | |
| `DSCNXXXX` | 0000-9999 | Camera | |
| `PICTXXXX` | 0000-9999 | Camera | [@CharlesMontgomeryBurns.](https://youtube.com/@CharlesMontgomeryBurns.) |
| `MAQ0XXXX` | 0000-9999 | Camera | |
| `FILEXXXX` | 0000-9999 | Dashcam | |
| `GOPRXXXX` | 0000-9999 | GoPro | |
| `GP01XXXX` | 0000-9999 | GoPro | |
| `GX01XXXX` | 0000-9999 | GoPro | |
| `DJI XXXX` | 0000-2000 | Drone | [@CharlesMontgomeryBurns.](https://youtube.com/@CharlesMontgomeryBurns.) |
| `HNI 0XXX` | 000-100 | Nintendo DS | [@KILOPOWER](https://youtube.com/@KILOPOWER) |
| `WA0XXX` | 000-999 | Misc | |
| `MOL0XX` | A-F, 0-9 | Camera | [@CharlesMontgomeryBurns.](https://youtube.com/@CharlesMontgomeryBurns.) |
| `"HHMMSS"` | 000000-235959 | Misc | Time of Day |
| `P100XXXX` | 0000-1999 | Camera | |
| `VTS XX X` | 00-99, 0-9 | DVD | |
| `"My Slideshow Video"` | - | Video Editor | |
| `"My Stupeflix Video"` | - | Video Editor | |
| `XXXX.MP4` | 0000-9999 | Misc | |
| `MAH0XXXX` | 0000-9999 | Camera | |
| `CIMGXXXX` | 0000-9999 | Camera | |
| `IMGPXXXX` | 0000-9999 | Camera | |
| `VideoXXXX` | 0000-9999 | Camera | |
| `MOV0XXXX` | 0000-9999 | Camera | |
| `M2U0XXXX` | 0000-9999 | Camcorder | [@blissom](https://youtube.com/@blissom) |
| `GH01XXXX` | 0000-9999 | GoPro | |
| `M4H0XXXX` | 0000-9999 | Camera | [@Fraigo](https://youtube.com/@Fraigo) |
| `M4V0XXXX` | 0000-9999 | Camera | [@AymonAdren](https://youtube.com/@AymonAdren) |
| `SDC1XXXX` | 0000-9999 | Camera | [@saso1901](https://youtube.com/@saso1901) |
| `SANYXXXX` | 0000-9999 | Camera | [@Mackhill8851](https://youtube.com/@Mackhill8851) |
| `HPIMXXXX` | 0000-9999 | Camera | |
| `GEDCXXXX` | 0000-9999 | Camera | [@CharlesMontgomeryBurns.](https://youtube.com/@CharlesMontgomeryBurns.) |
| `VID0XXXX` | 0000-5000 | Camera | [@Techyarchivuma](https://youtube.com/@Techyarchivuma) |
| `DSC 0XXXX` | 0000-5000 | Camera | [@__atob__](https://youtube.com/@__atob__) |
| `CAM0XXXX` | 0000-5000 | Camera | [@Denzelkrocker1673](https://youtube.com/@Denzelkrocker1673) |
| `AMBAXXXX` | 0001-5000 | Action Cam | [@saso1901](https://youtube.com/@saso1901) |
| `HDV XXXX` | 0001-5000 | Camera | [@YeoungBraxx](https://youtube.com/@YeoungBraxx) |
| `DSCIXXXX` | 0001-4000 | Camera | [@Dontzky](https://youtube.com/@Dontzky) |
| `SNV3XXXX` | 0001-3000 | Camera | [@saso1901](https://youtube.com/@saso1901) |
| `MOVXXXXA` | 0000-3000 | Camera | [@AymonAdren](https://youtube.com/@AymonAdren) |
| `Zi6 XXXX` | 0001-2000 | Camera | [@misterherman](https://youtube.com/@misterherman) |
| `ClipXXXX` | 0000-2000 | Misc | [@Techyarchivuma](https://youtube.com/@Techyarchivuma) |
| `YDXJXXXX` | 0001-5000 | Action Cam | [@saso1901](https://youtube.com/@saso1901), range extended by [@isaiah658](https://youtube.com/@isaiah658) |
| `0XXXX.MTS` | 0000-2000 | Camera | [@YeoungBraxx](https://youtube.com/@YeoungBraxx) |
| `SSPXXXXX` | 0001-2000 | Camera | |
| `IMAGXXXX` | 0000-2000 | Camera | [@Piggypiggyyoinkyoink](https://youtube.com/@Piggypiggyyoinkyoink) |
| `CXXXX` | 0000-2000 | Camera | [@A0V1](https://youtube.com/@A0V1) |
| `SUNPXXXX` | 0000-1500 | Camera | [@Ron2600_](https://youtube.com/@Ron2600_) |
| `Picture XXX` | 001-1220 | Phone | [@Techyarchivuma](https://youtube.com/@Techyarchivuma) |
| `PC10XXXX` | 0001-1050 | Camera | |
| `MOVIXXXX` | 0000-1050 | Drone / Dashcam | |
| `PTDCXXXX` | 0000-1000 | Camera | [@PrimeroAtreides](https://youtube.com/@PrimeroAtreides) |
| `VCLPXXXX` | 0001-1000 | Camera | [@__atob__](https://youtube.com/@__atob__) |
| `FHDXXXX` | 0001-1000 | Action Cam | [@Mackhill8851](https://youtube.com/@Mackhill8851) |
| `REC XXXX` | 0000-1000 | Drone / Dashcam | |
| `KVIDXXXX` | 0000-1000 | Camera | [@Junoeclipse7715](https://youtube.com/@Junoeclipse7715) |
| `Moto_0XXX` | 000-999 | Phone | [@Jannik323](https://youtube.com/@Jannik323) |
| `WEB_0XXX` | 001-999 | Camera | [@GaspacoZanis](https://youtube.com/@GaspacoZanis) |
| `ZOOM0XXX` | 001-800 | Camera | [@Alexanderhunt9263](https://youtube.com/@Alexanderhunt9263) |
| `SVM AXXXX` | 0000-1000 | Camera | [@nellip.683](https://youtube.com/@nellip.683) |
| `MUSIC0X.DAT` | 1-9 | DVD (Karaoke) | |
| `AVI00XXX` | 000-100 | Camera | |
| `4XXX` | AAA-FFF | Phone (hex) | |
| `Trim 4XXX` | AAA-FFF | Phone (hex) | |
| `Copy 4XXX` | AAA-FFF | Phone (hex) | |
| `Video 4XXX` | AAA-FFF | Phone (hex) | |
| `"Axon Body * Video"` | - | Body Cam | |
| `"Axon Flex Video"` | - | Body Cam | |
| `"Month DD, YYYY"` | - | Phone | |
| `AVSEQXX` | 00-99 | Misc | [@Set_Your_Handle10](https://youtube.com/@Set_Your_Handle10) |
| `"My Videolicious Video"` | - | Video Editor | [@slurrygeyser8133](https://youtube.com/@slurrygeyser8133) |
| `VTS XXX 1` | 000-999 | DVD | |
| `VTS 01 XXX` | 000-999 | DVD | |
| `"My Slideshow XX"` | 00-99 | Video Editor | |
| `"My Stupeflix Video XXXX"` | 0000-1050 | Video Editor | |
| `AVSEQXX.DAT` | 00-99 | Misc | |
| `AVI 0XXX` | 001-150 | Camera | |
| `00XXXXA` | 0001-2000 | Action Cam | |
| `ВидеоXXXX` | 0000-1000 | Camera | Russia. [@_Mag10_](https://youtube.com/@_Mag10_) |
| `im000XXX` | 001-899 | Camera | [@Lorenzorentniop717](https://youtube.com/@Lorenzorentniop717) |
| `SV A0XXX` | 001-600 | Camera | [@Mackhill8851](https://youtube.com/@Mackhill8851) |
| `Videoplayback XXX` | 1-500 | Misc | |
| `GEDV0XXX` | 001-500 | Camera | [@Mackhill8851](https://youtube.com/@Mackhill8851) |
| `"0001 0XXX"` | 019-500 | Blender 3D | [@BladeOscReal](https://youtube.com/@BladeOscReal) |
| `ACTP0XXX` | 001-400 | Action Cam | [@Mackhill8851](https://youtube.com/@Mackhill8851) |
| `IM000XXX` | 000-400 | Trail Cam / Camera | |
| `MAV 0XXX` | 000-399 | Camera | Japan |
| `MOVIE 0XXX` | 000-300 | Camera | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `ANMR0XXX` | 000-300 | Camera | [@Jannik323](https://youtube.com/@Jannik323) |
| `Snímek XXX` | 001-300 | Camera | Czech. [@Jannik323](https://youtube.com/@Jannik323) |
| `DIGI0XXX` | 001-300 | Camera | [@Mackhill8851](https://youtube.com/@Mackhill8851) |
| `ASF 0XXX` | 001-300 | Camera | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `IONX0XXX` | 001-250 | Camera | [@Mackhill8851](https://youtube.com/@Mackhill8851) |
| `VICO0XXX` | 001-250 | Dashcam | [@Mackhill8851](https://youtube.com/@Mackhill8851) |
| `ArcSoft VideoXXX` | 1-249 | Camera | [@KappenKonundrum](https://x.com/KappenKonundrum) |
| `PRMS0XXX` | 001-200 | Trail Cam | [@Chloe.in.mae](https://instagram.com/chloe.in.mae) |
| `SMOV0XXX` | 001-200 | Camera | [@Mackhill8851](https://youtube.com/@Mackhill8851) |
| `RCA 0XXX` | 001-200 | Camera | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `MOVA0XXX` | 001-200 | Camera | [@Mackhill8851](https://youtube.com/@Mackhill8851) |
| `"Sequence XXX"` | 001-200 | Video Editor | |
| `WideoXXX` | 000-199 | Camera | [@EvilyArised](https://youtube.com/@EvilyArised) |
| `MAX 0XXX` | 001-150 | Drone | [@UsuallyLime](https://youtube.com/@UsuallyLime) |
| `MDGC0XXX` | 001-150 | Trail Cam | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `PCDV0XXX` | 001-150 | Camera | [@Ron2600_](https://youtube.com/@Ron2600_) |
| `HD0 0XXX` | 000-120 | Camera | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `"Filmato 0XXX"` | 001-120 | Misc | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `LOOP0XXX` | 001-100 | Action Cam | [@Mackhill8851](https://youtube.com/@Mackhill8851) |
| `SMDC0XXX` | 001-100 | Camera | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `HUNT0XXX` | 001-100 | Trail Cam | [@Harrisonmoss1310](https://youtube.com/@Harrisonmoss1310) |
| `ACXS0XXX` | 001-100 | Action Cam | [@saso1901](https://youtube.com/@saso1901) |
| `MVC XXXV` | 001-100 | Camera | [@Evanlee1](https://instagram.com/evanlee1) |
| `MA0 00XX` | 00-99 | Camera | Japan |
| `MMF00XX` | 00-99 | Camera | [@CharlesMontgomeryBurns.](https://youtube.com/@CharlesMontgomeryBurns.) |
| `G01000XX` | 10-99 | GoPro | |
| `"Kazam Screencast 000XX"` | 01-50 | Screen Recorder | [@СтаниславШолтанюк](https://youtube.com/@%D0%A1%D1%82%D0%B0%D0%BD%D0%B8%D1%81%D0%BB%D0%B0%D0%B2%D0%A8%D0%BE%D0%BB%D1%82%D0%B0%D0%BD%D1%8E%D0%BA) |
| `CADDX0000XX` | 01-50 | Drone | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `ZOE 00XX` | 01-50 | Camera | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `101 XXXX` | 0001-6500 | Camera | |
| `VIDXXXX` | 0000-5000 | Camera | [@isaiah658](https://youtube.com/@isaiah658) |
| `"PIC XXXX"` | 0001-4000 | Camera | [@Michael_Unce](https://youtube.com/@Michael_Unce) |
| `102 XXXX` | 0001-4000 | Camera | [@OliveGreen-z9h](https://youtube.com/@OliveGreen-z9h) |
| `S500XXXX` | 0001-3000 | Camera | [@AymonAdren](https://youtube.com/@AymonAdren) |
| `Picture XXXX` | 0001-3000 | Camera | |
| `VídeoXXXX` | 0001-2000 | Camera | Brazil/Portugal. [@AymonAdren](https://youtube.com/@AymonAdren) |
| `照片 XXX` | 001-1500 | Camera | China. [@AymonAdren](https://youtube.com/@AymonAdren) |
| `SNC0XXXX` | 0001-1250 | Camera | |
| `XXXX.mpeg` | 0001-1000 | Camera | |
| `MOVXXX` | 000-999 | Camera | Hex variants too, e.g. `MOV42A` |
| `Photo XXX` | 001-900 | Camera | [@berry_xi_](https://youtube.com/@berry_xi_) |
| `NORM0XXX` | 000-500 | Action Cam | [@faizrisky8](https://youtube.com/@faizrisky8) |
| `"Obraz XXX"` | 001-500 | Camera | Poland. [@blackshock116](https://youtube.com/@blackshock116) |
| `MPEG0XXX` | 001-500 | Camera | |
| `Film0XXX` | 001-300 | Camera | Poland. [@blackshock116](https://youtube.com/@blackshock116) |
| `DV000XXX` | 001-300 | Camera | [@Piggypiggyyoinkyoink](https://youtube.com/@Piggypiggyyoinkyoink) |
| `YDTL0XXX` | 001-300 | Time-lapse | [@isaiah658](https://youtube.com/@isaiah658) |
| `FOTO0XXX` | 001-250 | Camera | [@MagoLuiz56000](https://youtube.com/@MagoLuiz56000) |
| `"Фильм 0XXX"` | 001-250 | Misc | Russia. [@arteam63](https://youtube.com/@arteam63) |
| `MovieXXX` | 001-200 | Game Capture | The Sims |
| `DCFC0XXX` | 001-199 | Camera | [@omfgcake](https://youtube.com/@omfgcake) |
| `"วิดีโอ0XXX"` | 000-140 | Camera | Thailand. [@AymonAdren](https://youtube.com/@AymonAdren) |
| `AK000XXX` | 001-100 | Camera | [@Pagenonfound](https://youtube.com/@Pagenonfound) |
| `EMER0XXX` | 001-100 | Dashcam | [@mattie7856](https://youtube.com/@mattie7856) |
| `ATNX0XXX` | 001-100 | Hunting Camera | [@magaz](https://youtube.com/@magaz) |
| `NORMAL000XX` | 00-99 | Camera | [@VoidGear-sh2](https://youtube.com/@VoidGear-sh2) |
| `Eco 000XX` | 01-99 | Camera | PlayStation Eye. [@parascryptor](https://youtube.com/@parascryptor) |
| `TLC000XX` | 01-80 | Time-lapse Camera | [@Samfromonline](https://youtube.com/@Samfromonline) |
| `L00000XX` | 01-60 | Camera | [@magaz](https://youtube.com/@magaz) |
| `Videoklip 00XX` | 01-50 | Camera | Hungary. [@Partyzan_Pmp](https://youtube.com/@Partyzan_Pmp) |
| `EKEN00XX` | 01-50 | Action Cam | |
| `"TVideo_000XX"` | 01-50 | Webcam | [@fujifilms5800](https://youtube.com/@fujifilms5800) |
| `DV000XX` | 01-30 | Camera | [@plug1707](https://youtube.com/@plug1707) |
| `CH000000000000XX` | 01-16 | Security Camera | DVR channel dumps |

### Game-Capture IDs (console DVR exports)

Fixed capture IDs from EA Sports-era console game DVRs — search them verbatim.

| Keyphrase | Game |
|:----------|:-----|
| `501A0001` | NHL |
| `NHL14XBX` | NHL 14 |
| `771A0001` | UFC |
| `741A0001` | FIFA 10 |
| `632A0001` | FIFA 11 |
| `491A0001` | FIFA 12 |
| `521A0001` | Madden 11 |
| `NCA14XBX` | NCAA Football 14 |

### Multi-Variable Patterns (manual substitution required)

These need two values to construct a search and aren't auto-loaded into the spinner — they're listed here for human reference and manual searching. Substitute the X-blocks yourself in YouTube's search bar.

> **Note for tool maintainers:** these intentionally use bullets, not table rows, because the spinner's parser would otherwise pick up the first variable block and produce a half-substituted search string.

- **P1XX0XXX** — variable 1: `01–35`, variable 2: `001–999` — Camera
- **PAXX0XXX** — variable 1: `00–30`, variable 2: `001–499` — Camera
- **PBXX0XXX** — variable 1: `00–30`, variable 2: `001–499` — Camera
- **VXX0XXX** — variable 1: `00–50`, variable 2: `101–300` — Camera — [@AymonAdren](https://x.com/AdrenAymon)
- **PCXX00XX** — variable 1: `00–30`, variable 2: `01–99` — Camera — [@Mackhill8851](https://youtube.com/@Mackhill8851)
- **"Sequence XX X"** — variable 1: `01–99`, variable 2: `1–3` — Video Editor
- **"My Project X"** — single variable: `0–50` — Video Editor — [@Coletale](https://youtube.com/@Coletale)
- **"Il mio filmato X"** — single variable: `1–100` — Misc (Italy)
- **10X XXXX** — variable 1: `3–9`, variable 2: `0001–2000` — Camera
- **L10X0XXX** — variable 1: `0–9`, variable 2: `001–120` — Camera — [@magaz](https://youtube.com/@magaz)
- **MOVXXX.MOD** — variable 1: `0–9`, variable 2: `00–99` / `AA–FF` (e.g. `MOV4AA.MOD`) — Camera
- **SXXX00XX** — variable 1: `1–8`, variable 2: `00–99`, variable 3: `01–99` (e.g. `S1230011`) — Camera — [@fatalreligion](https://youtube.com/@fatalreligion)
- **"X.mpg"** — single variable: `1–1000` — Misc — [@AymonAdren](https://youtube.com/@AymonAdren)
- **(X).mpg** — single variable: `1–500` — Camera — [@yura32tv](https://youtube.com/@yura32tv)
- **"Produce X"** — single variable: `1–300` — Misc — [@RikkityRikkus](https://youtube.com/@RikkityRikkus)
- **"Screencast X"** — single variable: `1–200` — Screen Recorder — [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke)
- **"Untitled Project X"** — single variable: `1–150` — Misc — [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke)
- **"X.webm"** — single variable: `0–100` — Misc — [@NImportant4u](https://youtube.com/@NImportant4u)
- **"My Video HD X"** — single variable: `1–100` — Video Editor — [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke)
- **(X).m2ts** — single variable: `1–100` — Camera — [@yura32tv](https://youtube.com/@yura32tv)
- **X.rmvb** — single variable: `1–100` — Misc — [@NImportant4u](https://youtube.com/@NImportant4u)
- **X.divx** — single variable: `1–100` — Misc — [@NImportant4u](https://youtube.com/@NImportant4u)
- **"X.ogv"** — single variable: `0–50` — Misc — [@NImportant4u](https://youtube.com/@NImportant4u)
- **TITLE01 X** — single variable: `1–50` — DVD — [@lezyv3104](https://youtube.com/@lezyv3104)
- **"(X).mkv"** — single variable: `1–45` — Misc (YouTube intros) — [@alephnullify](https://youtube.com/@alephnullify)
- **XVR CHX** — single variable: `1–30` — Security Camera — [@funni_man23](https://youtube.com/@funni_man23)
- **"X FLV VIDEO"** — single variable: `0–9` — Game Capture

---

## Date-Based Formats

> Formats that include a date in the filename. Use `Before:(Year)` to narrow results.

| Keyphrase | Years Active | Source | Credit |
|:----------|:-------------|:-------|:-------|
| `Screencast YYYY-MM-DD` | >2020 | Screen Recorder | ChromeOS / GNOME. [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `PANO_YYYYMMDD` | >2015 | Smartphone | Android panoramic video. [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `vlc-record-YYYY-MM-DD` | >2008 | Misc | VLC media player. [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `Video YYYYMMDD` | >2012 | Misc | |
| `VID YYYYMMDD` | >2008 | Misc | |
| `WIN YYYYMMDD` | >2013 | Webcam | |
| `Capture YYYYMMDD` | >2008 (<2018) | Webcam | [@thevoid6756](https://youtube.com/@thevoid6756) |
| `InShot YYYYMMDD` | >2016 | App | |
| `PXL YYYYMMDD` | >2020 | Smartphone | |
| `WhatsApp Video YYYY MM DD` | >2015 | App | |
| `Desktop YYYY MM DD` | - | Game Capture | |
| `WP YYYYMMDD` | >2011 (<2018) | Misc | |
| `KakaoTalk Video YYYY MM` | >2012 | Misc | |
| `"QuickCapture Video - Month D, YYYY"` | 2007-2013 | Webcam | [@Pagenonfound](https://youtube.com/@Pagenonfound) |
| `Webcam YYYYMMDD` | 2007-2010 | Webcam | [@GaspacoZanis](https://youtube.com/@GaspacoZanis) |
| `Screen Recording YYYY MM DD` | >2012 | Screen Recorder | [@Qrde](https://youtube.com/@Qrde) |
| `Bandicam YYYY MM DD` | >2010 | Screen Recorder | [@Thatoneguy59-x9l](https://youtube.com/@Thatoneguy59-x9l) |
| `Javaw YYYY MM DD` | >2009 | Game Capture | [@Mort3534](https://youtube.com/@Mort3534) |
| `Grand Theft Auto 5 YYYY MM DD` | >2008 | Game Capture (GTA V) | [@Laxesthecorgi9824](https://youtube.com/@Laxesthecorgi9824) |
| `YouCut YYYYMMDD` | >May 2018 | Video Editor | |
| `XRecorder YYYYMMDD` | >2024 | Screen Recorder | [@Dayve8977](https://youtube.com/@Dayve8977) |
| `AUD-YYYYMMDD` | >2017 | Misc | |
| `GMTYYYYMMDD` | - | Zoom | [@zxz41_Kristian](https://x.com/zxz41_Kristian) |
| `Webcam Recorded Video - Month D, YYYY` | 2008-2010 | Webcam | |
| `Webcam video Month D, YYYY` | 2010-2012 | Webcam | |
| `Webcam video from Month D, YYYY` | 2011-2016 | Webcam | [@flizzycat](https://youtube.com/@flizzycat) |
| `SCR YYYYMMDD` | 2014-2018 | Screen Recorder | [@GaspacoZanis](https://youtube.com/@GaspacoZanis) |
| `Flipagram Month YYYY` | 2013-2019 | Video Editor | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `Iw3mp YYYYMMDD` | 2008-2020 | Game Capture (COD 4) | [@Zeebdy](https://youtube.com/@Zeebdy) |
| `"AR.Drone 2.0 Video: YYYY"` | 2015-2021 | Drone | [@Whenwhowhathow](https://x.com/whenwhowhathow) |
| `WA VID YYYYMMDD` | 2018-2023 | App | [@Hrotmaister](https://x.com/Hrotmaister) |
| `XRecorder DDMMYYYY` | 2021-2024 | Screen Recorder | [@Dayve8977](https://youtube.com/@Dayve8977) |
| `CODWAWMP YYYY MM DD` | 2008-2023 | Game Capture (COD WAW) | [@Zeebdy](https://youtube.com/@Zeebdy) |
| `Hl2 YYYY MM DD` | 2008-2023 | Game Capture (Half-Life) | [@Zeebdy](https://youtube.com/@Zeebdy) |
| `Chrome YYYY MM DD` | >2010 | Screen Recorder | [@Lemonposting](https://youtube.com/@Lemonposting) |
| `Simplescreenrecorder YYYY MM DD` | >2023 | Screen Recorder | [@RadieForge](https://youtube.com/@RadieForge) |
| `720p YYMMDD` | >2023 | VYond / GoAnimate | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) |
| `"Project of DD Mth 2011 PDT"` | 2011 | Video Editor | [@Machine___angel](https://x.com/machine___angel) |
| `RobloxApp YYYYMMDD` | >2009 | Game Capture (Roblox) | [@mingau993rj](https://youtube.com/@mingau993rj) |
| `RobloxApp YYYY MM DD` | >2009 | Game Capture (Roblox) | [@mingau993rj](https://youtube.com/@mingau993rj) |
| `VLC Record YYYY MM DD` | >2010 | Misc | [@user-hv8pk9kp6h](https://youtube.com/@user-hv8pk9kp6h) |
| `Vlcsnap YYYY` | >2010 (<2023) | Misc | [@roamingbovine](https://youtube.com/@roamingbovine) |
| `mobizen YYYYMMDD` | >2014 | Screen Recorder | [@qrde](https://youtube.com/@qrde) |
| `obs YYYY-MM-DD` | >2018 | Screen Recorder (OBS) | [@olus_owo_uwu](https://youtube.com/@olus_owo_uwu) |
| `Videoshop YYYY MM` | >2019 | Camera | [@roamingbovine](https://youtube.com/@roamingbovine) |

### Manual date patterns (not auto-loaded)

These use date orders or localized date words the spinner can't auto-substitute — construct the search yourself.

- **VDD MM YY** / **VDDMMYY** — `V` + 2-digit day/month/year, `2008–2017` — Camera
- **YYYY년 M월 D일** — South Korean date titles, `>2010` — [@crashbender6490](https://youtube.com/@crashbender6490)
- **YYYY年M月D日** — Japanese date titles, `>2010` — [@crashbender6490](https://youtube.com/@crashbender6490)
- **ScreenRecording MM DD YYYY** — `>2017` — Screen Recorder — [@mentallystablegaming](https://youtube.com/@mentallystablegaming)
- **"My Movie (MM DD, 2013)"** — Camera — [@AymonAdren](https://youtube.com/@AymonAdren)

---

## Ancient YouTube (2006-2008)

> **Sort by:** View Count (Optional)
> **Search Tools:** `Before:(Year)` e.g. `Before:2008`, Quotations `" "`

The deepest layer of the Recycle Bin. These keyphrases surface videos from the first years of YouTube — many with zero views since upload. Finding anything here from 2005-2006 is **SUPER RARE**.

| Keyphrase | Source | Credit |
|:----------|:-------|:-------|
| `"Qik"` | App | Qik mobile video (2008-2011). [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `"Made with One True Media"` | Video Editor | Online creator (2005-2014). [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `"Jing"` | Screen Recorder | TechSmith Jing (2007-2013). [@Chegnus](https://youtube.com/@BASHnBRASS) |
| `"You have new picture mail! (video)"` | Phone | |
| `"Media1.3gp"` | Phone | |
| `"Media1.3g2"` | Phone | |
| `"Video.3g2"` | Misc | |
| `"New Multimedia Message"` | Phone | |
| `"Multimedia Message"` | Phone | |
| `"Video from my phone"` | Phone | |
| `"Video uploaded from my mobile phone"` | Phone | |
| `"For Month DD, YYYY"` | Phone | |
| `"Recorded on Month DD, YYYY using a Flip Video Camcorder"` | Camera | [@Hassan-zw9tb](https://youtube.com/@Hassan-zw9tb) |
| `Video0XX` (00-10) | Camera | |
| `Vid0XX` (00-10) | Camera | |
| `MOV000XX` (00-10) | Camera | |
| `"Recorded on Month DD, YYYY using a Flip Video Camera"` | Camera | |
| `"Created on Month DD, YYYY using FlipShare"` | Camera | |
| `muuvee00XX` (00-40) | Video Editor | [@GaspacoZanis](https://youtube.com/@GaspacoZanis) |
| `0_VIDEO_0XX` (01-54) | Phone | [@GaspacoZanis](https://youtube.com/@GaspacoZanis) |
| `"You have received a new message"` | Phone | [@i664k](https://youtube.com/@i664k) |
| `"My Great Movie"` | Video Editor | [@Chernyat5048](https://youtube.com/@Chernyat5048) |
| `"My First Project"` | Video Editor | |
| `"Video van Mijn telefoon"` | Phone (Netherlands) | |
| `"Vídeo desde mi teléfono"` | Phone (Spanish) | |
| `"vídeo subido desde mi teléfono móvil"` | Phone (Spanish) | |
| `"video geüpload van mijn mobiel"` | Phone (Netherlands) | |
| `"I created this video with the YouTube Slideshow Creator"` | Video Editor | |
| `"I created this video with the YouTube Video Editor"` | Video Editor | [@Infinitysnapz](https://youtube.com/@Infinitysnapz) |
| `"Sent from my blackberry smartphone"` | Phone | [@Infinitysnapz](https://youtube.com/@Infinitysnapz) |
| `"Video from Tweetcaster"` | App | [@UsuallyLime](https://youtube.com/@UsuallyLime) |
| `"My Ezvid Video"` | Screen Recorder | [@UsuallyLime](https://youtube.com/@UsuallyLime) |
| `"This video was uploaded from an Android phone"` | Phone | [@UsuallyLime](https://youtube.com/@UsuallyLime) |
| `"Sprint PictureMail"` | Phone | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) |
| `"My stop motion movie"` | Video Editor | [@Huebirdfan2.0](https://youtube.com/@Huebirdfan2.0) |
| `"Stop motion.avi"` | Stop Motion | [@Evanlee1](https://youtube.com/@Evanlee1) |
| `"Dvgrab"` | Camera | [@BastienSante1902](https://youtube.com/@BastienSante1902) |
| `"XiaoYing video"` | Misc | [@Hrotmaister](https://youtube.com/@Hrotmaister) |
| `"Temp video for share"` | Drone | [@PianoScoreVids](https://youtube.com/@PianoScoreVids) |
| `"Cliquez pour ajouter un titre…"` | Misc | France — placeholder title |
| `"Click here to change title"` | Camera | |
| `/tmp/upload/ before:2009` | File Path | Server-side upload path |
| `=?utf-8?b before:2009` | File Path | MIME-encoded MMS subject lines |
| `=?utf-8?q before:2009` | File Path | MIME-encoded MMS subject lines |
| `=?iso-8859-1?Q? before:2009` | File Path | MIME-encoded MMS subject lines |
| `"You have a PXT from"` | Phone | NZ/AU picture messages. [@forwardmomentumn](https://youtube.com/@forwardmomentumn) |
| `"C:\Documents and Settings"` | File Path | Windows XP path. [@rustyketchup8015](https://youtube.com/@rustyketchup8015) |

---

> See also: **[Solved Mysteries](SOLVED_MYSTERIES.md)** — explained encounters like Webdriver Torso, Better Bandai, and other cryptic channels

---

## Contributors

> Thank you to everyone who helped discover new format leads. This list grows because of you.

[@Junoeclipse7715](https://youtube.com/@Junoeclipse7715) | [@ZuperDarkk](https://youtube.com/@ZuperDarkk) | [@zxz41_Kristian](https://youtube.com/@zxz41_Kristian) | [@TheLimeyDragon](https://youtube.com/@TheLimeyDragon) | [@nellip.683](https://youtube.com/@nellip.683) | [@Hassan-zw9tb](https://youtube.com/@Hassan-zw9tb) | [@Oopse47](https://youtube.com/@Oopse47) | [@slurrygeyser8133](https://youtube.com/@slurrygeyser8133) | [@denzelkrocker1673](https://youtube.com/@denzelkrocker1673) | [@Set_Your_Handle10](https://youtube.com/@Set_Your_Handle10) | [@StormSplurge](https://youtube.com/@StormSplurge) | [@CharlesMontgomeryBurns.](https://youtube.com/@CharlesMontgomeryBurns.) | [@kyle6266](https://youtube.com/@kyle6266) | [@czechgop7631](https://youtube.com/@czechgop7631) | [@KILOPOWER](https://youtube.com/@KILOPOWER) | [@T1MAGEDDON](https://youtube.com/@T1MAGEDDON) | [@stickmandaninacan](https://youtube.com/@stickmandaninacan) | [@blissom](https://youtube.com/@blissom) | [@thevoid6756](https://youtube.com/@thevoid6756) | [@Jannik323](https://youtube.com/@Jannik323) | [@Coletale](https://youtube.com/@Coletale) | [@Laxesthecorgi9824](https://youtube.com/@Laxesthecorgi9824) | [@Infinitysnapz](https://youtube.com/@Infinitysnapz) | [@AymonAdren](https://youtube.com/@AymonAdren) | [@misterherman](https://youtube.com/@misterherman) | [@Fraigo](https://youtube.com/@Fraigo) | [@UsuallyLime](https://youtube.com/@UsuallyLime) | [@Thatoneguy59-x9l](https://youtube.com/@Thatoneguy59-x9l) | [@Chernyat5048](https://youtube.com/@Chernyat5048) | [@BladeOscReal](https://youtube.com/@BladeOscReal) | [@sScorpioNn1](https://youtube.com/@sScorpioNn1) | [@H2knad](https://youtube.com/@H2knad) | [@Lorenzorentniop717](https://youtube.com/@Lorenzorentniop717) | [@Mort3534](https://youtube.com/@Mort3534) | [@_Mag10_](https://youtube.com/@_Mag10_) | [@EvilyArised](https://youtube.com/@EvilyArised) | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) | [@i664k](https://youtube.com/@i664k) | [@Piggypiggyyoinkyoink](https://youtube.com/@Piggypiggyyoinkyoink) | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) | [@Pagenonfound](https://youtube.com/@Pagenonfound) | [@flizzycat](https://youtube.com/@flizzycat) | [@PianoScoreVids](https://youtube.com/@PianoScoreVids) | [@Ron2600_](https://youtube.com/@Ron2600_) | [@Huebirdfan2.0](https://youtube.com/@Huebirdfan2.0) | [@Hrotmaister](https://youtube.com/@Hrotmaister) | [@Harrisonmoss1310](https://youtube.com/@Harrisonmoss1310) | [@Dayve8977](https://youtube.com/@Dayve8977) | [@Zeebdy](https://youtube.com/@Zeebdy) | [@Lemonposting](https://youtube.com/@Lemonposting) | [@Dontzky](https://youtube.com/@Dontzky) | [@Alexanderhunt9263](https://youtube.com/@Alexanderhunt9263) | [@Techyarchivuma](https://youtube.com/@Techyarchivuma) | [@Mackhill8851](https://youtube.com/@Mackhill8851) | [@A0V1](https://youtube.com/@A0V1) | [@PrimeroAtreides](https://youtube.com/@PrimeroAtreides) | [@YeoungBraxx](https://youtube.com/@YeoungBraxx) | [@BastienSante1902](https://youtube.com/@BastienSante1902) | [@RadieForge](https://youtube.com/@RadieForge) | [@GaspacoZanis](https://youtube.com/@GaspacoZanis) | [@Qrde](https://youtube.com/@Qrde) | [@saso1901](https://youtube.com/@saso1901) | [@__atob__](https://youtube.com/@__atob__) | [@Whenwhowhathow](https://youtube.com/@Whenwhowhathow) | [@Machine___angel](https://youtube.com/@Machine___angel) | [@KappenKonundrum](https://youtube.com/@KappenKonundrum) | [@Chloe.in.mae](https://youtube.com/@Chloe.in.mae) | [@Evanlee1](https://youtube.com/@Evanlee1) | [@Daldosbm](https://youtube.com/@Daldosbm) | [@PnfrmEnm](https://youtube.com/@PnfrmEnm) | [@СтаниславШолтанюк](https://youtube.com/@%D0%A1%D1%82%D0%B0%D0%BD%D0%B8%D1%81%D0%BB%D0%B0%D0%B2%D0%A8%D0%BE%D0%BB%D1%82%D0%B0%D0%BD%D1%8E%D0%BA) | [@vvvvvvvvvvvvvvv](https://youtube.com/@vvvvvvvvvvvvvvv) | [@Paper_Frogg](https://youtube.com/@Paper_Frogg) | [@mentallystablegaming](https://youtube.com/@mentallystablegaming) | [@user-yh1dn4nk1r](https://youtube.com/@user-yh1dn4nk1r) | [@isaiah658](https://youtube.com/@isaiah658) | [@Michael_Unce](https://youtube.com/@Michael_Unce) | [@OliveGreen-z9h](https://youtube.com/@OliveGreen-z9h) | [@berry_xi_](https://youtube.com/@berry_xi_) | [@faizrisky8](https://youtube.com/@faizrisky8) | [@blackshock116](https://youtube.com/@blackshock116) | [@yura32tv](https://youtube.com/@yura32tv) | [@RikkityRikkus](https://youtube.com/@RikkityRikkus) | [@MagoLuiz56000](https://youtube.com/@MagoLuiz56000) | [@arteam63](https://youtube.com/@arteam63) | [@omfgcake](https://youtube.com/@omfgcake) | [@NImportant4u](https://youtube.com/@NImportant4u) | [@mattie7856](https://youtube.com/@mattie7856) | [@magaz](https://youtube.com/@magaz) | [@fatalreligion](https://youtube.com/@fatalreligion) | [@VoidGear-sh2](https://youtube.com/@VoidGear-sh2) | [@parascryptor](https://youtube.com/@parascryptor) | [@Samfromonline](https://youtube.com/@Samfromonline) | [@Partyzan_Pmp](https://youtube.com/@Partyzan_Pmp) | [@fujifilms5800](https://youtube.com/@fujifilms5800) | [@alephnullify](https://youtube.com/@alephnullify) | [@funni_man23](https://youtube.com/@funni_man23) | [@plug1707](https://youtube.com/@plug1707) | [@lezyv3104](https://youtube.com/@lezyv3104) | [@coolmancool63](https://youtube.com/@coolmancool63) | [@cchhey3812](https://youtube.com/@cchhey3812) | [@typeone1704](https://youtube.com/@typeone1704) | [@reverseflesh](https://youtube.com/@reverseflesh) | [@roamingbovine](https://youtube.com/@roamingbovine) | [@ethanr_5](https://youtube.com/@ethanr_5) | [@charlescatyt](https://youtube.com/@charlescatyt) | [@ravioliboy3759](https://youtube.com/@ravioliboy3759) | [@youtubersingingmoments4402](https://youtube.com/@youtubersingingmoments4402) | [@lawnside82](https://youtube.com/@lawnside82) | [@thebilabialtrill](https://youtube.com/@thebilabialtrill) | [@xfdhcdjxfhjjtgj](https://youtube.com/@xfdhcdjxfhjjtgj) | [@GPLeast](https://youtube.com/@GPLeast) | [@chipseed](https://youtube.com/@chipseed) | [@mazurthc](https://youtube.com/@mazurthc) | [@diberhaze](https://youtube.com/@diberhaze) | [@TrashonicLizard](https://youtube.com/@TrashonicLizard) | [@SJursa-ey4tt](https://youtube.com/@SJursa-ey4tt) | [@MilkyBloomet](https://youtube.com/@MilkyBloomet) | [@phoenixkh93](https://youtube.com/@phoenixkh93) | [@grobokop2357](https://youtube.com/@grobokop2357) | [@machine.angel.777](https://youtube.com/@machine.angel.777) | [@urmom694-X](https://youtube.com/@urmom694-X) | [@h8erssss](https://youtube.com/@h8erssss) | [@whosjozikolnik](https://youtube.com/@whosjozikolnik) | [@volevv_](https://youtube.com/@volevv_) | [@nerks5135](https://youtube.com/@nerks5135) | [@user-hv8pk9kp6h](https://youtube.com/@user-hv8pk9kp6h) | [@JosephVM2](https://youtube.com/@JosephVM2) | [@Ancend](https://youtube.com/@Ancend) | [@martijn9560](https://youtube.com/@martijn9560) | [@crashbender6490](https://youtube.com/@crashbender6490) | [@forwardmomentumn](https://youtube.com/@forwardmomentumn) | [@rustyketchup8015](https://youtube.com/@rustyketchup8015) | [@mingau993rj](https://youtube.com/@mingau993rj) | [@olus_owo_uwu](https://youtube.com/@olus_owo_uwu) | [@Chegnus](https://youtube.com/@BASHnBRASS)

---

<p align="center">
  <sub>Maintained by <a href="https://youtube.com/@KVNAUST">KVN AUST</a> &amp; the community | Tool by <a href="https://x.com/Chegnus">@Chegnus</a> / <a href="https://falcontechnix.com">FalconTechnix</a> | <a href="https://github.com/sworrl/KVN_AUST">GitHub</a> | <a href="https://kvnaust.falcontechnix.com/">Play</a></sub>
</p>

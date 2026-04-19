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
  <a href="https://falcontechnix.com/KVN_AUST/"><img src="https://img.shields.io/badge/PLAY_NOW-falcontechnix.com-e74c3c?style=for-the-badge" alt="Play Now"></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/TOTAL_FORMATS-192-e74c3c?style=flat-square&labelColor=1a1a2e" alt="192 Total Formats">
  <img src="https://img.shields.io/badge/Search_Keyphrases-43-3498db?style=flat-square&labelColor=1a1a2e" alt="43 Search Keyphrases">
  <img src="https://img.shields.io/badge/File_Extensions-13-9b59b6?style=flat-square&labelColor=1a1a2e" alt="13 File Extensions">
  <img src="https://img.shields.io/badge/Numbered_Formats-78-2ecc71?style=flat-square&labelColor=1a1a2e" alt="78 Numbered Formats">
  <img src="https://img.shields.io/badge/Date--Based-21-e67e22?style=flat-square&labelColor=1a1a2e" alt="21 Date-Based Formats">
  <img src="https://img.shields.io/badge/Ancient_YouTube-37-f39c12?style=flat-square&labelColor=1a1a2e" alt="37 Ancient YouTube Formats">
</p>

> **Note from KVN AUST:** WORKING ON A FIX FOR SORTING BY UPLOAD DATE

---

YouTube currently hosts over **20 billion videos**. **93%** have under 1,000 views. **30%** have under 100. This map helps you access the billions of forgotten, zero-view uploads by searching for **default device filenames** that the algorithm never learned to recommend.

The only way to access these videos is to search for the **keyphrase** associated with the device or application used to record them. These are usually the default filenames given to recorded or downloaded videos.

> **For contributors:** The [Recycle Bin tool](https://falcontechnix.com/KVN_AUST/) parses this file to populate its format spinner. To ensure new numbered formats are picked up, they **must** follow this exact table format:
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
| `YDXJXXXX` | 0001-2000 | Action Cam | [@saso1901](https://youtube.com/@saso1901) |
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
| `4XXX` | AAA-FFF, 000-999 | Phone | |
| `Trim 4XXX` | AAA-FFF, 000-999 | Phone | |
| `"Axon Body * Video"` | - | Body Cam | |
| `"Axon Flex Video"` | - | Body Cam | |
| `"Month DD, YYYY"` | - | Phone | |
| `AVSEQXX` | 00-99 | Misc | [@Set_Your_Handle10](https://youtube.com/@Set_Your_Handle10) |
| `"My Videolicious Video"` | - | Video Editor | [@slurrygeyser8133](https://youtube.com/@slurrygeyser8133) |

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
| `"Vdeo desde mi telfono"` | Phone (Spanish) | |
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

---

## Solved Mysteries

### "Better Bandai" / Webdriver Torso-Style Channels

You may encounter channels uploading hundreds or thousands of short videos consisting of **colored rectangles changing size and position** with **high-pitched beeping tones**. Examples include channels like "Better Bandai" and the infamous "Webdriver Torso."

Despite their eerie, cryptic appearance, **these are not** C2 (Command & Control) communications, ARGs, or secret number stations.

**What they actually are:** Automated test videos created by YouTube/Google to continuously monitor the platform's video uploading, encoding, and compression infrastructure.

- **Why boxes and beeps?** Simple visual patterns (solid colored rectangles) and audio tones are specifically designed to be easy for software to analyze. YouTube's backend compares the uploaded output to the original source file to measure quality loss during compression and detect audio desync.
- **The titles** (e.g. `gcs-pkg-20200105-032036-742513`) are automated system log IDs and timestamps. "GCS" stands for Google Cloud Storage, part of the infrastructure used to host and process these files.
- **The volume** is intentional — YouTube uploads hundreds of thousands of these test videos across multiple bot channels to monitor performance at scale.

> While the sheer volume and bizarre nature of these videos have sparked many conspiracy theories over the years, they are just behind-the-scenes engineering tools used to ensure the platform is functioning correctly.

---

## Contributors

> Thank you to everyone who helped discover new format leads. This list grows because of you.

[@Junoeclipse7715](https://youtube.com/@Junoeclipse7715) | [@ZuperDarkk](https://youtube.com/@ZuperDarkk) | [@zxz41_Kristian](https://youtube.com/@zxz41_Kristian) | [@TheLimeyDragon](https://youtube.com/@TheLimeyDragon) | [@nellip.683](https://youtube.com/@nellip.683) | [@Hassan-zw9tb](https://youtube.com/@Hassan-zw9tb) | [@Oopse47](https://youtube.com/@Oopse47) | [@slurrygeyser8133](https://youtube.com/@slurrygeyser8133) | [@denzelkrocker1673](https://youtube.com/@denzelkrocker1673) | [@Set_Your_Handle10](https://youtube.com/@Set_Your_Handle10) | [@StormSplurge](https://youtube.com/@StormSplurge) | [@CharlesMontgomeryBurns.](https://youtube.com/@CharlesMontgomeryBurns.) | [@kyle6266](https://youtube.com/@kyle6266) | [@czechgop7631](https://youtube.com/@czechgop7631) | [@KILOPOWER](https://youtube.com/@KILOPOWER) | [@T1MAGEDDON](https://youtube.com/@T1MAGEDDON) | [@stickmandaninacan](https://youtube.com/@stickmandaninacan) | [@blissom](https://youtube.com/@blissom) | [@thevoid6756](https://youtube.com/@thevoid6756) | [@Jannik323](https://youtube.com/@Jannik323) | [@Coletale](https://youtube.com/@Coletale) | [@Laxesthecorgi9824](https://youtube.com/@Laxesthecorgi9824) | [@Infinitysnapz](https://youtube.com/@Infinitysnapz) | [@AymonAdren](https://youtube.com/@AymonAdren) | [@misterherman](https://youtube.com/@misterherman) | [@Fraigo](https://youtube.com/@Fraigo) | [@UsuallyLime](https://youtube.com/@UsuallyLime) | [@Thatoneguy59-x9l](https://youtube.com/@Thatoneguy59-x9l) | [@Chernyat5048](https://youtube.com/@Chernyat5048) | [@BladeOscReal](https://youtube.com/@BladeOscReal) | [@sScorpioNn1](https://youtube.com/@sScorpioNn1) | [@H2knad](https://youtube.com/@H2knad) | [@Lorenzorentniop717](https://youtube.com/@Lorenzorentniop717) | [@Mort3534](https://youtube.com/@Mort3534) | [@_Mag10_](https://youtube.com/@_Mag10_) | [@EvilyArised](https://youtube.com/@EvilyArised) | [@Evanbeckman358](https://youtube.com/@Evanbeckman358) | [@i664k](https://youtube.com/@i664k) | [@Piggypiggyyoinkyoink](https://youtube.com/@Piggypiggyyoinkyoink) | [@AFasterSlowpoke](https://youtube.com/@AFasterSlowpoke) | [@Pagenonfound](https://youtube.com/@Pagenonfound) | [@flizzycat](https://youtube.com/@flizzycat) | [@PianoScoreVids](https://youtube.com/@PianoScoreVids) | [@Ron2600_](https://youtube.com/@Ron2600_) | [@Huebirdfan2.0](https://youtube.com/@Huebirdfan2.0) | [@Hrotmaister](https://youtube.com/@Hrotmaister) | [@Harrisonmoss1310](https://youtube.com/@Harrisonmoss1310) | [@Dayve8977](https://youtube.com/@Dayve8977) | [@Zeebdy](https://youtube.com/@Zeebdy) | [@Lemonposting](https://youtube.com/@Lemonposting) | [@Dontzky](https://youtube.com/@Dontzky) | [@Alexanderhunt9263](https://youtube.com/@Alexanderhunt9263) | [@Techyarchivuma](https://youtube.com/@Techyarchivuma) | [@Mackhill8851](https://youtube.com/@Mackhill8851) | [@A0V1](https://youtube.com/@A0V1) | [@PrimeroAtreides](https://youtube.com/@PrimeroAtreides) | [@YeoungBraxx](https://youtube.com/@YeoungBraxx) | [@BastienSante1902](https://youtube.com/@BastienSante1902) | [@RadieForge](https://youtube.com/@RadieForge) | [@GaspacoZanis](https://youtube.com/@GaspacoZanis) | [@Qrde](https://youtube.com/@Qrde) | [@saso1901](https://youtube.com/@saso1901) | [@__atob__](https://youtube.com/@__atob__) | [@Whenwhowhathow](https://youtube.com/@Whenwhowhathow) | [@Machine___angel](https://youtube.com/@Machine___angel) | [@KappenKonundrum](https://youtube.com/@KappenKonundrum) | [@Chloe.in.mae](https://youtube.com/@Chloe.in.mae) | [@Evanlee1](https://youtube.com/@Evanlee1) | [@Daldosbm](https://youtube.com/@Daldosbm) | [@PnfrmEnm](https://youtube.com/@PnfrmEnm) | [@Chegnus](https://youtube.com/@BASHnBRASS)

---

<p align="center">
  <sub>Maintained by <a href="https://youtube.com/@KVNAUST">KVN AUST</a> &amp; the community | Tool by <a href="https://x.com/Chegnus">@Chegnus</a> / <a href="https://falcontechnix.com">FalconTechnix</a> | <a href="https://github.com/sworrl/KVN_AUST">GitHub</a> | <a href="https://falcontechnix.com/KVN_AUST/">Play</a></sub>
</p>

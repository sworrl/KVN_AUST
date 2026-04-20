<h1 align="center">
  <br>
  YouTube's Recycle Bin
  <br>
  <sub>Solved Mysteries</sub>
  <br>
</h1>

<p align="center">
  <a href="https://www.youtube.com/@KVNAUST"><img src="https://img.shields.io/badge/YouTube-KVN_AUST-red?style=for-the-badge&logo=youtube" alt="YouTube"></a>
  <a href="https://x.com/MingKasterMK"><img src="https://img.shields.io/badge/X-@MingKasterMK-black?style=for-the-badge&logo=x" alt="X/Twitter"></a>
  <a href="https://falcontechnix.com/KVN_AUST/"><img src="https://img.shields.io/badge/PLAY_NOW-falcontechnix.com-e74c3c?style=for-the-badge" alt="Play Now"></a>
</p>

---

When diving into YouTube's Recycle Bin, you'll occasionally encounter channels and videos that seem inexplicable — thousands of identical uploads, cryptic titles, machine-generated content. This document explains the ones the community has figured out.

> Have you found something weird that isn't explained here? Share it in the [KVN AUST Discord](https://www.youtube.com/@KVNAUST) or open an issue on [GitHub](https://github.com/sworrl/KVN_AUST/issues).

---

## "Better Bandai" / Webdriver Torso-Style Channels

You may encounter channels uploading hundreds or thousands of short videos consisting of **colored rectangles changing size and position** with **high-pitched beeping tones**. Examples include channels like "Better Bandai" and the infamous "Webdriver Torso."

Despite their eerie, cryptic appearance, **these are not** C2 (Command & Control) communications, ARGs, or secret number stations.

**What they actually are:** Automated test videos created by YouTube/Google to continuously monitor the platform's video uploading, encoding, and compression infrastructure.

### Why boxes and beeps?

Simple visual patterns (solid colored rectangles) and audio tones are specifically designed to be easy for software to analyze. YouTube's backend compares the uploaded output to the original source file to measure quality loss during compression and detect audio desync.

### The titles

Titles like `gcs-pkg-20200105-032036-742513` are automated system log IDs and timestamps. "GCS" stands for Google Cloud Storage, part of the infrastructure used to host and process these files.

### The volume

The sheer number is intentional — YouTube uploads hundreds of thousands of these test videos across multiple bot channels to monitor performance at scale across different regions, codecs, and resolutions.

> While the bizarre nature of these videos has sparked many conspiracy theories over the years, they are just behind-the-scenes engineering tools used to ensure the platform is functioning correctly.

---

*Know of another solved mystery? [Open an issue](https://github.com/sworrl/KVN_AUST/issues) or submit a PR.*

---

<p align="center">
  <sub><a href="https://github.com/sworrl/KVN_AUST">GitHub</a> | <a href="https://falcontechnix.com/KVN_AUST/">Play Now</a> | <a href="FORMAT-MAP.md">Format Map</a> | <a href="CHANGELOG.md">Changelog</a></sub>
</p>

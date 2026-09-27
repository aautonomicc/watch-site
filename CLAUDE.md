# W@tch website (watch-site)
## Description
Public landing site for W@tch, the Autonomi media player. Live at https://aautonomicc.github.io/watch-site/ (GitHub Pages, `main` branch root).
## Tech Stack
Hand-built static HTML/CSS, no framework, no build step. Wordmark font: Anton (self-hosted, SIL OFL).
## Test Commands
None — static site. Visual check: `python3 -m http.server 8377` + browser/playwright screenshot.
## Dev Server (command and port)
`python3 -m http.server 8377` from the repo root → http://localhost:8377/
## Current Status
Landing page + step-by-step install guide live. Deploys automatically on push to `main`.
## Architecture Notes
- `index.html` — landing page (neon glass style, palette from the app's WiTokens: ink #0A0A0A / bone #F5F2EB / accent #42A5F5)
- `install.html` — plain-English install guide, sections in order: Android phone, Windows, Linux, Mac, Android TV
- `apk/index.html` — JS redirect to the latest `.apk` release asset; gives Android TV users the short Downloader address `aautonomicc.github.io/watch-site/apk`
- `style.css` — shared by both pages; install-guide styles at the bottom
- Download buttons on both pages resolve direct per-platform asset URLs from the GitHub releases API at page load (fallback: releases page)
- Install-guide screenshot slots are `display:none` until their image loads (`onload` reveals) — drop real screenshots into `assets/install/` with the filenames listed in `assets/install/README.md` and they appear with no HTML change. None captured yet (need real Android/Windows/Mac/TV devices).
- Facts baked into the guide: Windows zip contains `watchit.exe`; macOS dmg contains `W@tch.app` (unsigned → right-click Open); one universal APK serves both Android phone and TV; Linux AppImage needs the execute bit.
## Recent Changes
- [2026-09-27] Added install.html (step-by-step guide for non-technical users: Android phone / Windows / Linux / Mac / Android TV), apk/ short-URL redirect for TV sideloading (verified it resolves and downloads the latest APK), hidden screenshot slots + assets/install/README.md naming them, Install nav link + guide link on the landing page.
- [2026-09-26] Initial landing page — neon glass style (9b400fd).

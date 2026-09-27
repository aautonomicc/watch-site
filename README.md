# W@tch website

Landing page for [W@tch](https://github.com/aautonomicc/Watch-It) — a peer-to-peer media player for the Autonomi network.

Live at **https://aautonomicc.github.io/watch-site/**

## How it works

Hand-built static site — `index.html` (landing), `install.html` (step-by-step install guide) + shared `style.css`, no framework, no build step. Served by GitHub Pages from the `main` branch root.

- `apk/index.html` is a tiny redirect page: it resolves the latest `.apk` release asset via the GitHub API and starts the download — so Android TV users can type the short address `aautonomicc.github.io/watch-site/apk` into the Downloader app.
- The install guide has hidden screenshot slots per step; drop real screenshots into `assets/install/` (filenames in `assets/install/README.md`) and they appear automatically.

- Download buttons link to the latest GitHub release; a small inline script resolves direct per-platform asset URLs from the GitHub API at page load (falls back to the releases page if the API is unreachable).
- Branding assets are copied from the Watch-It repo (`branding/icon.svg`, `branding/social-preview.png`, `docs/screenshots/*.jpg`).
- The wordmark uses [Anton](https://fonts.google.com/specimen/Anton), self-hosted under the SIL Open Font License (`assets/fonts/Anton-OFL.txt`).
- Screenshots show a sample library; titles and artwork are invented/AI-generated for the screenshots.

## Editing

Edit `index.html` / `style.css` and push to `main` — Pages redeploys automatically.

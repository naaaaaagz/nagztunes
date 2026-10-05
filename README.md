# Nagz Tunes

Source of [music.nagz.space](https://music.nagz.space/), my hobby music page: releases, old tunes, videos, remixes, live jams.

A static single-page site served by GitHub Pages. No build step: everything (HTML, CSS, JS, data) lives in `index.html`.

## Adding a release

All content is defined in data arrays near the top of the `<script>` in `index.html`:

| Array | Tab |
| --- | --- |
| `releases` | Releases. `type` is `"lp"`, `"ep"` or `"single"` and decides the section (a section only appears once it has a release) |
| `oldTunes` | Old Tunes |
| `videos` | Videos |
| `remixes` | Remixes (SoundCloud URLs) |
| `liveJams` | Live Jams |

For a new release:

1. Add an entry to `releases` (newest first): title, year, type, genre, cover, fanlink, optional YouTube video.
2. Put the cover at `cover/<name>.jpg` (500×500) and a WebP copy at `cover/preview/<name>.webp`.
3. Add its streaming links to `serviceLinks`, keyed by the fanlink URL.
4. Add its Apple preview tracks to `previewTracks`, keyed by the Apple Music album ID (the number at the end of the Apple link). Track count and total length are calculated from these.

## Files

- `index.html`: the whole site
- `404.html`: page GitHub Pages shows for unknown URLs
- `cover/`: release artwork (`preview/` holds the WebP versions the page actually loads)
- `CNAME`: custom domain for GitHub Pages
- favicons, `site.webmanifest`, `logo.png`, `me.jpg`: icons and images

# biolink

An extreme-minimalist, monochrome, frosted-glass bio-link page with an
Arch/terminal aesthetic. Single self-contained `index.html` — no build step,
no dependencies, no framework.

## Features

- **True-black OLED** monochrome theme, monospace type.
- **Borderless link tiles** with a cursor-following "light-catch" frosted glow
  and a terminal **decode/scramble** animation on hover.
- **Terminal prompt** header (`sid@arch ~ $`) with a blinking cursor, and an
  animated tab-title spinner (`[-] [\] [|] [/]`).
- **Built-in music player** styled to match the link tiles: playlist support,
  play/pause, prev/next, click-to-seek, auto-advance, and autoplay with a
  browser-safe fallback (starts on first interaction).
- **Muted, looping YouTube background video**, desaturated to stay on-theme.
- Respects `prefers-reduced-motion`.

## Editing

Everything is controlled from the `CONFIG` block at the top of `index.html`:

- `handle`, `host`, `tagline`, `footer` — your basic info.
- `links[]` — copy a block to add a link, delete one to remove it.
- `playlist[]` — copy a block to add a song (see below).
- `video` — set `youtubeId` to your background clip; `grayscale` on/off.
- `spinnerFrames` / `spinnerSpeed` — the tab-title spinner.

## Audio

Audio files are **not** included in this repo — supply your own. Drop an
`.mp3` next to `index.html`, then add an entry to `playlist[]`:

```js
{ title: "Track Name", artist: "Artist", src: "your-song.mp3" }
```

Browsers block audio autoplay until the user interacts, so the first track
starts on the first click/keypress anywhere on the page.

## Hosting

It's a static file — host it anywhere (a VPS, Netlify, GitHub Pages, etc.).
Note that the YouTube background embed is unreliable over `file://`; serve it
over `http(s)` for the video to load.

## License

MIT

# Radio Roulette

Press **TUNE** and land on a random web radio station from anywhere in the
world — then capture what you hear, loop it in time, and export the stem.

A single self-contained HTML file: no build step, no dependencies, no server.
Open `index_studio_en.html` in a browser, or drop it into a Max for Live
`HTML INSTRUMENTS` device to run it next to a Live set.

## What it does

- **Tune** — a random station, filtered by genre, country, name, minimum
  bitrate, HTTPS-only, or capture-ready-only. Station data comes from the
  [Radio Browser](https://www.radio-browser.info) public API.
- **Capture** — grab the last stretch of audio off the stream into a buffer,
  with a waveform view.
- **Loop** — one-shot or looping playback, with length in beats (1/2/4/8/16),
  Auto BPM detection or tap tempo, and lock-to-beat trimming.
- **Export** — save the captured stem as a file, ready to drag into a DAW or
  a restoration tool.
- **Five themes** — Default (paper), Sepia, Midnight, Ember, Phosphor. Every
  colour lives in CSS tokens, so a theme is one attribute on `<html>` and even
  the waveform canvas follows along.

Keyboard: `space` play/pause · `N` next station · `F` favourite · `C` capture ·
`L` loop · `O` one shot · `E` export · `B` auto BPM · `T` tap.

## Notes

The page is designed to work from `file://` — that is how it runs inside the
Max for Live device — so everything is inlined in one document on purpose.
Which stations can be captured depends on their CORS headers; the
"capture-ready only" filter keeps the roulette to those that work.

Station metadata © the [Radio Browser](https://www.radio-browser.info)
community. Streams belong to their broadcasters — capture responsibly and
respect the rights on what you record.

MIT licensed. Made by pinaxa, with Claude.

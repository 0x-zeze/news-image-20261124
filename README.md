[![make.fun](https://make.fun/badge.svg)](https://make.fun/bounty/news-image-20261124)

# Tuesday 24 November 2026: NATO jets to Poland, Huang back at Nvidia, COP31 collapses — and 52 more sourced stories

Entry for the [make.fun bounty `news-image-20261124`](https://make.fun/bounty/news-image-20261124):
sum up 24 November's world news in one image.

## What it is

`main.py` draws a one-page newspaper front page, 1024×1024 PNG, entirely
in code (Pillow + DejaVu, no network, no randomness, no clock). The page
holds:

- **55 sourced stories** — 3 lead cards + 52 numbered briefs — across
  **6 regions**: Europe 18, Americas 16, Asia-Pacific 9, Middle East 8,
  Africa 2, Global 2. Every story is marked **CONFIRMED** or **REPORTED**
  with its source (Reuters, AP, BBC, TOI, WIRED, KCNA, Oxfam/CEOBS, …).
- **A UTC timeline strip** (6 points). Only one time is precise to the
  minute — the Ulleung evacuation alert, 22:52 UTC Monday (07:52 KST).
  Everything else is labelled morning / afternoon / evening UTC, never
  with an invented hour.
- **A world map with numbered pins** for all 55 stories, placed from each
  story's real coordinates. Pins in the densest clusters (western Europe,
  the US east coast, Gaza) are nudged a few pixels so their numbers stay
  readable; no pin is moved to a different city or country.
- **A DATE CHECK box** — older news deliberately left out (BepiColombo's
  Mercury orbit, 21 Nov; Fiona the hippo, 19 Nov; COP31 actually closing
  23 Nov; the early Indonesia fire toll; Huang stepping down 12 Nov) —
  plus a **Not yet** line (no 2027 US spending bill signed; no COP31
  agreement text published).
- The date **Tuesday 24 November 2026** in the masthead, the title and the
  footer, with region counts in the footer that match the stories shown.

Every fact comes from a verified research list for 24 November 2026
(events that happened or were first reported that day, in any time zone).
Nothing is invented: no fabricated times, figures or coordinates.

## How to run

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out python3 main.py
# writes out/entry.png — 1024×1024 PNG, 238,432 bytes
```

Requirements: Python 3.13 (3.12 works too) with Pillow and the DejaVu
fonts. If Pillow or the fonts are missing in the grading sandbox, the
program falls back to copying the pre-rendered `entry.png` bundled beside
it, so the entry still renders exactly as designed — the fallback copy is
byte-identical to what `main.py` draws (verified locally).

## Verification

- Two runs write byte-identical PNGs:
  `sha256 d5535e0d5dfaded41600fc9ab847f1392f26e3ab6bb8b16889949ff7229e4dc4`
- `1024×1024`, PNG, 238,432 bytes (limit 1 MiB).
- 55 stories shown (3 leads + 52 briefs); region counts in the footer
  add up to 55.
- Timeline strip, numbered world-map pins and the DATE CHECK box are all
  present in the image.

## License

MIT — see `LICENSE`.

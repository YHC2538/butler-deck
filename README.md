# Butler of Everything — term project proposal (Slidev)

Group 9 · IoT Technologies and Applications · due 2026-11-09 13:00

## Run

Needs Node.js 22.12 or newer.

```bash
npm install          # or: pnpm install
npm run dev          # opens http://localhost:3030
```

- Presenter view with the speaker notes (Traditional Chinese): http://localhost:3030/presenter
- Overview of all slides: press `o`
- Export PDF: `npm run export` (needs `playwright-chromium`, installed as a dev dependency;
  if the browser is missing run `npx playwright install chromium` once)
- Export PowerPoint (each slide as an image): `npm run export-pptx`

## Files

- `slides.md`  all 19 slides (HTML inside Markdown) and the speaker notes
- `styles/index.css`  the whole visual design (the slides use their own classes, not theme typography)

## Before you present

- Title slide: replace `[name]` with the presenter (members: 徐瑞利, 陳羿豪, 孫悅騫).
- Gantt (slide 17): owners and dates are tentative; edit the `tasks` rows, or the week labels, in `slides.md`.
- Slide numbers come from `{{ $slidev.nav.currentPage }}`.

## Template checklist (course requirement)

| # | Section | Slides |
|---|---|---|
| 1 | Description (≥1) | 2, 3 |
| 2 | Related Work (≥3; distant / intermediate / close + unique advantages) | 4, 5, 6, 7 |
| 3 | Actors | 8 |
| 4 | Preconditions | 9 |
| 5 | Triggers | 10 |
| 6 | Normal Flow | 11, 12 |
| 7 | Alternative Flow | 13 |
| 8 | High-Level Illustration | 14, 15 |
| 9 | Potential Challenges and Solutions | 16 |
| 10 | Tasks and Schedule (Gantt chart) | 17 |
| 11 | References | 19 |

Slide 18 (demo and evaluation plan) is an extra.

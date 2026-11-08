# Library (private)

Nick's Dribbble reference library for the `dribbble-frontend` skill: **1,170 full-res shots** (740 web, 430 mobile,
all exactly 1800x1350) from 234 searches in 36 categories, plus 120 older search-page captures.

| Folder | What | Index |
|---|---|---|
| `web-shots/` | 740 shots, w01-w148, 5 per search | [web-shots/INDEX.md](web-shots/INDEX.md) |
| `mobile-shots/` | 430 shots, m01-m86, 5 per search | [mobile-shots/INDEX.md](mobile-shots/INDEX.md) |
| `web/`, `mobile/` | older search-page grid captures (w01-w30, m01-m30) | `INDEX.md` in each |
| `sheets/` | contact sheets | |
| `tools/fetch-shots.mjs` | the fetcher (real 1800x1350 originals only; skips ads; never bypasses a bot check) | |

Use it:

```bash
export DRIBBBLE_LIB="$PWD/library"
python3 scripts/pick.py write-categories
python3 scripts/pick.py pick "privacy fintech landing" -n 4
```

Grow it (Playwright needed):

```bash
DRIBBBLE_LIB="$PWD/library" PLAYWRIGHT_FROM=/path/to/project-with-playwright/package.json \
  node library/tools/fetch-shots.mjs web 10 "term a" "term b" -- "spare term"
```

Then map each new term in `TERM_CATS` in `nick-skills/skills/dribbble-frontend/scripts/pick.py` (the skill is edited
there and published here with `scripts/publish-skill.sh`).

**Rights.** Every image is another designer's work, credited with its link in the INDEX files. This repo is internal
reference only and **must stay private**. Never make it public, ship the images in a product, or copy them into a
project repo. The working copy also lives in the private `dribbble-frontend-kit` (grokbot/design-references).

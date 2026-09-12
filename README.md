# KCG — Karate Chop Game

The official KCG rulebook, as a website.

Static HTML, CSS and JavaScript. No build step, no dependencies, no framework.
Clone it and open `index.html` — that's the whole setup.

---

## Viewing it

**Quickest:** double-click `index.html`.

**Properly** (recommended — relative paths and anchors behave exactly as they
will live):

```bash
python3 -m http.server 4173
```

Then open <http://localhost:4173>.

## Publishing it

The repo is ready for GitHub Pages as-is: `index.html` sits at the root and
`.nojekyll` is present so Jekyll doesn't touch the folder.

Settings → Pages → Source: **Deploy from a branch** → Branch: **main**, folder
**/ (root)** → Save. The site appears at
`https://<username>.github.io/<repo>/` within a minute or two.

It will also drop straight onto Netlify or Cloudflare Pages with no
configuration.

---

## Structure

```
index.html              the entire site — one page
styles/
  tokens.css            design tokens: color, type, space, shape
  base.css              reset, typography, focus states, motion preferences
  layout.css            container, section rhythm, card grid
  components.css        header/nav, buttons, rule lists, zone panels,
                        tables, callouts, spec tiles, footer
scripts/
  main.js               mobile nav, header scroll state, footer year
assets/                 logo and artwork
```

Page sections, in order: Concept → Joining → Legal chop zones → Turn system →
Blocking → Penalty chops → Spirit of the Game → Competitive format → Growing
the sport → Governing body.

## Editing the rules

All copy lives in `index.html` as plain HTML — no templating, no CMS. Find the
section by its `id` (`#zones`, `#turns`, `#penalties`, `#tournament`) and edit
the text directly.

---

## Brand

**The KCG lettermark is the logo** — the orange rounded square reading "KCG"
(`assets/kcg-lettermark.jpg`). Use it everywhere. Do not substitute the
circular crest or the jersey mark.

| File | Status |
| --- | --- |
| `kcg-lettermark.jpg` | **the logo** — hero, header, footer, governors, touch icon |
| `favicon.svg` | browser tab (a vector echo of the lettermark) |
| `kcg-crest.png` | unused — circular crest, kept for reference |
| `kcg-mark.png` | unused — jersey mark, kept for reference |
| `kcg-emblem.png` | unused — the original two-up brand sheet |

### Color

Sampled from the artwork, not guessed:

| Token | Value | Use |
| --- | --- | --- |
| `--brand-500` | `#E9580B` | lettermark orange — surfaces, large display text |
| `--brand-700` | `#AC4108` | links and buttons (the accessible variant) |
| `--crest-ink` | `#1C1B19` | banned-zone panel, warning pill |
| `--coral` | `#F0997B` | accents on dark |
| `--cream-50` | `#FFF7ED` | page background |
| `--danger` | `#8F1F14` | negative scores, disqualifications |

`--brand-500` is deliberately **not** used behind normal-size white text: white
on `#E9580B` measures 3.58:1, which fails WCAG AA for body copy. Buttons use
`--brand-700` (5.98:1). Keep that distinction if you restyle.

Verified pairs — ink on cream 17.71:1 · brand-700 on cream 5.63:1 · coral on
crest-ink 7.82:1 · danger on cream 8.33:1.

---

## ⚠️ This site and the Google Doc disagree

The site was built from **"KCG (Karate Chop Game) — Official Rulebook"** in
Google Drive, but five rules have since been changed on the site and **not yet
in the doc**. The site is the newer version.

| Rule | Google Doc | This site |
| --- | --- | --- |
| Chopping the same person twice in a row | Not allowed — another player must be involved in between | **Allowed.** No limit; players can chop each other unlimited times, back to back |
| 3-different-players-in-a-row cap, and the "all 3 are owed a return chop" mechanic | Present | **Removed entirely** — was never an actual rule |
| Blocking | Blocker must target someone other than whoever they just blocked | **No restriction** — blocker may chop straight back |
| Banned zone, tournament scoring | −2 points | **Disqualification from the round** |
| Banned zone, fouls table | 1 penalty chop | **Disqualification from the round** |
| Successful block, tournament scoring | +1 point (marked TBD) | **Removed** — a block scores nothing |

Two knock-on effects worth knowing:

- Banned zones are no longer a penalty-chop offence at all. Penalty chops now
  cover driving, mid-meal and open-drink fouls only.
- Blocking still matters tactically — it transfers the turn obligation to the
  blocker — but it is worth no points.

The doc also has two headed-but-empty sections, **Uniform/Jersey** and **KCG
Primary Crest and Jersey Icon**. They aren't on the site because there was no
content to publish.

---

## Governing body

Andrés Pardiño · Alejandro Pardiño — end of list.

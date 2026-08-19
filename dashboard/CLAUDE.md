# Dashboard — Mentorship Platform

A mentorship-mentee matching platform for UC Santa Cruz's Baskin Engineering Mentorship
Program. This branch owns the dashboard — the space each matched pair lands in after
onboarding, to track sessions and progress over the 12-week cohort.

No dashboard screens exist yet — this folder currently just has the real brand reference to
build from. Onboarding's screens live on the `Onboarding` branch; see the root `CLAUDE.md` for
how the branches relate.

## What's in this folder

- `_ds/baskin-engineering/` — the real UC Santa Cruz Baskin Engineering brand: `tokens.css`
  (CSS custom properties for the official palette) and `readme.md` (colors, typography, logo
  rules, where to get real logo assets). Source:
  https://toolkit.engineering.ucsc.edu/baskin-engineering-brand/. Shared with the onboarding
  team — keep changes here compatible with theirs so the two branches merge cleanly later.
- `support.js` — runtime needed to render a Claude Design `.dc.html` canvas, if you create one
  here (e.g. `Dashboard.dc.html`, linking `_ds/baskin-engineering/tokens.css` the same way
  onboarding's canvas does).

## Working on this

- Use `_ds/baskin-engineering/tokens.css`'s custom properties (`--be-navy`, `--be-orange`,
  etc.) instead of re-typing hex values, so a future brand-color change is a one-file edit.
- Check contrast (WebAIM Color Contrast Checker) before shipping any new foreground/background
  color pairing — see `_ds/baskin-engineering/readme.md`.
- Real logo files aren't in this repo (they require a CruzID, via UCSC's brand Google Drive).

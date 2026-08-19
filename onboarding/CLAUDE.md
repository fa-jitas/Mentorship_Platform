# Onboarding — Mentorship Platform

A mentorship-mentee matching platform for UC Santa Cruz's Baskin Engineering Mentorship
Program. This branch owns the onboarding flow: role select (student/mentor), account creation,
cohort expectations, profile building, matching, and the first message with your match.

## What's in this folder

- `Mentorship Onboarding.dc.html` — the onboarding design canvas (Claude Design). Open it in a
  browser to view the onboarding screens. It's self-contained (inline styles), already using
  the real UC Santa Cruz Baskin Engineering brand colors and Roboto typeface.
- `_ds/baskin-engineering/` — the real brand reference: `tokens.css` (CSS custom properties for
  the official palette) and `readme.md` (colors, typography, logo rules, where to get real logo
  assets). Source: https://toolkit.engineering.ucsc.edu/baskin-engineering-brand/
- `uploads/` — reference screenshots.
- `support.js` — runtime the `.dc.html` canvas needs to render; don't remove it.

## Working on this

- Use `_ds/baskin-engineering/tokens.css`'s custom properties (`--be-navy`, `--be-orange`,
  etc.) for new colors instead of re-typing hex values, so a future brand-color change is a
  one-file edit.
- Check contrast (WebAIM Color Contrast Checker) before shipping any new foreground/background
  color pairing — see `_ds/baskin-engineering/readme.md`.
- Real logo files aren't in this repo (they require a CruzID, via UCSC's brand Google Drive) —
  the header currently says "logo placeholder" until someone adds one.

# Onboarding — Fly Bites

Fly Bites is a mobile app concept for ordering food inside an airport terminal: give it your
flight, it shows what you can eat before you board — what's near your gate, how long the wait
is, whether you can still make it. Drawn for one surface, a 393×852 iPhone frame.

## What's in this folder

- `Mentorship Onboarding.dc.html` — the onboarding design canvas (Claude Design). Open it in a
  browser to view the onboarding screens; it pulls its styling from `_ds/onboarding/`.
- `_ds/onboarding/` — the Fly Bites design system: tokens (colors, type, spacing), components,
  and the UI kit the onboarding screens are built from. Shared with the dashboard team — see the
  root `CLAUDE.md`.
- `_ds/onboarding/readme.md` — design system source notes and content/voice guidelines (worth
  reading before writing onboarding copy).
- `uploads/` — reference screenshots.
- `support.js` — runtime the `.dc.html` canvas needs to render; don't remove it.

## Working on this

- Onboarding copy pattern: two lines, a greeting then the payoff (e.g. "Welcome aboard!" /
  "Your meal and flight, tracked together"). Sentence case, second person, no "I".
- If you rename or restructure anything under `_ds/`, update every reference to that path in
  `Mentorship Onboarding.dc.html` and the files inside `_ds/onboarding/` (`_ds_manifest.json`,
  `_ds_bundle.js`, `styles.css`) — they cross-reference each other by literal path string.

# Dashboard — Fly Bites

Fly Bites is a mobile app concept for ordering food inside an airport terminal: give it your
flight, it shows what you can eat before you board — what's near your gate, how long the wait
is, whether you can still make it. Drawn for one surface, a 393×852 iPhone frame.

No dashboard screens exist yet — this folder currently just has the shared design system to
build from. Onboarding's actual screens live on the `Onboarding` branch; see the root
`CLAUDE.md` for how the branches relate.

## What's in this folder

- `_ds/onboarding/` — the Fly Bites design system: tokens (colors, type, spacing), components,
  and the UI kit. Shared with the onboarding team — keep changes here compatible with theirs so
  the two branches merge cleanly later.
- `_ds/onboarding/readme.md` — design system source notes and content/voice guidelines.
- `support.js` — runtime needed to render a Claude Design `.dc.html` canvas, if you create one
  here (e.g. `Dashboard.dc.html`, referencing `_ds/onboarding/` the same way onboarding's does).

## Working on this

- Voice: friendly gate agent — short, warm, practical, sentence case, second person, no "I".
- If you rename or restructure anything under `_ds/`, update every reference to that path in
  your `.dc.html` canvas and the files inside `_ds/onboarding/` (`_ds_manifest.json`,
  `_ds_bundle.js`, `styles.css`) — they cross-reference each other by literal path string.

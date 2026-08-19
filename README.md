# Mentorship Platform

Fly Bites is a mobile app concept for ordering food inside an airport terminal: give it your
flight, it shows what you can eat before you board — what's near your gate, how long the wait
is, whether you can still make it. Built for one surface, a 393×852 iPhone frame.

## Branches

Work is split by team, across branches, not folders on `main`:

| Branch | Team | Contents |
| --- | --- | --- |
| [`Onboarding`](../../tree/Onboarding) | Onboarding | `onboarding/` — onboarding screens (Claude Design canvas) + design system |
| [`Dashboard`](../../tree/Dashboard) | Dashboard | `dashboard/` — design system to build the dashboard from |
| `main` | — | Merge target once both sides are ready to combine |

Both branches share the same design system (`_ds/onboarding/` in each team's folder) so the two
sides stay visually consistent and merge with minimal conflicts later. If you change shared
tokens or components, coordinate with the other team before merging to `main`.

## Working with Claude Code

Each branch has a `CLAUDE.md` at the repo root and another inside its team folder
(`onboarding/CLAUDE.md` / `dashboard/CLAUDE.md`) with project and scope-specific context. Clone
the repo, check out your team's branch, and open the folder in Claude Code — it picks up that
context automatically.

```
git clone https://github.com/fa-jitas/Mentorship_Platform.git
cd Mentorship_Platform
git checkout Onboarding   # or Dashboard
```

## Design system

The shared Fly Bites design system (tokens, components, UI kit) lives under each branch's
`_ds/onboarding/` folder. See its `readme.md` for design-system source notes and content/voice
guidelines. If you rename or restructure anything under `_ds/`, update every reference to that
path in the `.dc.html` canvas and in `_ds_manifest.json` / `_ds_bundle.js` / `styles.css` —
they cross-reference each other by literal path string.

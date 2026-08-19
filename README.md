# Mentorship Platform

A mentorship-mentee matching platform for UC Santa Cruz's Baskin Engineering Mentorship
Program: students and mentors sign up, build a profile, get matched, and start their first
conversation.

## Branches

Work is split by team, across branches, not folders on `main`:

| Branch | Team | Contents |
| --- | --- | --- |
| [`Onboarding`](../../tree/Onboarding) | Onboarding | `onboarding/` — onboarding screens (Claude Design canvas) + brand reference |
| [`Dashboard`](../../tree/Dashboard) | Dashboard | `dashboard/` — brand reference to build the dashboard from |
| `main` | — | Merge target once both sides are ready to combine |

## Design system

Both branches share a `_ds/baskin-engineering/` reference: the real UC Santa Cruz Baskin
Engineering brand colors and typography, pulled from
https://toolkit.engineering.ucsc.edu/baskin-engineering-brand/. See its `readme.md` for the
full palette, typography, logo rules, and where to get real logo assets (CruzID required).

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

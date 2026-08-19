# Mentorship Platform

A mentorship-mentee matching platform for UC Santa Cruz's Baskin Engineering Mentorship
Program: students and mentors sign up, build a profile, get matched, and start their first
conversation.

This repo is split by team across branches:

- `Onboarding` branch — onboarding flow, owned by the onboarding team. Work lives under `onboarding/`.
- `Dashboard` branch — dashboard, owned by the dashboard team. Work lives under `dashboard/`.
- `main` — merge target once both sides are ready to combine.

## Design system

Both team folders share a `_ds/baskin-engineering/` reference — the real UC Santa Cruz Baskin
Engineering brand (colors, typography) pulled from
https://toolkit.engineering.ucsc.edu/baskin-engineering-brand/, not a placeholder. Keep the copy
in your branch's `_ds/` folder in sync with the other branch, or flag it for review before
merging to `main`.

See the `CLAUDE.md` inside each team's folder (`onboarding/CLAUDE.md`, `dashboard/CLAUDE.md`)
for scope-specific context.

## Git workflow (5-person team, shared branches)

Everyone on a team pushes to the same branch (`Onboarding` or `Dashboard`), so:

- **Pull before starting work, and pull again right before pushing.** Run `git pull` (or
  `git pull --rebase` if you have local commits) before you begin, and once more immediately
  before `git push`, so you're never pushing on top of stale history.
- **Commit locally as you go** — don't wait until a big change is finished to make your first
  commit.
- **Never push without asking first.** Show the user what's about to be pushed (`git status`,
  `git diff --stat` against the remote branch, or the commits about to go up) and get an
  explicit go-ahead before running `git push`. Five people auto-pushing to two shared branches
  is how broken or half-finished work lands where everyone else is working.
- If `git pull` reports a conflict, stop and surface it — don't resolve a conflict by guessing
  which side is right without checking with the user.

## `main` is live (GitHub Pages)

`main` is served publicly at https://fa-jitas.github.io/Mentorship_Platform/ — never push or
merge into `main` directly. When a branch's work is ready to go live, open a Pull Request into
`main` on GitHub instead, and only merge it once someone has actually looked at the diff. This
keeps a review checkpoint before anything reaches the public link, since `main` no longer waits
for both teams to finish — it updates incrementally as each team's work is ready.

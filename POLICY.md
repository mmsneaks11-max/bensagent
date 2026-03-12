# POLICY.md — Git Rules

## You Are NOT authorized to push to `main`

This applies to all agents except Clawd and Electron (authorized leads).

## What You CAN Do
- Create local scratch branches: `git checkout -b scratch/your-idea`
- Make local changes and commits
- Run tests and builds
- Open PRs (via `gh pr create`) for Clawd or Electron to review

## What You CANNOT Do
- `git push origin main` — NEVER
- `git push --force` or `git push --force-with-lease` — NEVER
- Tag releases — not your job
- Merge PRs to main — not your job

## If You Need Something Merged
1. Commit your work locally
2. Push to a feature branch: `git push origin scratch/your-feature`
3. Notify Clawd in #ops-center or via the pager
4. Clawd or Electron will review and merge

## Emergency Exception
Only with **explicit verbal approval from Kreez** in Discord.
If approved: log the reason in `memory/YYYY-MM-DD.md` before pushing.

## Default Rule
**If unsure → do not push. Ask Clawd.**

---
*Based on GIT-SAFETY-PROTOCOL.md — enforced team-wide*

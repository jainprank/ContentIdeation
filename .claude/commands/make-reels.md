---
description: Run the full Insta Studio pipeline for a brief: trends, scripts, draft video, and review package.
argument-hint: <brief file in briefs/, e.g. 2026-10-14-week1.md>
---

Run the Insta Studio pipeline for the brief `briefs/$ARGUMENTS` (see CLAUDE.md for the rules). If no argument is given, use the newest file in `briefs/` (not `_template.md`).

Run the steps in order. Do not start a step until the previous one has finished and written its files.

1. **Research.** Use the `trend-scout` agent. Ask it for a trend report for today's date. It writes `research/<date>-trends.md`.
2. **Scripts.** Use the `script-writer` agent. Give it the brief and the new trend report. It writes `output/<date>-<slug>/script.md` for each reel in the brief.
3. **Video.** For each script, use the `avatar-producer` agent. It writes `draft.mp4` and `render_log.md`. If owner clips are missing, stop and list what the owners need to record.
4. **Review.** For each package, use the `reviewer` agent. It writes `review.md` and sets the status.

When all steps finish, reply with a short summary table:

| Post folder | Status | What the owner must do |
|---|---|---|

Include the trend report path, and list any NEEDS_FIX items with the agent that should fix each one. Do not publish anything.

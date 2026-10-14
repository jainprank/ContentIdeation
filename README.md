# Insta Studio

Agents that turn research into review-ready Instagram reels for our dance & fitness page. Nothing is published automatically.

## One-time setup
1. Make sure the Apify MCP server is connected in Claude Code (it provides `search-actors`, `call-actor`, `get-dataset-items`).
2. Install FFmpeg: `brew install ffmpeg`
3. Add your clips to `assets/avatars/` (for example `priyanka_front.mp4`, `abha_side.mp4`) and any voice recordings you want used.
4. Optional, for lip-sync: install MuseTalk following its own README. The pipeline falls back to FFmpeg-only if it is missing.

## Every week
1. Copy `briefs/_template.md` to `briefs/<date>-week.md` and fill it in.
2. Open Claude Code in this folder and run:
   `/make-reels <date>-week.md`
3. Review `output/<date>-<slug>/review.md` and `draft.mp4` for each post.
4. Fix anything marked NEEDS_FIX (ask the agent named in the review to redo that step).
5. Post manually in the Instagram app: upload the video, pick the audio named in the review, paste the caption, and set the AI label.

## What each agent does
| Agent | Job | Output |
|---|---|---|
| trend-scout | Finds trending formats, audio, and hashtags via Apify (public data) | `research/<date>-trends.md` |
| script-writer | Writes hooks, beats, lines, captions, and a shot list | `output/<folder>/script.md` |
| avatar-producer | Edits the draft video from owner clips (FFmpeg, optional MuseTalk) | `draft.mp4`, `render_log.md` |
| reviewer | Compliance and quality check, then a copy-paste post sheet | `review.md` with STATUS |

## Notes
- Apify actors cost credits. The trend-scout starts with small runs to keep costs low.
- The rules for likeness, music, disclosure, and health claims live in `CLAUDE.md`. Edit the brand section there.
- These agents load when Claude Code starts in this folder. If you add or change an agent, restart the session.

# Insta Studio — Dance & Fitness page

Owners: Priyanka and Abha. Goal: a lively Instagram page showing a fun daily activity we do together (dance + fitness).

## Hard rules (every agent follows these)
- **Nothing is published by an agent.** Final output goes to `output/<date>-<slug>/` with status `READY_FOR_REVIEW`. The owners review and post manually.
- **Only the owners' likeness and voice.** Do not generate or lip-sync anyone else without written consent from that person.
- **Label AI-made media.** Every package carries an `ai_disclosure` line the owners can paste into the caption or use as the "AI-generated" label.
- **Music:** only audio from Instagram's licensed audio library (picked by the owner in the app). Never put a commercial song file into a video.
- **Research uses public data only.** Apify actors only; no logins, no cookies, no account scraping.
- **Health claims:** fitness tips are general fun activity, not medical advice. No weight-loss promises, no before/after claims.

## Brand (edit freely)
- Tone: upbeat, playful, real. Two friends having fun, not a studio ad.
- Pillars: daily dance break, 5-minute fitness combo, "us vs. the song" challenge, behind-the-scenes.
- Hashtags: keep 5–8, mix one niche tag, one broad tag, and one trend tag from research.

## Folder map
- `briefs/` — one brief per post batch (copy `briefs/_template.md`)
- `research/` — trend reports from `trend-scout` (dated)
- `assets/avatars/` — owner reference clips and photos (you add these)
- `output/` — review packages from the pipeline
- `.claude/agents/` — the four agents
- `.claude/commands/make-reels.md` — runs the whole pipeline

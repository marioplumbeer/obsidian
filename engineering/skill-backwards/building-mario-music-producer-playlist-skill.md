---
title: Building the mario-music-producer-playlist Skill
date: 2026-07-27
tags: [engineering, claude-code, agent-skills, youtube-music, genius-api]
---

# Building the mario-music-producer-playlist Skill

## Summary
Built a Claude Code skill that turns "make me a YouTube Music playlist of songs produced by X" into a real playlist. The interesting part wasn't the happy path — it was two full architecture reversals, each forced by evidence from actually running the thing against live APIs rather than by upfront design.

## Decisions & insights

### Channel-only discovery is structurally blind to the thing that matters
First version resolved a producer to their own YouTube channel (disambiguated by keeping only Music-tagged channels and picking the highest subscriber count, since YouTube's public API has no "verified artist" flag) and pulled from their catalog. It worked — until a real Swizz Beatz/Timbaland production credit turned up on The Game's channel, which this approach could never surface. A production credit and a channel are just different things; no amount of tuning the channel-matching logic fixes that.

### Genius is the actual source of truth, but only when queried right
Reinstating Genius, the fix wasn't just "add Genius back" — it was switching from noisy full-text `/search` to `/artists/{id}/songs?sort=release_date|popularity`, an endpoint scoped to the artist and pre-sorted by the right signal. Every candidate still needs its `producer_artists` field confirmed individually, since that endpoint lists any credited role (writer, feature, producer), not just production.

### An unplanned discovery beat the planned fix
Hit a real YouTube API 429 mid-session — the standard free quota is exactly 100 `search.list` calls/day. Backoff/retry was the first instinct, but retrying doesn't help when the quota is genuinely exhausted, only when it's a transient burst — a distinction worth checking against the actual error body, not assuming. While waiting on the reset, inspecting live Genius responses turned up something better than the fix being sought: Genius often already embeds a direct YouTube link in its `media` field, cutting the cost of finding a video by roughly 100x (`videos.list`, 1 unit vs. `search.list`, 100 units). Made that the default path, with real search demoted to an explicit, off-by-default opt-in.

### Root-cause the environment before working around it
An OAuth browser flow that looked broken twice turned out to be `localhost` resolving to IPv6 before IPv4 on the test machine, so the browser and the local callback server tried different addresses. The actual fix (bind both explicitly to `127.0.0.1`) was smaller and more reliable than the manual copy-paste workaround that was tried first — worth remembering that "this API/library seems flaky" is often an environment mismatch, not a real defect.

## Key takeaways
1. Don't trust a design until it's run against live data — two of this project's core architecture decisions were reversed by evidence a single real API response surfaced, not by anticipating edge cases in advance.
2. When a fallback exists for cost or reliability reasons, make it an explicit opt-in with a stated reason, not a silent default — it should be a deliberate choice, not something a user discovers only after the bill (in tokens, quota, or time) arrives.
3. A flaky-looking dependency is worth one real diagnostic pass (inspect the actual error, check the actual environment) before reaching for a workaround — the workaround is often solving the wrong problem.

## References
- PR: [marioplumbeer/skills#18](https://github.com/marioplumbeer/skills/pull/18)

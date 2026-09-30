# Scout Still Knows — Lyric Teaser (v2)

**Date:** 2026-09-30 (ET)  
**Output:** `assets/video/scout_still_knows_teaser.mp4`  
**Also:** `assets/video/scout_still_knows_teaser_v2.mp4` (same encode); v1 archived as `scout_still_knows_teaser_v1.mp4`

## Specs

| Field | Value |
|-------|-------|
| Duration | **26.21s** (ffprobe; target &lt;30s) |
| Resolution | 1920×1080 @ 24fps |
| Video | H.264 (libx264, CRF 19) |
| Audio | AAC 192 kb/s stereo |
| Size | ~19.2 MB |
| Captions | Burned-in ASS (Liberation Sans Bold, white + soft dark outline/shadow, lower-third; centered title on end card) |

## Creative (v2 — response to feedback)

Fewer cuts, longer holds so the chorus and Scout story can land. Dropped stacked night kitchen/transit/blue-hour walk. Prefer brighter domestic + golden-hour clips; lift exposure/shadows with `eq` + `curves`. Soft crossfades (0.75s). End card on graded golden-hour walk (not crushed blue-hour).

### Lyric lines (on-screen)

1. And you're done waiting in these walls  
2. Scout still waits by the door at nine  
3. Like loyalty don't understand goodbye  
4. I kept the grind, you kept your peace  
5. He kept the scent of you and me  
6. **Scout Still Knows** / Zoë MV (end card)

Source lyric text from `lyrics/LYRICS_LOCKED.md` (chorus). Whisper timestamps on `scout_still_knows_seedmusic_cli.mp3` used for sync (chorus 2 window).

### Audio source window

| Song in | Song out | Notes |
|---------|----------|-------|
| **159.68s** (2:39.68) | ~**185.88s** | Chorus 2 through scent line + end card; afade in 0.40s, afade out from teaser 23.70s (2.5s) |

Whisper phrase map (song absolute → teaser-relative):

| Start | End | Line |
|-------|-----|------|
| 159.68 | 164.76 | And you're done waiting in these walls |
| 164.76 | 167.94 | Scout still waits by the door at nine |
| 167.94 | 170.82 | Like loyalty don't understand goodbye |
| 170.82 | 175.38 | I kept the grind, you kept your peace |
| 175.38 | 180.58 | He kept the scent of you and me |

### Video cuts (teaser-relative) — 3 long holds

| Teaser in–out | Dur (pre-xfade) | Clip | In-point | Beat / why |
|---------------|-----------------|------|----------|------------|
| 0.00–~8.25 (+0.75 xfade) | 9.0s | `p04_b_feed.mp4` | 1.0s | Home / Scout / bowls / leash — “waiting in these walls” + door motif |
| ~8.25–~16.70 (+0.75 xfade) | 9.2s | `p07_a_couch.mp4` | 1.5s | Zoë + Scout intimacy — loyalty / grind vs peace |
| ~16.70–26.21 | 9.5s | `p01_a_walk.mp4` | 2.0s | Golden-hour forward walk + title end card (replaces dark p08) |

Soft `xfade` fade transitions at offsets **8.25s** and **16.70s** (0.75s each). Total **26.21s**.

ASS overlay: `tmp/teaser/teaser_lyrics.ass` (PlayRes 1920×1080; v2 timings through 26.10s).

### Grade notes

| Clip | Grade |
|------|-------|
| `p04_b_feed` | `eq` brightness +0.07, contrast 1.06, gamma 1.10, sat 1.05; curves shadow lift `0.20→0.28` |
| `p07_a_couch` | Mild: brightness +0.04, gamma 1.06; light curves |
| `p01_a_walk` | Stronger lift for backlit face/jacket: brightness +0.10, contrast 1.08, gamma 1.14; curves `0.18→0.32` |

Avoided v1 stack of `p06_a_kitchen`, `p05_b_door`, `p06_b_bag`, `p05_a_transit`, ungraded `p08_a_walk` (crushed blue-hour end).

Mid-frame YAVG (verify): ~118–152 vs v1 dark end ~30–35.

## Build notes

- No new AI video generation; edit of existing MiniMax-H3 clips only.  
- No Jimeng web.  
- Audio from SeedMusic CLI master (`assets/audio/scout_still_knows_seedmusic_cli.mp3`).  
- v1 rejected: quick cuts hid song/MV value; last frame too dark.

## Mac delivery

Copied to machine `1f7690a8-3f0c-4b36-8e31-6a58c7127895`:

- `/Users/kenlu/zoe-mv-teaser/scout_still_knows_teaser.mp4`
- `/Users/kenlu/zoe-mv-teaser/scout_still_knows_teaser_v2.mp4`

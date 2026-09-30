# Scout Still Knows — Lyric Teaser

**Date:** 2026-09-30 (ET)  
**Output:** `assets/video/scout_still_knows_teaser.mp4`

## Specs

| Field | Value |
|-------|-------|
| Duration | **24.42s** (ffprobe; target 22–28s) |
| Resolution | 1920×1080 @ 24fps |
| Video | H.264 (libx264, CRF 19) |
| Audio | AAC 192 kb/s stereo |
| Size | ~11.8 MB |
| Captions | Burned-in ASS (Liberation Sans Bold, white + soft dark outline/shadow, lower-third; centered title on end card) |

## Creative

Punchy chorus teaser: Scout motif + breakup energy. Quick cuts from Phase 3 clips (not a continuous master excerpt), continuous chorus-2 audio so lyric burn-ins land on sung phrase boundaries.

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
| **159.68s** (2:39.68) | **180.58s** (3:00.58) + fade through ~184.1s | Chorus 2 punch → into bridge; afade in 0.35s, afade out from teaser 21.5s |

Whisper phrase map (song absolute):

| Start | End | Line |
|-------|-----|------|
| 159.68 | 164.76 | And you're done waiting in these walls |
| 164.76 | 167.94 | Scout still waits by the door at nine |
| 167.94 | 170.82 | Like loyalty don't understand goodbye |
| 170.82 | 175.38 | I kept the grind, you kept your peace |
| 175.38 | 180.58 | He kept the scent of you and me |

### Video cuts (teaser-relative)

| Teaser in–out | Dur | Clip | In-point | Beat |
|---------------|-----|------|----------|------|
| 0.00–5.08 | 5.08s | `p06_a_kitchen.mp4` | 4.0s | Break / “done waiting” |
| 5.08–8.26 | 3.18s | `p05_b_door.mp4` | 2.5s | Scout at the door |
| 8.26–11.14 | 2.88s | `p06_b_bag.mp4` | 3.0s | Loyalty / goodbye |
| 11.14–15.70 | 4.56s | `p05_a_transit.mp4` | 4.0s | Grind vs peace |
| 15.70–20.90 | 5.20s | `p07_a_couch.mp4` | 2.0s | Scout remains / scent |
| 20.90–24.40 | 3.50s | `p08_a_walk.mp4` | 5.0s | Forward walk, darkened end card |

ASS overlay: `tmp/teaser/teaser_lyrics.ass` (PlayRes 1920×1080).

## Build notes

- No new AI video generation; edit of existing MiniMax-H3 clips only.  
- No Jimeng web.  
- Audio from SeedMusic CLI master (`assets/audio/scout_still_knows_seedmusic_cli.mp3`).  
- Master MV continuous chorus window was an alternative; quick cuts chosen for stronger Scout/break/forward motif match to each caption.

## Mac delivery

Copied to machine `1f7690a8-3f0c-4b36-8e31-6a58c7127895`:

- `/Users/kenlu/zoe-mv-teaser/scout_still_knows_teaser.mp4`

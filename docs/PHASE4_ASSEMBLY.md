# Phase 4 — Assemble Scout Still Knows MV

**Date:** 2026-09-29 (ET)  
**Song:** `assets/audio/scout_still_knows_seedmusic_cli.mp3` (270.028s, MP3 320 kb/s stereo)  
**Video source:** 18 MiniMax-H3 I2V clips from Phase 3 (Plan A stills)

## Probe summary (inputs)

| Asset | Duration | Resolution | FPS | Video | Pixel | Audio |
|-------|----------|------------|-----|-------|-------|-------|
| Each H3 clip (×18) | 15.084s | 2560×1440 | 24 | H.264 | yuv420p | AAC (discarded) |
| SeedMusic CLI MP3 | 270.028s | — | — | — | — | MP3 320 kb/s |

All 18 clips share identical stream params → concat demuxer with `-c:v copy` is safe.  
Raw concat length: 18 × 15.084 = **271.512s** → trimmed to song length on mux.

## Shot order (concat)

Same as `docs/PHASE3_SHOTLIST.md`:

1. `p01_a_walk.mp4`
2. `p01_b_look.mp4`
3. `p02_a_campus.mp4`
4. `p02_b_leave.mp4`
5. `p03_a_meetup.mp4`
6. `p03_b_toast.mp4`
7. `p04_a_floor.mp4`
8. `p04_b_feed.mp4`
9. `p05_a_transit.mp4`
10. `p05_b_door.mp4`
11. `p06_a_kitchen.mp4`
12. `p06_b_bag.mp4`
13. `p07_a_couch.mp4`
14. `p07_b_fur.mp4`
15. `p08_a_walk.mp4`
16. `p08_b_ahead.mp4`
17. `p08_c_scout.mp4`
18. `p04_c_motif.mp4`

## Tools

- **ffmpeg** 7.1.5 (concat demuxer + mux + 720p scale)
- **ffprobe** for duration / stream checks

## Commands

Concat list: `tmp/concat_list.txt` (absolute `file '…'` paths, shot order above).

### Master (native H3 1440p, stream-copy video)

```bash
ffmpeg -y -f concat -safe 0 -i tmp/concat_list.txt \
  -i assets/audio/scout_still_knows_seedmusic_cli.mp3 \
  -map 0:v -map 1:a \
  -c:v copy \
  -c:a aac -b:a 192k \
  -t 270.027755 \
  -movflags +faststart \
  assets/video/scout_still_knows_mv.mp4
```

### 720p deliverable (repo-friendly)

```bash
ffmpeg -y -i assets/video/scout_still_knows_mv.mp4 \
  -vf "scale=1280:720:flags=lanczos" \
  -c:v libx264 -crf 20 -preset medium -pix_fmt yuv420p -r 24 \
  -c:a aac -b:a 160k \
  -movflags +faststart \
  assets/video/scout_still_knows_mv_720p.mp4
```

## Outputs

| File | Duration | Resolution | Size | Notes |
|------|----------|------------|------|-------|
| `assets/video/scout_still_knows_mv.mp4` | ~270.13s | 2560×1440 @ 24fps | ~176 MB | Full master; **not tracked in git** (too large; see `.gitignore`) |
| `assets/video/scout_still_knows_mv_720p.mp4` | ~270.25s | 1280×720 @ 24fps | ~74 MB | Tracked in git; primary shareable deliverable |

Audio on both: AAC from SeedMusic CLI track. Clip-embedded AAC discarded.

## Verification

- Master video stream ≈ 270.09s, audio ≈ 270.00s, container ≈ 270.13s
- 720p container ≈ 270.25s (minor frame pad from re-encode)
- Both have video + audio; moov atom front (`+faststart`) for streaming

## Mac delivery

Copied to machine `1f7690a8-3f0c-4b36-8e31-6a58c7127895`:

- `/Users/kenlu/zoe-mv-phase4/scout_still_knows_mv.mp4`
- `/Users/kenlu/zoe-mv-phase4/scout_still_knows_mv_720p.mp4`

## Notes

- No new AI video generation; no Jimeng web.
- Trimmed ~1.48s from end of concat (clip overrun vs song) via `-t` on mux.

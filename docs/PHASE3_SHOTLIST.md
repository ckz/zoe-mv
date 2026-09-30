# Phase 3 Shot List — Scout Still Knows

**Song:** `assets/audio/scout_still_knows_seedmusic_cli.mp3` (~270s / 4:30)  
**Model:** MiniMax-H3 · I2V · 16:9 · 15s · Plan A PNG stills  
**Pipeline:** `mmx video generate --model MiniMax-H3` (not Jimeng Seedance)

Total: **18 clips × 15s = 270s** (exact song length). Phase 4 muxes in order; minor trims OK.

| # | File | Still | Song window | Motion prompt (I2V) |
|---|------|-------|-------------|---------------------|
| 01 | `p01_a_walk.mp4` | page01_south_bay | 0:00–0:15 | Slow push-in as Zoë walks toward camera on a South Bay street at golden hour; palm shadows drift; warm amber light; subtle hair and jacket movement; cinematic indie MV, natural motion |
| 02 | `p01_b_look.mp4` | page01_south_bay | 0:15–0:30 | Soft lateral drift; Zoë glances toward the hills then forward again; golden-hour haze; gentle wind in trees; keep face consistent |
| 03 | `p02_a_campus.mp4` | page02_berkeley_startup | 0:30–0:45 | Gentle camera drift across Berkeley/campus energy into office; screens flicker softly; Zoë moves with purpose packing/working; cool daylight |
| 04 | `p02_b_leave.mp4` | page02_berkeley_startup | 0:45–1:00 | Zoë lifts a box / laptop with LumenReach sticky note energy; slight push-in on resolve; office bokeh; confident motion |
| 05 | `p03_a_meetup.mp4` | page03_meetup_david | 1:00–1:15 | Slow orbit in dim meetup venue; neon/string lights shimmer; Zoë and David mid-laugh; phone screens glow; chemistry, not melodrama |
| 06 | `p03_b_toast.mp4` | page03_meetup_david | 1:15–1:30 | Subtle handheld sway; they lean closer over drinks; shallow DOF; warm practical intimacy |
| 07 | `p04_a_floor.mp4` | page04_raise_scout | 1:30–1:45 | Soft living-room ambient; Zoë and David on the floor with Scout; Scout's tail/ears move; bowls and leash visible; cozy warmth |
| 08 | `p04_b_feed.mp4` | page04_raise_scout | 1:45–2:00 | Scout nosing toward food bowls; human hands gesture gently; leash by door; intimate domestic motion; Scout is the emotional center |
| 09 | `p05_a_transit.mp4` | page05_startup_orbit | 2:00–2:15 | Airport/rideshare cool blue grade; Zoë on laptop in transit; slight motion blur; calendar grind energy |
| 10 | `p05_b_door.mp4` | page05_startup_orbit | 2:15–2:30 | Cut-home energy: David and Scout by the door; Scout's head turns toward the door; waiting loyalty; warmer apartment light |
| 11 | `p06_a_kitchen.mp4` | page06_the_break | 2:30–2:45 | Night kitchen light; Zoë and David standing apart; slow push-in; Scout between them looks up; packed emotion, no chaos |
| 12 | `p06_b_bag.mp4` | page06_the_break | 2:45–3:00 | Subtle camera drift to half-zipped bag / distance between them; Scout shifts weight; quiet heartbreak |
| 13 | `p07_a_couch.mp4` | page07_scout_remains | 3:00–3:15 | Morning light; Zoë on couch, Scout's head in her lap; soft breathing motion; hand in fur; empty second mug implied |
| 14 | `p07_b_fur.mp4` | page07_scout_remains | 3:15–3:30 | Tight on hand in Scout's fur; Scout blinks/ear twitch; quiet grief and comfort; slow push-in |
| 15 | `p08_a_walk.mp4` | page08_forward_walk | 3:30–3:45 | Blue hour sidewalk; Zoë walking Scout; leash motion; city lights coming up; she looks ahead |
| 16 | `p08_b_ahead.mp4` | page08_forward_walk | 3:45–4:00 | Slow tracking beside them; Scout paces with her; hope without reunion; wind in hair |
| 17 | `p08_c_scout.mp4` | page08_forward_walk | 4:00–4:15 | Lower angle favoring Scout walking beside Zoë; familiar San Jose block; motif close |
| 18 | `p04_c_motif.mp4` | page04_raise_scout | 4:15–4:30 | Soft memory flash: Scout between them at home, bowls and leash; gentle loop-friendly motion for outro motif |

## Naming / paths

- Stills: `/workspace/zoe-mv/assets/images/<still>.png` (Plan A PNG masters)
- Out: `/workspace/zoe-mv/assets/video/<file>`
- Char refs available for `--reference-image` if identity drifts: `char_zoe.png`, `char_david.png`, `char_scout.png`

## CLI template

```bash
mmx video generate \
  --model MiniMax-H3 \
  --prompt "..." \
  --image /workspace/zoe-mv/assets/images/PAGE.png \
  --duration 15 \
  --ratio 16:9 \
  --download /workspace/zoe-mv/assets/video/NAME.mp4 \
  --non-interactive
```

Prefer sequential generate+wait (or async + poll) to stay inside Token Plan limits. On failure, retry once; record task IDs in this file or `assets/video/TASKS.md`.

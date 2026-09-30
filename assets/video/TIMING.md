# Phase 3 MiniMax-H3 I2V Timing Log

All times **America/New_York (ET, UTC-4)**. Model MiniMax-H3 · 15s · 16:9 · Plan A stills.

**Time basis:** `estimated` = session log + mtimes; `measured` = wall clock submit→download.

| # | File | Still | Task ID | Submit | Complete | Wall-s | Size MB | Basis | Notes |
|---|------|-------|---------|--------|----------|--------|---------|-------|-------|
| 01 | `p01_a_walk.mp4` | page01_south_bay | 447177470792232 | 20:18:00 | 20:31:27 | 807 | 7.68 | estimated | async after sync timeout; ok |
| 02 | `p01_b_look.mp4` | page01_south_bay | 447177559023998 | 20:18:10 | 20:31:28 | 798 | 7.49 | estimated | batch with 01; ok |
| 03 | `p02_a_campus.mp4` | page02_berkeley_startup | 447178957140490 | 20:18:20 | 20:31:30 | 790 | 12.64 | estimated | batch with 01; ok |
| 04 | `p02_b_leave.mp4` | page02_berkeley_startup | 447182495216143 | 20:31:10 | 20:42:51 | 701 | 9.63 | estimated | async before batch script; ok |
| 05 | `p03_a_meetup.mp4` | page03_meetup_david | 447182014792154 | 20:32:08 | 20:42:54 | 646 | 9.83 | estimated | batch script; ok |
| 06 | `p03_b_toast.mp4` | page03_meetup_david | 447181731193326 | 20:32:15 | 20:43:31 | 676 | 11.23 | estimated | batch script; ok |
| 07 | `p04_a_floor.mp4` | page04_raise_scout | 447183690203706 | 20:43:05 | 20:54:53 | 708 | 15.22 | estimated | bg script; ok |
| 08 | `p04_b_feed.mp4` | page04_raise_scout | 447191629873686 | 21:10:27 | 21:21:41 | 673 | 15.54 | measured | ok; soft-reprompt after identity policy 1046 |
| 09 | `p05_a_transit.mp4` | page05_startup_orbit | 447185002901846 | 20:44:10 | 20:54:56 | 646 | 7.86 | estimated | bg script; ok |
| 10 | `p05_b_door.mp4` | page05_startup_orbit | 447184354595192 | 20:44:40 | 20:54:23 | 583 | 6.96 | estimated | bg script; ok |
| 11 | `p06_a_kitchen.mp4` | page06_the_break | 447186707919353 | 20:54:20 | 21:10:27 | 967 | 7.19 | estimated-submit+mtime | ok; prior bg submit; download after poll-parser fix |
| 12 | `p06_b_bag.mp4` | page06_the_break | 447191040369187 | 21:10:32 | 21:21:05 | 632 | 7.25 | measured | ok;  |
| 13 | `p07_a_couch.mp4` | page07_scout_remains | 447191113273712 | 21:10:37 | 21:21:58 | 680 | 9.68 | measured | ok;  |
| 14 | `p07_b_fur.mp4` | page07_scout_remains | 447194737373703 | 21:21:07 | 21:32:26 | 679 | 12.95 | measured | ok;  |
| 15 | `p08_a_walk.mp4` | page08_forward_walk | 447194135294308 | 21:21:59 | 21:32:28 | 629 | 8.4 | measured | ok;  |
| 16 | `p08_b_ahead.mp4` | page08_forward_walk | 447194993783309 | 21:22:03 | 21:31:52 | 589 | 8.91 | measured | ok;  |
| 17 | `p08_c_scout.mp4` | page08_forward_walk | 447196310065516 | 21:31:52 | 21:43:14 | 681 | 10.73 | measured | ok;  |
| 18 | `p04_c_motif.mp4` | page04_raise_scout | 447196246167919 | 21:32:29 | 21:42:46 | 616 | 13.48 | measured | ok;  |

## Summary

| Metric | Value |
|--------|-------|
| Succeeded on disk | 18 / 18 |
| Total bytes (ok) | 182,659,456 (182.7 MB) |
| Estimated wall | n=10 mean=732s median=704s min=583s max=967s |
| Measured wall | n=8 mean=647s median=652s min=589s max=681s |
| Combined per-clip wall | n=18 mean=694s median=678s min=583s max=967s |
| Throughput (rough) | serial ~5.2 clips/h; 3-concurrent ~15.6 clips/h |

Updated 2026-09-29 21:43:14 ET.

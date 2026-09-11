# ppt169_beidou_navigation_narrated

- Source: topic-only input researched inside the Generate route (`sources/beidou_navigation_research.md` + `.facts.json`): the BeiDou system office site (beidou.gov.cn), the 2022 white paper *China's BeiDou Navigation Satellite System in the New Era*, Xinhua / People's Daily reports on the 2020-06-23 final launch and the 2020-07-31 commissioning; every figure carries its source and reference year on the page
- Style: free design (no bundled Style); deep-space field, orbit and constellation geometry drawn natively (circles, ellipses, connectors), three derived AI images (cover Earth limb, night sea scene, muted application scene) as JPEG
- **Delivery: recorded / self-running.** The first example built for unattended playback: the per-scene narration was written to `notes/total.md` before any page was drawn (video-design reference), then synthesized with MiniMax `speech-2.8-hd` / `presenter_male` into `audio/*.mp3` + word-timed `audio/*.srt` (14 pages, 6.97 min); `narration_timing.json` maps all 32 animated groups to the SRT cue that speaks about them and `narration_animations.json` is the derived click-free motion sidecar. `exports/*_narrated.pptx` embeds the narration, auto-advances every slide and carries speaker notes; `audio/total.srt` is the PPTX-timeline subtitle diagnostic
- Language: Chinese throughout (slides, narration, design spec)
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260911
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (silent deck, `animations.json` motion); add `--native-charts-and-tables` for the two editable charts, the table and the formula; for the narrated deck run `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir> --recorded-narration audio --narration-start-floor 0.8 --narration-padding 0.5` (the `narration_animations.json` sidecar is picked up automatically). Re-synthesizing the audio needs a MiniMax key and re-running `narration_sync.py fingerprint` / `animations`

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (three derived AI images; raw generations are not shipped)
- `icons/`: project icon set (tabler-outline)
- `notes/`: per-page narration script (speaker notes) and `total.md`
- `audio/`: per-page MiniMax narration (`.mp3`) with word-timed subtitles (`.srt`), plus `total.srt`
- `sources/`: topic-research facts
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard, `_native_charts_tables`, `_narrated`)

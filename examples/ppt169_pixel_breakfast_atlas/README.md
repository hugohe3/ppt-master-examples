# pixel_breakfast_atlas

- Canvas format: ppt169 (1280×720)
- Created: 20260903
- Runtime: Default Generate (Strategist → Image_Generator → Executor), topic-only input with topic research
- Mode / visual style: briefing / pixel-art (a Pokédex-style atlas: eleven numbered entry cards with HUD attribute bars, one native comparison table, a closing "atlas complete" page)
- Image system: eight AI pixel-art sheets generated in-pipeline (food, props, HUD icons, scene pieces, a player sprite in six poses, two lettering sheets) and sliced into 41 transparent sprites; three CJK pixel lettering marks (中国早餐图鉴 / 开吃！ / 图鉴完成) sit beside native editable titles; sprites are placed at or below their pixel size so the pixel edges stay crisp
- Native objects: 25 preset shapes (snip-corner HUD panels, chevron process chains, bevel buttons, stars, bracket pairs), tile floors and progress bars built from rectangles, 1 native-ready table (activated in the second export), inline emphasis; no gradients or filters by style discipline
- Facts: every attribute value cites its source year; fields without a verifiable source show NO DATA instead of an estimate
- Speaker notes on every slide; 74 entrance animations (appear / wipe only, no fades), Morph on slides 3→4 and 7→8, and three short sound cues from the bundled Kenney library (cover, spice-level switch, completion)

## Directories

- `svg_output/`: authored SVG slides (native-export source)
- `svg_final/`: self-contained preview SVGs (images embedded; rendered by the gallery viewer)
- `images/`: slide images compressed for distribution — sprites as PNG with alpha fitted to twice their rendered size (256 px floor); the generation sheets themselves are not shipped, `image_prompts.json` records every generation request including the sheets
- `sounds/`: the three sound cues referenced by `animations.json`
- `notes/`: speaker notes
- `sources/`: topic-research brief and fact provenance
- `analysis/image_analysis.csv`: image inventory the plan read
- `design_spec.md` / `spec_lock.md`: the confirmed plan and its lock
- `animations.json`: transitions, Morph pairs, sound cues, and per-object entrance choreography
- `exports/`: exported PPTX — default shape-based export, plus a `_native_charts_tables` variant where the atlas index is a PowerPoint table object

No icon library was used; the HUD sprites carry every pictorial cue on the same pixel grid.

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --with-notes
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --with-notes --native-charts-and-tables
```

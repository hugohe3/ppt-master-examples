# mid_autumn_papercut

- Canvas format: ppt169 (1280×720)
- Created: 20260902
- Runtime: Default Generate (Strategist → Image_Generator → Executor), topic-only input with topic research
- Mode / visual style: narrative / paper-cut (deep-indigo night ground instead of the preset's warm cream)
- Image system: six AI illustration sheets and two full-canvas scenes generated in-pipeline, sliced into 33 transparent cut-paper layers, three tone-matched derivatives, four CJK lettering marks (中秋 / 月夕 / 月饼 / 团圆); the moon changes phase and position across the deck and is carried by three Morph transitions
- Native objects: 9 preset shapes, 1 native-ready table (activated in the second export), inline emphasis, filters and gradients on the paper layers
- Speaker notes on every slide; 46 entrance animations across 12 slides plus Morph on slides 2, 3 and 16

## Directories

- `svg_output/`: authored SVG slides (native-export source)
- `svg_final/`: self-contained preview SVGs (images embedded; rendered by the gallery viewer)
- `images/`: slide images compressed for distribution — cut-paper slices as PNG with alpha fitted to twice their rendered size, scenes as JPEG; the generation sheets themselves are not shipped, `image_prompts.json` records every generation request including the sheets
- `notes/`: speaker notes
- `sources/`: topic-research brief and fact provenance
- `analysis/image_analysis.csv`: image inventory the plan read
- `design_spec.md` / `spec_lock.md`: the confirmed plan and its lock
- `animations.json`: transitions, Morph pairs, and per-object entrance choreography
- `exports/`: exported PPTX — default shape-based export, plus a `_native_charts_tables` variant where the mooncake-schools table is a PowerPoint table object

No icon library was used; the cut-paper slices carry every pictorial cue.

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --with-notes
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --with-notes --native-charts-and-tables
```

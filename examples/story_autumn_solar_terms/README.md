# story_autumn_solar_terms

- Canvas format: story (1080×1920, vertical)
- Created: 20260904
- Runtime: Default Generate (Strategist → Image_Generator → Executor), topic-only input with topic research
- Mode / visual style: showcase / sketch-notes (a hand-drawn autumn journal: six solar-term "stations" from Liqiu to Shuangjiang, two breathing pages on autumn colours and seasonal food, one native overview table, a sources page with live hyperlinks)
- Image system: six AI sketch sheets generated in-pipeline (term doodles, phenology motifs, seasonal food, decorations, two lettering sheets) and sliced into 30 transparent pieces; eight brush-lettered marks (cover title, six term names, a 秋 seal) sit beside native editable titles; paper grain is a native pattern fill
- Native objects: 15 preset shapes across four families (plaque, chevron, bracketPair, pie, cloudCallout, ribbon2, upArrow, foldedCorner), wobbly `<path>` outlines instead of rounded rectangles, 1 native-ready table (left as shapes in this export), 6 native hyperlinks; no gradients or filters by style discipline
- Facts: the six 2026 term dates come from the Hong Kong Observatory almanac, the eighteen 候 lines from 《月令七十二候集解》; the one field without a source (lunar-calendar correspondence) shows NO DATA instead of an estimate
- Speaker notes on every slide; 22 entrance animations across five families, Morph on slides 3→4 and 11→12, and two motion paths (the wild goose on Bailu, the frosted leaf on Shuangjiang); no sound cues
- Platform safe zone: all text stays inside y=120..1740 so story-format overlays do not cover it; illustrations and the paper ground bleed to the edges

## Directories

- `svg_output/`: authored SVG slides (native-export source)
- `svg_final/`: self-contained preview SVGs (images embedded; rendered by the gallery viewer)
- `images/`: slide images compressed for distribution — transparent slices as PNG; the generation sheets themselves are not shipped, `image_prompts.json` records every generation request including the sheets
- `icons/`: the tabler-outline icons the plan selected
- `notes/`: speaker notes
- `sources/`: topic-research brief and fact provenance
- `analysis/image_analysis.csv`: image inventory the plan read
- `design_spec.md` / `spec_lock.md`: the confirmed plan and its lock
- `animations.json`: transitions, Morph pairs, motion paths, and per-object entrance choreography
- `exports/`: exported PPTX (default shape-based export)

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --with-notes
```

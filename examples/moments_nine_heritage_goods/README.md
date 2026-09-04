# moments_nine_heritage_goods

- Canvas format: moments (1080×1080, square)
- Created: 20260904
- Runtime: Default Generate (Strategist → Image_Generator → Executor), topic-only input with topic research
- Mode / visual style: showcase / vintage-poster (a nine-post square series for a Moments grid: cover, one poster per heritage product — 回力, 永久, 光明, 上海牌, 大白兔, 英雄, 海鸥, 蝴蝶, 红灯 — ordered by birth year 1935→1972, and a sources page with live hyperlinks)
- Image system: four AI poster sheets generated in-pipeline (reduced graphic product illustrations, decorations, two lettering sheets) and sliced into 23 transparent pieces; ten brush-cut poster lettering marks (cover title and nine product names) sit beside native editable titles; the generation sheets themselves are not shipped, `image_prompts.json` records every generation request including the sheets
- Native objects: 22 preset shapes in ten kinds (triangle ray wedges, blockArc, parallelogram, plaque, frame, donut, brace …), 36 tabler-outline icons, 13 native pattern fills (paper grain and halftone), 9 hyperlinks; limited flat colour blocks with no gradients or filters by style discipline
- Facts: birth year, origin and one defining fact per product cite their sources; the two fields without a verifiable source show NO DATA on the sources page
- Speaker notes on every slide; 49 entrance animations across eight families and nine Morph pairs — the sun disc carries from the cover to the first poster and the numbered badge chains through all nine
- Export: the PPTX page size is square (10287000 × 10287000 EMU)

## Directories

- `svg_output/`: authored SVG slides (native-export source)
- `svg_final/`: self-contained preview SVGs (images embedded; rendered by the gallery viewer)
- `images/`: transparent slices as PNG fitted to twice their rendered size; `image_prompts.json` records every generation request
- `icons/`: the tabler-outline icons the plan selected
- `notes/`: speaker notes
- `sources/`: topic-research brief and fact provenance
- `analysis/image_analysis.csv`: image inventory the plan read
- `design_spec.md` / `spec_lock.md`: the confirmed plan and its lock
- `animations.json`: transitions, Morph pairs, and per-object entrance choreography
- `exports/`: exported PPTX (default shape-based export)

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --with-notes
```

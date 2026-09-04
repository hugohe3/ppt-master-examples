# a4_tea_six_classes

- Canvas format: a4 (1240×1754, portrait print)
- Created: 20260904
- Runtime: Default Generate (Strategist → Image_Generator → Executor), topic-only input with topic research
- Mode / visual style: instructional / ink-notes (a one-sheet-per-class handout: cover, a fermentation axis that seats all six classes, one page each for green, white, yellow, oolong, black and dark tea — core process, representative teas, liquor colour, water temperature and steeping time, one buying tip — and a sources page with live hyperlinks)
- Image system: two AI ink sheets generated in-pipeline (leaf and teaware motifs, six class-name lettering marks) and sliced into 15 transparent pieces; the six brush-lettered class names sit beside native editable titles; the generation sheets themselves are not shipped, `image_prompts.json` records every generation request including the sheets
- Native objects: 14 preset shapes (chevron, trapezoid, arrows, brace), 3 marker arrows, 31 tabler-outline icons; near-monochrome ink line work with one semantic colour per class (its liquor colour); no gradients, filters, shadows or paper grain by style discipline
- Facts: process, representative teas, liquor colours and brewing parameters cite their sources; three fields without a verifiable source show NO DATA and two contested temperatures are listed as such on the sources page
- Speaker notes on every slide; 50 entrance animations across seven families and seven Morph pairs — the fermentation axis carries from the overview through every class page, plus a class-identity pair on the first class page
- Export: the PPTX page size is A4 (11811000 × 16706850 EMU)

## Directories

- `svg_output/`: authored SVG slides (native-export source)
- `svg_final/`: self-contained preview SVGs (images embedded; rendered by the gallery viewer)
- `images/`: transparent slices as PNG at their generated size; `image_prompts.json` records every generation request
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

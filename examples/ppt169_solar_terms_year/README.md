# solar_terms_year

- Canvas format: ppt169 (1280×720)
- Created: 20260904
- Runtime: Default Generate (Strategist → Image_Generator → Executor), topic-only input with topic research
- Mode / visual style: instructional / soft-rounded (a year-long journal: cover, year-ring overview, four season dividers, one page per solar term, sources)
- Image system: nine AI sheets generated in-pipeline (four seasonal motif sheets, lettering sheets, ornaments) and sliced into 51 transparent pieces; 23 brush-lettered term names sit beside native titles (惊蛰 is native-only after the model misdrew the character); the generation sheets are not shipped, `image_prompts.json` records every request including the sheets
- Native objects: 121 preset shapes in thirteen kinds, 44 tabler-filled icons, one native-ready line chart (sun elevation, left as shapes in this export), six hyperlinks; soft elevation on four pages, one semantic colour per season, a radius family kept consistent across 31 pages
- Facts: dates and times from the Purple Mountain Observatory, 候 lines from 《月令七十二候集解》, customs from the China Meteorological Administration; `notes/fidelity_check.md` traces ten numbers to their sentences; no NO DATA fields
- Long-form record: `notes/longform.md` keeps per-segment page timing (1.92 / 0.61 / 0.58 min per page) and the consistency notes of the first deck over thirty pages
- 149 entrance animations across seven families and five Morph groups — the season disc and the year ring carry from each divider into its first term

## Directories

- `svg_output/`: authored SVG slides (native-export source)
- `svg_final/`: self-contained preview SVGs (rendered by the gallery viewer)
- `images/`: transparent slices as PNG fitted to twice their rendered size; `image_prompts.json` records every generation request
- `icons/`: the tabler-filled icons the plan selected
- `notes/`: speaker notes, `fidelity_check.md`, `longform.md`
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

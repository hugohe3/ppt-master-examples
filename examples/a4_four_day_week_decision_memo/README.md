# a4_four_day_week_decision_memo

- Source: topic research only (`sources/four_day_week_research.md` + `.facts.json`, 72 sourced facts from the UK 2022 four-day-week pilot report and its 2024 follow-up, the Iceland 2015–2019 trials, Belgium's 2022 law, Portugal's 2023–24 pilot and critical sources); the client firm is generic and unnamed. No images
- Style: bundled `consulting-decision` Style workspace (`templates/design_spec.style.consulting-decision.md`); pyramid mode on `swiss-minimal`
- Language: English throughout (pages, speaker notes, design spec)
- Canvas: `a4` (1240×1754 portrait, print), chosen with `project_manager.py init --format a4`; body text locked at 26 px (about 12.5 pt) for a read-close document rather than the poster-scale default, reason recorded in `design_spec.md` §IV
- Created: 20260910
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries the Morph pairs and entrances); add `--native-charts-and-tables` for the three editable charts and two tables

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (empty — the memo uses no images)
- `icons/`: project icon set (chunk-filled)
- `notes/`: speaker notes
- `templates/`: the installed Style workspace spec
- `sources/`: research supplement and fact provenance
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverable

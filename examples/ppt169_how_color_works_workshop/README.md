# ppt169_how_color_works_workshop

- Source: topic research only (`sources/how_color_works_research.md` + `.facts.json`, 36 sourced facts from W3C WCAG, NIH/NEI, CIE-derived tables and peer-reviewed papers); the demonstration specimen is Hokusai's *Under the Wave off Kanagawa* from Wikimedia Commons (public domain), bundled as the fitted JPEG derivative recorded in `images/image_sources.json`; the AI illustration sheet is not bundled — its prompts stay in `images/image_prompts.json`, the two slices and the cover (JPEG q82) in `images/`
- Style: bundled `workshop-teaching` Style workspace (`templates/design_spec.style.workshop-teaching.md`); the Style's sketch-notes preference was set aside for a quiet warm-paper grid so that the only saturated pixels on any page are the colours under examination — the reason is recorded in `design_spec.md`
- Language: English throughout (slides, speaker notes, design spec)
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260910
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries the Morph pairs and entrances); add `--native-charts-and-tables` for the editable cone-peak and CVD charts and the WCAG reference table

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (cover, two illustration slices, the fitted specimen, `image_sources.json`)
- `icons/`: project icon set
- `notes/`: speaker notes
- `templates/`: the installed Style workspace spec
- `sources/`: research supplement and fact provenance
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverable

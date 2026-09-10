# ppt169_heatline_seed_pitch

- Source: topic research only (`sources/heatline_pitch_research.md` + `.facts.json`, sourced facts from the IEA, the UK Boiler Upgrade Scheme, the US IRA 25C credit, REPowerEU and trade-body installer data); **Heatline, its product, team, customers and every traction, revenue, pipeline and financial figure are fictional and marked "illustrative" on the pages that carry them** — only the external market evidence is real. Three AI-rendered atmosphere images (JPEG q82); no illustration sheet
- Style: bundled `investor-pitch` Style workspace (`templates/design_spec.style.investor-pitch.md`)
- Language: English throughout (slides, speaker notes, design spec)
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260910
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries the Morph pairs and entrances); add `--native-charts-and-tables` for the five editable charts (including the ChartEx waterfall) and four tables

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (three AI atmosphere images)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `templates/`: the installed Style workspace spec
- `sources/`: research supplement and fact provenance
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverable

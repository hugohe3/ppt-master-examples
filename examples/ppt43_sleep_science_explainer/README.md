# ppt43_sleep_science_explainer

- Source: topic research only (`sources/sleep_science_research.md` + `.facts.json`, sourced facts from NIH/NHLBI, AASM/SRS, NHTSA, StatPearls, Nature Neuroscience, Science); no source files; AI illustration sheets are not bundled — their prompts stay in `images/image_prompts.json`, the sliced paper-cut elements in `images/`, the cover re-encoded as JPEG q82 at 1920 px
- Style: bundled `science-explainer` Style workspace (`templates/design_spec.style.science-explainer.md`); mode instructional, visual style paper-cut with the paper-cut rendering; colour carries one explanatory job for the whole talk (navy = sleep pressure, orange = light / body clock, rust = REM and risk)
- Canvas: `ppt43` (1024×768), chosen with `project_manager.py init --format ppt43`; the first 4:3 example built on the Default runtime
- Created: 20260910
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries the Morph pairs, the chart wipes and the entrances); add `--native-charts-and-tables` for editable charts and the myth table

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (cover plus seven sliced AI elements)
- `icons/`: project icon set (tabler-filled)
- `notes/`: speaker notes
- `templates/`: the installed Style workspace spec
- `sources/`: research supplement and fact provenance
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverable

# ppt169_teachers_day_chalkboard

- Source: topic research only (`sources/chalkboard_teachers_day_research.md` + `.facts.json`, 36 sourced facts from gov.cn, moe.gov.cn, People's Daily / Xinhua, UNESCO and classical texts); no source files; AI lettering and illustration sheets are not bundled — their prompts stay in `images/image_prompts.json`, the sliced chalk headlines and drawings in `images/` (scaled to about twice their rendered size)
- Style: free design on the bundled `chalkboard` visual style with the `chalkboard` rendering and a custom mode built as a classroom wall newspaper — every page is one board with a chalk-lettered masthead, a lead column, side columns and chalk borders; no Style / Brand / Layout workspace
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260910
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries the Morph pairs and entrances); add `--native-charts-and-tables` for the editable teacher-count charts and the world-dates table

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (cover lettering, twelve chalk mastheads, six chalk drawings)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `sources/`: research supplement and fact provenance
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverable

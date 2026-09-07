# ppt169_qianli_jiangshan_scroll

- Source: topic research only (`sources/qianli_jiangshan_research.md` + `.facts.json`, 19 sourced facts); the painting scans are public-domain files from Wikimedia Commons (王希孟《千里江山图》, Palace Museum, Beijing), re-encoded as JPEG q82 at their original 1600 px height because several pages crop them at source resolution; AI illustration sheets are not bundled — their prompts stay in `images/image_prompts.json`, the sliced elements in `images/`
- Style: bundled `narrative-keynote` Style workspace (`templates/design_spec.style.narrative-keynote.md`); mode custom on `narrative`, visual style custom on `ink-wash` re-coloured with azurite / malachite / ochre / cinnabar
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260907
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries the Morph pairs and entrances)

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (six scroll scans and derivatives, twelve sliced AI elements)
- `icons/`: project icon set (empty — the deck uses no bundled icons)
- `notes/`: speaker notes
- `templates/`: the installed Style workspace spec
- `sources/`: research supplement and fact provenance
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverable

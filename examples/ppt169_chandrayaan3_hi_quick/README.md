# ppt169_chandrayaan3_hi_quick

- Source: topic-only input researched inside the Quick runtime (`sources/chandrayaan3_research.md` + `.facts.json`). Facts come from ISRO mission pages and Press Information Bureau releases (2023–2024) fetched by URL through `source_to_md.py`; each figure on a page carries its source and date, and compiled framings are marked संकलन
- Style: Quick free design (no strategist, no confirmation, no spec/lock) — a blueprint look on a deep navy grid: three AI schematic illustrations (stack isometric, south-pole terrain, regolith section), a native payload table, a native cost-comparison bar chart, sixteen tabler icons
- Language: Hindi throughout (slides and speaker notes), Western digits; the face is Nirmala UI with Consolas for dates and coordinates, `lang` is hi-IN and the theme's Devanagari script slot follows the locked face
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260912
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --quick-generate --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir> --quick-generate` (the sidecar `animations.json` carries three Morph pairs and the entrances); add `--native-charts-and-tables` for the editable payload table and cost chart

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (three AI illustrations, compressed to JPEG)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `sources/`: topic-research facts
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

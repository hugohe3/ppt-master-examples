# ppt169_fire_control_room_duty_manual

- Source: topic-only input researched inside the Generate route (`sources/fire_control_room_duty_manual_research.md` + `.facts.json`), plus the national occupational standard *消防设施操作员 (2026 年版)* fetched as a PDF URL and converted through `source_to_md.py` (Markdown + profile under `sources/`). Facts cite GB 25506-2010, GB 50116-2013, the Fire Protection Law and the National Fire and Rescue Administration's 2024 fire statistics with their reference years; the four-level judgment axis is compiled for this deck and marked 整理 on the page
- Style: bundled `duty-manual` Style workspace (`templates/design_spec.style.duty-manual.md`) — dark-field hairline grid, judgment-sentence titles, mechanism before rule, a left-edge section indicator that turns to the warning colour on the counterexample page; five AI images (three full-bleed scenes under directional scrims, one white line diagram, one square counterexample visual), all derived `--fit` files
- Language: Chinese throughout (slides, speaker notes, design spec)
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260911
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries the Morph chain along the judgment axis and the entrances); add `--native-charts-and-tables` for the editable night-split chart and the handover checklist and staffing tables

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (five derived AI images; the raw generations are not shipped)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `templates/`: the installed Style workspace spec
- `sources/`: topic-research facts and the occupational-standard PDF conversion with its profile
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

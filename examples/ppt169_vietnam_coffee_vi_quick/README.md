# ppt169_vietnam_coffee_vi_quick

- Source: topic-only input researched inside the Quick runtime (`sources/vietnam_coffee_vi_quick_research.md` + `.facts.json`). Facts come from USDA FAS coffee reports (two PDFs), Báo Thanh Niên and the Đắk Lắk provincial portal, fetched by URL through `source_to_md.py`; each figure on a page carries its source and marketing year, and compiled framings are marked in Vietnamese
- Style: Quick free design (no strategist, no confirmation, no spec/lock) — a data-journalism look: sourced photographs (coffee cherries, drying beans, highland plantation, phin drip, egg coffee) with inline attribution from `images/image_sources.json` and fit derivatives, three native charts and one native table with Vietnamese labels, twelve preset shapes, three Morph keys including a chapter rail that advances between pages
- Language: Vietnamese throughout; every page root carries `lang="vi-VN"` (Quick's language channel), so runs tag vi-VN; faces are Cambria for titles and figures and Segoe UI for body, Vietnamese thousands points and decimal commas kept out of chart markers (integer ticks, figures in text and table cells)
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260912
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --quick-generate --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir> --quick-generate` (the sidecar `animations.json` carries the Morph pairs and entrances in reading order); add `--native-charts-and-tables` for the editable production/export charts, the market doughnut and the region table

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (sourced photographs and their fit derivatives, compressed to JPEG; `image_sources.json` records provenance and licences)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `sources/`: topic-research facts
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

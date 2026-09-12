# ppt169_dead_sea_scrolls_he_quick

- Source: topic-only input researched inside the Quick runtime (`sources/dead_sea_scrolls_research.md` + `.facts.json`). Facts come from the Israel Antiquities Authority, the Israel Museum (Shrine of the Book), the Leon Levy Dead Sea Scrolls Digital Library and published dating studies, fetched by URL through `source_to_md.py`; each figure on a page carries its source and year, and compiled framings are marked עיבוד
- Style: Quick free design (no strategist, no confirmation, no spec/lock) — a desert-archive look: five sourced photographs (Qumran cliffs, the Great Isaiah Scroll, a scroll jar, a fragment, the Shrine of the Book) with inline attribution from `images/image_sources.json`, one native chart, one native table, four Morph keys across the dating and conservation pages
- Language: Hebrew throughout, right-to-left; every page root carries `lang="he-IL"` (Quick's language channel), so export writes right-to-left master defaults, points the theme's Hebrew script slot at David / Segoe UI, and tags runs he-IL; Western digits and Gregorian years
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260912
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --quick-generate --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir> --quick-generate` (the sidecar `animations.json` carries the Morph pairs and right-to-left entrances); add `--native-charts-and-tables` for the editable manuscript chart and the major-scrolls table

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (five sourced photographs, compressed to JPEG; `image_sources.json` records provenance and licences)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `sources/`: topic-research facts
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

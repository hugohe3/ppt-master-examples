# ppt169_nev_export_bilingual_zh_en

- Source: topic-only input researched inside the Generate route (`sources/nev_export_2025_research.md` + `.facts.json`). Facts come from CAAM and CPCA releases, the European Commission's anti-subsidy decision, USTR tariff notices, company disclosures and industry press (2024–2026), fetched by URL through `source_to_md.py`; each figure on a page carries its source and year, both statistical calibres are labelled where they differ, and compiled framings are marked 整理
- Style: free design — a bilingual industry briefing: every page carries its Chinese line and its English line together (title + English subtitle, paired bullet lines, bilingual chart categories and table headers), stacked rather than split into columns; one AI illustration batch (ro-ro port cover, charging array, overseas plant), three native charts and two native tables, seven preset shapes
- Language: Chinese with English on every page; faces are SimSun / Cambria for titles and Microsoft YaHei / Cambria for body, Chinese runs tag zh-CN and English runs en-US; bilingual speaker notes (Chinese paragraph, then English)
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260912
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries three Morph pairs; each Chinese/English pair enters together); add `--native-charts-and-tables` for the editable export-volume, four-year-step and destination charts and the exporter and overseas-plant tables

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (three AI illustrations, compressed to JPEG)
- `icons/`: project icon set (tabler-outline)
- `notes/`: bilingual speaker notes
- `sources/`: topic-research facts
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

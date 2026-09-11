# ppt169_tokaido_shinkansen_60_ja

- Source: topic-only input researched inside the Generate route (`sources/tokaido_shinkansen_60_research.md` + `.facts.json`). Facts come from JR Central fact sheets (2026 edition), news releases (2012, 2017, 2024), the N700S vehicle page, and a 2017 Japan Society of Mechanical Engineers journal article, fetched by URL (several as PDFs) through `source_to_md.py`; each figure on a page carries its source and reference year, and the framing of the sixty years as speed, frequency, punctuality, and safety is compiled for this deck
- Style: free design — a Showa commemorative-poster look (custom mode on a narrative base, custom visual style and rendering on a vintage-poster base); four AI illustrations from one batch (arched cover poster, rounded 1964 window, a duotone derivative as the safety-chapter background, a circular crop on the next-sixty-years page)
- Language: Japanese throughout (slides, speaker notes, design spec values); faces are Yu Mincho / Times New Roman for titles and Yu Gothic / Segoe UI for body, with Arial Black for hero numbers
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260911
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries two Morph pairs and the hero entrances); add `--native-charts-and-tables` for the editable Tokyo–Osaka travel-time bar chart, the passenger-km column chart, and the rolling-stock table

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (four AI images, compressed to JPEG; the parent of the duotone derivative is not shipped)
- `icons/`: project icon set (chunk-filled)
- `notes/`: speaker notes
- `sources/`: topic-research facts
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

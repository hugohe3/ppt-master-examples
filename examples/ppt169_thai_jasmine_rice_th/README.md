# ppt169_thai_jasmine_rice_th

- Source: topic-only input researched inside the Generate route (`sources/thai_jasmine_rice_research.md` + `.facts.json`). Facts come from the Thai Rice Department and Department of Intellectual Property (GI registration), the Thai Rice Exporters Association, the Office of Agricultural Economics, USDA and FAO publications, and the World Rice Conference award records, fetched by URL through `source_to_md.py`; each figure on a page carries its source and year, years are written in the Buddhist calendar with the conversion stated, and compiled framings are marked in Thai
- Style: free design — a vintage-poster editorial look (custom mode on narrative + instructional bases, custom visual style on editorial + vintage-poster bases): flat-colour halftone illustrations from one AI batch (dawn paddy, Isan basin, grain and aroma, export port, farmer's hands), a chevron roadmap, native charts and tables
- Language: Thai throughout (slides, speaker notes, design spec values), Western digits; faces are Leelawadee UI for titles and body and Tahoma for data and footnotes, `lang` is th-TH and the theme's Thai script slot follows the locked face
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260912
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries three Morph pairs and the hero entrances); add `--native-charts-and-tables` for the editable five-year export line chart, the buyer-share doughnut, and the two comparison tables

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (five AI illustrations, compressed to JPEG)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `sources/`: topic-research facts
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

# ppt169_russia_demography_ru

- Source: ten World Bank indicator CSV files as the only data source (`sources/API_*.csv`, downloaded from the World Bank API; `sources/ru_demography_slice.csv` and `ru_demography_facts.md` are the sliced subset and the facts read from it). Every figure on a page carries the indicator code and year; no fact comes from outside the CSVs
- Style: free design — a data briefing: nine native charts (population line, births/deaths cross, natural change and migration columns, fertility, life expectancy by sex, ageing, urbanisation, five-country comparison), two native tables, one native formula, two AI images (cover field, closing band), wedge callouts on the chart annotations; three Morph pairs carry the hero figure and the period markers between pages
- Language: Russian throughout; faces are Times New Roman for titles and figures, Arial for body and Consolas for data anchors, `lang` is ru-RU; Russian number style (space thousands, decimal comma) in text and table cells, integer axis ticks inside the charts
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260912
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries three Morph pairs and the entrances); add `--native-charts-and-tables` for the nine editable charts and two tables

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (two AI images, compressed to JPEG)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `sources/`: World Bank indicator CSVs, the sliced subset and the facts file
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

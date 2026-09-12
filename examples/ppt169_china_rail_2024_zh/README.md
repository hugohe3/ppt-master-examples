# ppt169_china_rail_2024_zh

- Source: user-supplied materials only — the National Railway Administration's 2024 railway statistical bulletin (`sources/railway_bulletin_2024.pdf`, nine pages with three tables, converted to `railway_bulletin_2024.md`), a World Bank rail route-km spreadsheet for eight countries (`sources/rail_route_km_worldbank.xlsx`), and six Wikimedia Commons CC photos with `sources/credits.tsv`. Every figure comes from the attachments; no AI image was generated
- Style: free design — a custom mode (pyramid + briefing) over a custom data-journalism / swiss-minimal / photo-editorial style: dense white data pages with square containers and hairline rules alternate with dark full-bleed scene pages; one photo derived as a washed variant (`fuxing_train_wash.jpg`); six native charts, two native tables, six preset shapes; every photo credited under CC BY / CC BY-SA with its Commons link; three Morph pairs carry the hero photo and hero figure between pages
- Language: Chinese throughout; faces are SimHei for titles and Microsoft YaHei for body, `lang` is zh-CN
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260912
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries three Morph pairs and the entrances); add `--native-charts-and-tables` for the six editable charts and two tables

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (the six CC photos and one derivative, compressed to JPEG)
- `icons/`: project icon set (chunk-filled)
- `notes/`: speaker notes
- `sources/`: the bulletin PDF and its Markdown, the World Bank spreadsheet and its Markdown, the six photos and `credits.tsv`
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

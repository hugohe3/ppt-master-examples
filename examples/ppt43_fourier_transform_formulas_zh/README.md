# ppt43_fourier_transform_formulas_zh

- Source: topic-only input researched inside the Generate route (`sources/fourier_transform_research.md` + `.facts.json`). Historical facts (Fourier 1807/1822, Cooley–Tukey 1965, JPEG T.81 1992, 802.11a 1999) and the mathematics carry their sources; every derivation on a page is the deck's own compilation
- Style: free design on a 4:3 canvas — a lecture-handout look (custom mode on instructional + briefing bases, custom visual style on swiss-minimal + editorial + data-journalism bases): full-width formula bands with a brass rule, hairline dividers, one AI illustration on the cover; **48 native Office Math formulas** (17 display blocks, 31 inline runs, 8 of them inside the transform-pair grid), one native column chart, twenty-one preset shapes
- Language: Chinese throughout; faces are SimSun / Cambria for titles, Microsoft YaHei / Cambria for body, Cambria Math for every formula, `lang` is zh-CN
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260912
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (formulas are always native; the sidecar `animations.json` carries two Morph pairs — one morphs the series coefficient into the transform integral — and entrances in reading order); add `--native-charts-and-tables` for the editable harmonic-amplitude column chart

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (one AI illustration, compressed to JPEG; its uncropped parent is not shipped)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `sources/`: topic-research facts
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

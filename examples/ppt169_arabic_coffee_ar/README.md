# ppt169_arabic_coffee_ar

- Source: topic-only input researched inside the Generate route (`sources/arabic_coffee_ar_research.md` + `.facts.json`). Facts come from the UNESCO Intangible Cultural Heritage pages for Arabic coffee (2015, extended 2024) and Khawlani coffee (2024), the Department of Culture and Tourism – Abu Dhabi gahwa page and booklet, the Saudi Ministry of Environment, Water and Agriculture, the Saudi Press Agency and the General Authority for Statistics, fetched by URL (two as PDFs) through `source_to_md.py`; each figure on a page carries its source and year, and compiled framings are marked تنظيم
- Style: free design — a majlis-hospitality editorial look (custom mode on narrative + instructional bases, custom visual style on editorial + photo-editorial bases): a thin brass vertical rule on the right, large Naskh titles, arched and circular photo windows, low-light still-life photography; six AI photographs from one batch plus two derivatives (a duotone terrace background, a darkened blur behind the closing page)
- Language: Arabic throughout (slides, speaker notes, design spec values), right-to-left reading order with Western digits; faces are Times New Roman for titles and Segoe UI for body, `lang` is ar-SA and paragraphs export with `rtl="1"`
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260911
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries two Morph pairs and the hero entrances); add `--native-charts-and-tables` for the editable coffee-production bar chart and the roast-by-region table

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (eight AI images, compressed to JPEG)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `sources/`: topic-research facts
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

# ppt169_jeju_haenyeo_ko

- Source: topic-only input researched inside the Generate route (`sources/jeju_haenyeo_ko_research.md` + `.facts.json`). Facts come from the Jeju Haenyeo Museum, Jeju Special Self-Governing Province haenyeo statistics, the Korea Heritage Service, a Jeju provincial council PDF, and UNESCO and FAO pages, fetched by URL through `source_to_md.py`; each figure on a page carries its source and year, and compiled framings are marked 정리
- Style: free design — "a record of depth" (custom mode on a narrative base, custom visual style on an editorial base, custom screen-print image rendering): a waterline runs through the deck; five AI illustrations from one batch, figures only from behind or in silhouette, with a duotone derivative, a dimmed derivative, a circular crop, and directional washes
- Language: Korean throughout (slides, speaker notes, design spec values), `ko-KR` in the lock and the exported package; Batang for titles and Malgun Gothic for body (Batang ships with Korean Windows and is an optional supplemental font elsewhere)
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260911
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries the hero entrances and two Morph pairs); add `--native-charts-and-tables` for the editable diver-count, age-mix, and entrants-versus-departures charts and the heritage-designation table

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (six placed images compressed to JPEG; the parent of the duotone derivative is not shipped)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `sources/`: topic-research facts
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

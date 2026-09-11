# ppt169_taiwan_super_aged_society_zh_hant

- Source: the National Development Council's *中華民國人口推估（2026年至2075年）* (released 2026-08-28), fetched as PDF URLs — the full report and the press release — through `source_to_md.py` (Markdown plus conversion profiles with their source URLs under `sources/`), with the council's five-year age-by-sex open data (`sources/ndc_popproj_5yr_age_sex_1980_2026_2075.csv`) and topic research (`taiwan_super_aged_research.md` + `.facts.json`). Every figure carries its source and year, projections name the medium variant, Minguo years are converted to the Western calendar, and the compiled framings are marked 整理 on the page
- Style: free design — "scale and evidence": a navy data-journalism layout on warm white paper with a time-scale ruler as the cross-page motif and brick red reserved for thresholds and the older population; three AI illustrations from one batch (a duotone cover derivative, a circular crop, an arched crop)
- Language: Traditional Chinese (Taiwan) throughout (slides, speaker notes, design spec values), `zh-Hant-TW` in the lock and `zh-TW` in the exported package; Microsoft JhengHei for Chinese with Segoe UI for Latin
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260911
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries the Morph along the time-scale ruler, the population-pyramid Morph between 2026 and 2075, and the entrances); add `--native-charts-and-tables` for the editable births-versus-deaths line, dependency-ratio and working-age charts and the international comparison table

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (three AI images, compressed to JPEG; the parent of the duotone derivative is not shipped)
- `icons/`: project icon set (tabler-filled)
- `notes/`: speaker notes
- `sources/`: the report and press-release conversions with their profiles, the age-by-sex CSV, and topic-research facts (the source PDFs are not shipped)
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

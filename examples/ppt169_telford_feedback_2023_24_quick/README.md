# ppt169_telford_feedback_2023_24_quick

- Source: Telford & Wrekin Council's public *Corporate Feedback Report 2023/24* (`https://www.telford.gov.uk/media/iyaj4b1z/corporate_feedback_report_2023_24.docx`), shipped as `sources/telford_corporate_feedback_2023_24.docx` with its `doc_to_md` conversion — the Markdown includes the cached data of the twelve Word charts embedded in the report, where most of its numbers live. Every figure on a page comes from the report; two internal inconsistencies are flagged on the page
- Runtime: Quick (explicit "quick mode, skip the strategy step"), so there is no design spec or lock; a paper-toned hairline layout with a snipped-corner motif, conclusion titles, and the cover's EMF logo passed through as a vector
- Language: English; speaker notes disabled
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260911
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --quick-generate --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir> --quick-generate --no-notes` (the sidecar `animations.json` carries 29 entrances and the cover-to-overview Morph); add `--native-charts-and-tables` for the five editable charts and two tables

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: the cover logo extracted from the report (EMF)
- `sources/`: the original DOCX, its Markdown conversion, and conversion profile
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

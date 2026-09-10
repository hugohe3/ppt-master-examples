# ppt169_every_day_counts_proposal

- Source: mixed real sources under `sources/` — ERIC ED617466 *Framework for Action: Addressing Chronic Absenteeism through ESSA Implementation* (PDF + its Markdown conversion and profile), two NYC Open Data end-of-year attendance and chronic-absenteeism CSVs (`sgsi-66kk`, `hags-jh3e`; read directly, aggregated student-weighted with the grouping stated on each page), and the gov.uk *Working together to improve school attendance* guidance page (Markdown conversion). **Lantern Education Partners, Riverbend Unified and every price, headcount, timeline commitment and projected effect are fictional and marked illustrative on the page**; the problem evidence is real and sourced
- Style: bundled `solution-proposal` Style workspace (`templates/design_spec.style.solution-proposal.md`) on `soft-rounded`; three AI-rendered atmosphere images (JPEG q82)
- Language: English throughout (slides, speaker notes, design spec)
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260910
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries the Morph pairs and entrances); add `--native-charts-and-tables` for the four editable charts (line, column, area, waterfall) and two tables

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (three AI atmosphere images)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `templates/`: the installed Style workspace spec
- `sources/`: the PDF, the two CSVs, the gov.uk page conversion and their profiles
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverable

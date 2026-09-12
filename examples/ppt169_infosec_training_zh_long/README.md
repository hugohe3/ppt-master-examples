# ppt169_infosec_training_zh_long

- Source: none supplied beyond the brief (a 26–30 page new-employee information-security awareness course). Facts came through topic research (`sources/infosec_training_zh_research.md` + `.facts.json`): the 2025 revision of the Cybersecurity Law, the Data Security Law, the Personal Information Protection Law and public case notices; every page carries a source line
- Style: free design — a custom mode (instructional + pyramid) over a custom editorial / swiss-minimal / data-journalism style: paper-toned ground, ink-dark chapter pages with oversized numerals, a seal-red accent; the eyebrow, dossier rail and footer sit at fixed coordinates on all twenty-eight pages; five chapters with divider pages, a contents page listing each chapter's starting page, and a closing quiz; four native charts, five native tables, twenty preset shapes, no images by style choice; six Morph pairs at the chapter boundaries
- Language: Chinese throughout; faces are SimSun for titles and Microsoft YaHei for body, `lang` is zh-CN
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260912
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries six Morph pairs and the entrances); add `--native-charts-and-tables` for the four editable charts and five tables

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: empty — the deck uses no images
- `icons/`: project icon set (chunk-filled)
- `notes/`: speaker notes
- `sources/`: topic-research pair
- `analysis/`: image_analysis.csv (no rows — the deck uses no images)
- `exports/`: final native DrawingML pptx deliverables (standard and `_native_charts_tables`)

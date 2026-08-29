# china_telecom_2025

- Canvas format: ppt169
- Created: 20260829
- Runtime: Quick Generate with the bundled `中国电信` Deck template (structured Master/Layout export)

## Directories

- `svg_output/`: authored SVG slides (native-export source; every page declares the installed Master/Layout/slot contract)
- `svg_final/`: self-contained preview SVGs (images and icons embedded; rendered by the gallery viewer)
- `templates/`: the installed Deck workspace spec and its five prototype pages
- `images/`: template brand assets referenced by the Master/Layout atoms
- `icons/`: project-local icons referenced by the slides
- `notes/`: speaker notes
- `sources/`: source material
- `animations.json`: section-page push transitions and per-object entrance choreography
- `exports/`: exported PPTX — `china_telecom_2025.pptx` (shape fallback) and `china_telecom_2025_native_charts_tables.pptx` (P07 bar chart as a native PowerPoint chart)

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --quick-generate --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate --with-notes
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate --with-notes --native-charts-and-tables
```

# wave_interference_diffraction

- Canvas format: ppt43 (1024×768)
- Created: 20260829
- Runtime: Quick Generate
- Mode / visual style: instructional / chalkboard
- Native objects: 5 editable OMML formulas (block + inline), 1 native-ready table (activated in the second export)

## Directories

- `svg_output/`: authored SVG slides (native-export source)
- `svg_final/`: self-contained preview SVGs (images embedded; rendered by the gallery viewer)
- `images/`: slide images (compressed for distribution); `image_sources.json` records provenance and licenses
- `icons/`: project-local icons referenced by the slides
- `notes/`: speaker notes
- `sources/`: research supplement and fact provenance
- `animations.json`: transition and object-animation configuration (click-to-reveal on the superposition, conditions, slit-width and practice pages)
- `exports/`: exported PPTX — default shape-based export, plus a `_native_charts_tables` variant where the summary table is a PowerPoint table object

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --quick-generate --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate --with-notes
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate --with-notes --native-charts-and-tables
```

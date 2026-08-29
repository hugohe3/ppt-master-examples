# kubernetes_blueprint_2026

- Canvas format: ppt169
- Created: 20260828
- Runtime: Quick Generate

## Directories

- `svg_output/`: authored SVG slides (native-export source)
- `svg_final/`: self-contained preview SVGs (images embedded; rendered by the gallery viewer)
- `images/`: slide images (compressed for distribution)
- `icons/`: project-local icons referenced by the slides
- `notes/`: speaker notes
- `sources/`: source material
- `animations.json`: transition and object-animation configuration
- `exports/`: exported PPTX (with speaker notes and animations)

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --quick-generate --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate --with-notes
```

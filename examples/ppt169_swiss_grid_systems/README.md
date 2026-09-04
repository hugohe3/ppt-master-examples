# swiss_grid_systems

- Canvas format: ppt169 (1280×720)
- Created: 20260517 — generated on the Default runtime of May 2026; **adapted on 2026-09-04 to the current authoring rules without regenerating** (see below)
- Runtime: Default Generate (Strategist → Image_Generator → Executor) from a design-history lecture outline
- Visual style: Swiss International Typographic Style lecture (Müller-Brockmann homage, red / black / white, exposed grid); this deck predates the mode / visual-style catalogs, so `spec_lock.md` carries no `mode` or `visual_style` section
- Image system: 3 AI images generated in-pipeline (cover, negative-space study, closing grid)
- Native objects: 6 simple-icons brand marks; 95 entrance animations (fade / split / wipe)
- Speaker notes on every slide (14 pages)

## 2026-09 adaptation

The slides are the May 2026 output. To keep the package regenerable with the current pipeline, only metadata and packaging were changed — no visible geometry was edited:

- `spec_lock.md`: added the `## communication` and `## pptx_structure` (`mode: flat`) sections, and declared the recurring display sizes as named typography roles
- `design_spec.md` §IX: added the `Audience move` and `Relationships` line to every slide block
- `icons/`: the referenced library icons are now shipped with the project
- `images/`: RGB PNGs converted to JPEG (quality 82) and unreferenced files dropped; every `href` and spec reference updated
- PPTX re-exported with the current `svg_to_pptx.py`; `svg_final/` regenerated with `finalize_svg.py`

## Directories

- `svg_output/`: authored SVG slides (native-export source)
- `svg_final/`: self-contained preview SVGs (images embedded; rendered by the gallery viewer)
- `images/`: slide images compressed for distribution
- `icons/`: project-local copies of the library icons the slides reference
- `notes/`: speaker notes
- `analysis/image_analysis.csv`: image inventory the plan read (where present)
- `design_spec.md` / `spec_lock.md`: the confirmed plan and its lock
- `animations.json`: per-object entrance choreography
- `exports/`: exported PPTX

The original source material was not retained when this deck was archived; `notes/` and `design_spec.md` §IX carry the full content.

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> -o <this_dir>/exports/swiss_grid_systems.pptx
```

# midautumn_moon_quick

- Canvas format: moments (1080×1080, square card)
- Created: 20260923
- Runtime: Quick Generate from a bare topic with topic research, on the bundled `moments_square` Layout template (all eight prototypes used once, redrawn as a dark night sky; structured Master/Layout export)
- Mode / visual style: instructional / custom "moonlit star chart" — deep navy field, warm moon-gold reserved for key figures and words
- Image system: three AI images generated in-pipeline — a 3×3 colour-key sheet sliced into eight transparent moon phases plus an osmanthus sprig, an illustrated city moonrise (labelled as an illustration) and a full-moon close-up; the key sheet itself is not shipped, its prompt stays in `image_prompts.json`
- Native objects: one `moon` preset shape; facts cite Purple Mountain Observatory, Guangzhou Wuyang Planetarium, Nanjing Daily and NASA on the cards
- Object animations on all eight cards and three Morph pairs (`moon-hero` carries 01→02→03→04); Chinese speaker notes

## Directories

- `svg_output/`, `svg_final/`, `images/`, `notes/`, `sources/`, `templates/`, `analysis/`, `animations.json`, `exports/` as in the other examples; no spec or lock (Quick runtime)

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --quick-generate --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate
```

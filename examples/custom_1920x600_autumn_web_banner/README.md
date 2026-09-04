# autumn_web_banner_set

- Canvas format: custom 1920×600 (viewBox `0 0 1920 600` on every page; not a registered format) — the first custom-canvas example; the exported PPTX page is 1920×600
- Created: 20260904
- Runtime: Quick Generate, user-supplied image material — the slices of the autumn journal example imported with `import-sources --copy`; no new AI generation
- Mode / visual style: showcase / sketch-notes (an overview banner plus one per autumn term), laid out horizontally for the wide format
- Typography: scaled from the short edge per canvas-formats (body 52, title 88, display 120)
- Image system: 27 transparent slices placed at or below their native size
- Native objects: 16 preset shapes across four families, a `pct5` paper-grain pattern on every page; no gradients or filters by style discipline
- 56 entrance animations and twelve Morph pairs — the route spine and the autumn seal carry through all seven banners

## Directories

- `svg_output/`, `svg_final/`, `images/`, `sources/`, `animations.json`, `exports/` as in the other examples; no spec or lock (Quick runtime)

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --quick-generate --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate --no-notes
```

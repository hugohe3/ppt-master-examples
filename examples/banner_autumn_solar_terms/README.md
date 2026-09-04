# autumn_banner_set

- Canvas format: banner (1920×1080)
- Created: 20260904
- Runtime: Quick Generate, user-supplied image material — the slices of the autumn journal example (`story_autumn_solar_terms`) imported with `import-sources --copy`; no new AI generation
- Mode / visual style: showcase / sketch-notes (an overview banner plus one banner per autumn term: 立秋 处暑 白露 秋分 寒露 霜降)
- Image system: 29 transparent slices (term doodles, phenology motifs, lettering, ornaments), the largest placed at 1.19× its native size
- Native objects: 10 preset shapes across four families, a native `pct5` paper-grain pattern on every page, wobbly `<path>` routes; no gradients or filters by style discipline
- 44 entrance animations and twelve Morph pairs — the route line and the autumn seal carry through all seven banners

## Directories

- `svg_output/`, `svg_final/`, `images/`, `icons/`, `sources/`, `animations.json`, `exports/` as in the other examples; no spec or lock (Quick runtime)

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --quick-generate --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate --no-notes
```

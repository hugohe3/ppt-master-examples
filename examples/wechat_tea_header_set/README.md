# tea_header_set

- Canvas format: wechat (900×383, article header)
- Created: 20260904
- Runtime: Quick Generate, user-supplied image material — the slices of the tea handout example (`a4_tea_six_classes`) imported with `import-sources --copy`; no new AI generation
- Mode / visual style: instructional / ink-notes (an overview header plus one header per tea class: green, white, yellow, oolong, black, dark)
- Image system: 15 transparent slices (six leaf motifs, three teaware pieces, six brush-lettered class names) placed at or below their native size beside native titles
- Native objects: 14 preset shapes, one semantic liquor-colour dot per class, callouts for the two classes whose liquor colour shows NO DATA; no gradients, filters or paper grain by style discipline
- 34 entrance animations and twelve Morph pairs — the fermentation axis and the gaiwan carry through all seven headers; no speaker notes

## Directories

- `svg_output/`, `svg_final/`, `images/`, `icons/`, `sources/`, `animations.json`, `exports/` as in the other examples; no spec or lock (Quick runtime)

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --quick-generate --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate --no-notes
```

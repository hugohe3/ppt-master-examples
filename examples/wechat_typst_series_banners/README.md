# typst_series_banners

- Canvas format: wechat (900×383, article header)
- Created: 20260923
- Runtime: Default Generate from five `.typ` chapters of the typst-doc-cn tutorial (Apache-2.0; `sources/LICENSE_head.*`)
- Mode / visual style: custom series-identity set / custom "proof table" on a Swiss grid — crop marks, a hairline baseline grid, proofreader-red insert cursor, ink-black code strips in monospace, serif display titles; flat, no images
- Six headers: a series cover, one banner per chapter (introduction, markup, math, Chinese typesetting) with a verbatim source snippet beside its typeset result, and a follow call-to-action closing the four-part route
- Native objects: the math banner carries its formula as a native PowerPoint equation
- Object animations and ten Morph pairs on two keys (the series name shrinks from display size to a running head, and the red cursor becomes the chapter-rail marker that moves forward banner by banner); Chinese speaker notes

## Directories

- `svg_output/`, `svg_final/`, `notes/`, `sources/`, `animations.json`, `design_spec.md`, `spec_lock.md`, `exports/` as in the other examples; no images or icons

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir>
```

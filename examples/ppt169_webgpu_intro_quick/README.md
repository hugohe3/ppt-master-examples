# webgpu_intro_quick

- Canvas format: ppt169 (1280×720)
- Created: 20260904
- Runtime: Quick Generate (no Strategist, confirmation, spec, or lock), source-driven — the input is the MDN "WebGPU API" overview page fetched with `source_to_md.py`; the deck is written in Chinese with the API terms kept in English
- Mode / visual style: instructional / dark-tech (an engineer's primer: why WebGPU exists, the browser-to-GPU stack, adapter → device, core versus compatibility mode, the two pipeline kinds, vertex and fragment stages with WGSL, the five steps of an app, a render pass read line by line, moving compute results back to JavaScript, error scopes, support status)
- Native objects: 32 preset shapes in eleven kinds (chevron, arrows, hexagon, plaque, snip rectangles, bracket pair, callout), 19 tabler-outline icons, 7 code blocks on 6 pages as editable Consolas text; gradients, three filters and two text effects carry the dark-tech surface; no images by design — the source page's only bitmap (a stack diagram) is redrawn as native SVG and doubles as a Morph endpoint
- Facts: everything comes from the one MDN page; the browser compatibility table is script-rendered and could not be fetched, so version numbers and the compatibility-mode limit list show NO DATA
- 36 entrance animations across eight families and three Morph pairs (stack layer 3→4, render pipeline 6→7, code panel 9→10); no speaker notes, no sound

## Directories

- `svg_output/`: authored SVG slides (native-export source)
- `svg_final/`: self-contained preview SVGs (rendered by the gallery viewer)
- `icons/`: the tabler-outline icons the deck uses
- `sources/`: the converted MDN page
- `animations.json`: transitions, Morph pairs, and per-object entrance choreography
- `exports/`: exported PPTX (default shape-based export)

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --quick-generate --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate --no-notes
```

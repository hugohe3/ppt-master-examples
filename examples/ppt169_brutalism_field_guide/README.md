# brutalism_field_guide

- Canvas format: ppt169 (1280×720)
- Created: 20260904
- Runtime: Default Generate (Strategist → Image_Searcher → Executor), source-driven — the input is the English Wikipedia article "Brutalist architecture" (CC BY-SA), fetched with `source_to_md.py`; the deck is written in English
- Mode / visual style: narrative / brutalist (a brutalist newspaper: wall-to-wall small type, irregular columns, heavy rule lines, one inverted ink cell per spread, a rotated stamp box, oversized masthead numerals)
- Typography: Arial Black headlines and numerals, Cambria body, Consolas labels — single named faces; calibrated with the Latin, CAPS and DIGITS rates
- Photographs: four (Wikimedia Commons ×3, Pexels ×1), each passed through `image_treat.py` (contrast, duotone into the deck ink and paper) and a hard ruled crop, with inline CC BY-SA credits; `images/image_sources.json` records provenance; twelve pages carry no photo by design
- Native objects: two native-ready tables (left as shapes in this export), three preset shapes, one halftone pattern fill; no gradients or filters
- Facts: everything is quoted from the one article; `notes/fidelity_check.md` traces ten claims; five fields the article does not give show NO DATA
- Speaker notes on every slide; 58 entrance animations across eight families and two Morph pairs (masthead numeral 2→3, section rule 14→15)

## Directories

- `svg_output/`: authored SVG slides (native-export source)
- `svg_final/`: self-contained preview SVGs (rendered by the gallery viewer)
- `images/`: the four treated photographs plus `image_manifest.json` and `image_sources.json`
- `notes/`: speaker notes and `fidelity_check.md`
- `sources/`: the converted article
- `analysis/image_analysis.csv`: image inventory the plan read
- `design_spec.md` / `spec_lock.md`: the confirmed plan and its lock
- `animations.json`: transitions, Morph pairs, and per-object entrance choreography
- `exports/`: exported PPTX (default shape-based export)

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --with-notes
```

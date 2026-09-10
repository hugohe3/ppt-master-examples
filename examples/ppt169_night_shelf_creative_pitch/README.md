# ppt169_night_shelf_creative_pitch

- Source: topic research only (`sources/night_shelf_research.md` + `.facts.json`, sourced reading and screen-time facts from Pew Research Center, the NEA Survey of Public Participation in the Arts, the National Literacy Trust and peer-reviewed sleep research); **Fog & Fern Books, its figures and this campaign are fictional and say so on the cover, in the notes and in the appendix** — only the audience-truth evidence is real. AI-rendered hero, poster, social and in-store artwork (JPEG q82), three derivatives of the hero from `image_treat.py`, six element slices; the generation sheet is not bundled — its prompts stay in `images/image_prompts.json`
- Style: bundled `creative-pitch` Style workspace (`templates/design_spec.style.creative-pitch.md`); the campaign's own identity (Georgia display, lamplight gold as a light colour never a type colour, a crescent mark as native preset) is demonstrated by the deck's pages; no text picture fill anywhere — every title is solid-colour type
- Language: English throughout (slides, speaker notes, design spec)
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260910
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries the Morph pairs and entrances); add `--native-charts-and-tables` for the editable audience chart and production table

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (four artworks, three hero derivatives, six element slices)
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `templates/`: the installed Style workspace spec
- `sources/`: research supplement and fact provenance
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverable

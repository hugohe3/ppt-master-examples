# ppt169_raft_consensus_deepdive

- Source: one PDF, `sources/raft.pdf` — Diego Ongaro and John Ousterhout, "In Search of an Understandable Consensus Algorithm (Extended Version)", Stanford University, 2014 (raft.github.io); converted to `sources/raft.md` with `source_to_md.py`. Every number and mechanism on the deck traces to the paper; the AI illustration sheet is not bundled — its prompts stay in `images/image_prompts.json`, the four isometric slices and the cover (JPEG q82) in `images/`
- Style: bundled `technical-deepdive` Style workspace (`templates/design_spec.style.technical-deepdive.md`) applied on the Quick runtime — the first Quick deck that installs a Style; visual style `blueprint` with the `3d-isometric` rendering for hardware and storage imagery, every mechanism diagram drawn as native SVG geometry
- Canvas is determined during authoring and recorded in the first SVG (Quick).
- Created: 20260910
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --quick-generate --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir> --quick-generate` (the sidecar `animations.json` carries the Morph pairs and entrances); add `--native-charts-and-tables` for the editable study charts and the RPC table

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (cover plus four isometric slices)
- `icons/`: project icon set (tabler-outline)
- `templates/`: the installed Style workspace spec
- `sources/`: the paper PDF and its Markdown conversion
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverable

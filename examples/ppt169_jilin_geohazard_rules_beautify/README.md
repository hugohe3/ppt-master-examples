# ppt169_jilin_geohazard_rules_beautify

- Source: the Jilin Department of Natural Resources' public policy briefing on the *吉林省地质灾害治理工程项目管理办法* (`http://zrzy.jl.gov.cn/zwgk/fgwj/zcjd/202403/P020241111329480622821.pptx`). **The original deck ships as `sources/jilin_geohazard_project_rules_policy.pptx`** for a before-and-after comparison, with its `ppt_to_md` conversion (the frozen content contract) beside it
- Profile: Beautify PPTX 1:1 on the Default runtime — page count and order kept, every word kept (a two-channel read-back of the export against the source finds nothing missing or added), run-level red/blue emphasis carried over in the deck's blue and accent red; the seven-chapter framework redrawn as editable chevrons, numbered tracks for the intake steps and acceptance stages, and all eight source pictures reused and re-laid-out
- Language: Chinese throughout; speaker notes disabled (the source notes held only page numbers)
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260911
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir> --no-notes` (the sidecar `animations.json` carries 69 hero entrances and the chapter-tag Morph across four page pairs)

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: the source deck's pictures, reused unchanged, with `image_manifest.json` binding them to source slides
- `icons/`: project icon set
- `sources/`: the original PPTX, its Markdown conversion and conversion profile
- `analysis/`: `beautify_inventory.json` (per-slide frozen ledger with ignored / needs-confirmation decisions) and `image_analysis.csv`
- `exports/`: the beautified native DrawingML pptx

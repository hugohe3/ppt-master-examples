# ppt169_dujiangyan_zh_sparse

- Source: none supplied — the whole user request was one sentence, 「帮我做一个介绍都江堰的PPT」. Facts came through topic research (`sources/dujiangyan_research.md` + `.facts.json`, with the seven fetched pages converted beside them: UNESCO World Heritage Centre, People's Daily, Sichuan Online, China News, the Water Civilisation site and two irrigation-district reports); every page carries its citation
- Style: free design — audience, page count, canvas and direction were all decided by the Strategist and justified in `design_spec.md` §I; a custom mode (instructional + narrative) over a custom blueprint / data-journalism style: dark ground, hairline frames, leader lines, dimension brackets, one warm accent for the part being explained; two web photos full-bleed and darkened (`images/image_sources.json` records the Pixabay and Wikimedia Commons CC BY-SA provenance, the Commons photo credited on its page); two native charts, one native table, six preset shapes; three Morph pairs carry the hero figure between pages
- Language: Chinese throughout; faces are SimHei for titles and Microsoft YaHei for body with Consolas for figures, `lang` is zh-CN
- Canvas is determined during authoring and recorded in spec_lock.md (Default) or the first SVG (Quick).
- Created: 20260912
- Regenerate: `python3 skills/ppt-master/scripts/svg_quality_checker.py <this dir> --canonical-authoring --stage final --json`, then `python3 skills/ppt-master/scripts/svg_to_pptx.py <this dir>` (the sidecar `animations.json` carries three Morph pairs and the entrances)

## Directories

- `svg_output/`: raw SVG output
- `svg_final/`: self-contained SVG visual preview; may be inserted manually as an SVG image, but PowerPoint Convert to Shape is unsupported
- `images/`: runtime image pool (two web photos, compressed to JPEG) and `image_sources.json`
- `icons/`: project icon set (tabler-outline)
- `notes/`: speaker notes
- `sources/`: topic-research pair and the converted web pages
- `analysis/`: image_analysis.csv
- `exports/`: final native DrawingML pptx deliverable

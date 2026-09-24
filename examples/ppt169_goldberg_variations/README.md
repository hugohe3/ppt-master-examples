# goldberg_variations

- Canvas format: ppt169 (1280×720)
- Created: 20260923
- Runtime: Default Generate (Strategist → Image_Generator → Executor) from a bare topic with topic research; free design
- Mode / visual style: a guided listening talk for listeners with no music theory, in a custom engraving style — cream paper, copperplate line work, crimson and navy accents, serif display titles
- Structure diagrams drawn natively: the 1 + 30 + 1 arch, the ten groups of three with every third a canon, the canon staircase from unison to the ninth, two-voice staves, the 32-bar bass line, and the Variation 16 midpoint axis
- Images: two AI engraving-style illustrations (the arch cover and an empty studio labelled as not a historical photo) and two public-domain Wikimedia scans (Haussmann's 1746 portrait of Bach and the 1741 title page), recorded in `images/image_sources.json`
- Native objects: the Gould 1955 / 1981 comparison is a native PowerPoint table; recording durations are left out because no authoritative source was found
- Object animations and three Morph transitions on two keys (the arch becomes the group grid; the canon row becomes the staircase and then its thumbnail); Chinese speaker notes

## Directories

- `svg_output/`, `svg_final/`, `images/`, `icons/`, `notes/`, `sources/`, `analysis/`, `animations.json`, `design_spec.md`, `spec_lock.md`, `exports/` as in the other examples

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir>
```

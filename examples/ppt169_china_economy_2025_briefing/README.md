# china_economy_2025_briefing

- Canvas format: ppt169 (1280×720)
- Created: 20260904
- Runtime: Default Generate (Strategist → Image_Generator → Executor), source-driven — the input is the National Bureau of Statistics communiqué on 2025 national economic and social development (official web page, converted with `source_to_md.py`); no topic research
- Mode / visual style: briefing / data-journalism (a reader-led data briefing: GDP and growth, industry structure, demand contribution, population, employment and income, consumption, investment, foreign trade, energy, innovation, livelihood, key takeaways, sources)
- Native objects: 10 native-ready charts in six types (column ×3, bar ×3, line, doughnut, pie, waterfall) and 3 native-ready tables, all activated in the second export; 7 preset shapes; 16 tabler-outline icons; hero numbers and progress bars in native geometry; no images by design (`image_usage: none`, reason recorded in the receipt)
- Facts: every number on the slides is quoted from the communiqué in its written form; three fields the communiqué does not give show NO DATA; `notes/fidelity_check.md` traces ten randomly chosen numbers back to their source sentences
- Typography: SimSun titles, Microsoft YaHei body, Times New Roman hero numbers, Arial data labels and table cells (lining figures; the first pass used Georgia, whose old-style figures were hard to read)
- Speaker notes on every slide; 61 entrance animations across eight families and four Morph transitions (1→2, 2→3, 6→7, 16→17), none of them paired to a native chart or table

## Directories

- `svg_output/`: authored SVG slides (native-export source, with the chart/table markers and JSON payloads)
- `svg_final/`: self-contained preview SVGs (rendered by the gallery viewer)
- `icons/`: the tabler-outline icons the plan selected
- `notes/`: speaker notes, plus `fidelity_check.md` (number-to-source audit)
- `sources/`: the converted communiqué the deck was built from
- `design_spec.md` / `spec_lock.md`: the confirmed plan and its lock
- `animations.json`: transitions, Morph pairs, and per-object entrance choreography
- `exports/`: exported PPTX — default shape-based export, plus a `_native_charts_tables` variant where the ten charts and three tables are PowerPoint chart and table objects

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --with-notes
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --with-notes --native-charts-and-tables
```

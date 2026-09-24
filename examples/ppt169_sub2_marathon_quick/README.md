# sub2_marathon_quick

- Canvas format: ppt169 (1280×720)
- Created: 20260923
- Runtime: Quick Generate from a bare topic with topic research; free design
- Mode / visual style: a data-led explainer for a running club, in a dark sports-data look — near-black field, one neon-green accent, large timing figures
- Pages: the 2:50/km pace, Breaking2 (Monza 2017) against INEOS 1:59 (Vienna 2019), a factor rail through pacing formation and laser, drafting, shoes, fuelling and course and weather, why 1:59:40 is not a record, and the ratified record at the time of writing
- Honest estimates: only drafting and shoes carry published estimates, marked on the page as research estimates that cannot be added up; the other factors stay qualitative, and one page states that no reliable second-by-second breakdown exists
- Images: three Wikimedia race and course photographs (one CC BY-SA, credited on the page; two CC0) and one AI shoe cutaway labelled as not a real product, recorded in `images/image_sources.json`
- Native objects: one chart and two tables; `exports/` also carries the `_native_charts_tables` version
- Object animations and four Morph pairs (the factor rail carries from page 4 to page 8); Chinese speaker notes

## Directories

- `svg_output/`, `svg_final/`, `images/`, `notes/`, `sources/`, `analysis/`, `animations.json`, `exports/` as in the other examples; no spec or lock (Quick runtime)

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --quick-generate --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> --quick-generate --native-charts-and-tables
```

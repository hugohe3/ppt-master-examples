# lora_hu_2021

- Canvas format: ppt169 (1280×720)
- Created: 20260523 — generated on the Default runtime of May 2026; **restored and adapted on 2026-09-05 to the current authoring rules without regenerating** (see below)
- Runtime: Default Generate (Strategist → Image_Generator → Executor) from the paper Hu et al. 2021, *LoRA: Low-Rank Adaptation of Large Language Models* (arXiv:2106.09685)
- Visual style: cool technical blueprint (navy / orange, structure diagrams, KPI cards); this deck predates the mode / visual-style catalogs, so `spec_lock.md` carries no `mode` or `visual_style` section
- Image system: 6 AI images generated in-pipeline (cover hero, GPU-rack cost figure, low-rank insight, reparameterization diagram, attention application, subspace heatmap) plus 4 rendered formula images
- Native objects: 14 tabler-outline icons; object-level entrance animations on every page
- Speaker notes on every slide (15 pages)

## 2026-09 adaptation

The deck was removed from the gallery in the August 2026 clean-up and restored from git history in September 2026 because readers asked for it. The slides were not regenerated; only package metadata was brought up to the current rules:

- `design_spec.md` §IX gained an `Audience move` and a `Relationships` line per slide, and `spec_lock.md` gained `communication`, `pptx_structure` (`flat`), and the two recurring display sizes (`hero_display: 64`, `stat_number: 52`) as named roles
- the 14 icons the pages reference were synced into `icons/` (`icon_sync.py`)
- three gradient-stroked `<line>` rails (agenda, limitations, conclusion) became gradient-filled 3px rects, because objectBoundingBox gradients do not render on a zero-width stroke
- RGB PNG images were re-encoded as JPEG (≤1920px, q82) and every reference renamed; the transparent formula PNGs stay PNG
- `image_analysis.csv` moved to `analysis/`; `svg_final/` and `exports/ppt169_lora_hu_2021.pptx` were regenerated with the current toolchain

Regenerate the PPTX with:

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir> -o <this_dir>/exports/ppt169_lora_hu_2021.pptx
```

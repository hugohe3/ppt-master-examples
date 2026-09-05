<!-- ppt-master-schema: design-spec/v1 -->
# ResearchStudio-Reel paper reading - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | ResearchStudio-Reel: Automate the Last Mile of Research from Paper to Poster, Video, and Blog — paper reading deck |
| Canvas Format | PPT 16:9 (1280 × 720) |
| Page Count | 18 |
| Primary Language | en-US |
| Target Audience | Researchers and research engineers at a lab meeting or reading group who know what an agent skill, a VLM judge, and a poster benchmark are, and want to judge whether the paper's claims are earned |
| Communication Intent | Walk the paper in its own constructive order — the open problem, prior work, the five-skill system, each skill's design requirements and gates, the benchmark result, its analysis, cost, limitations — so a skeptical audience can trace every conclusion back to a figure, a table, or a stated method |
| Desired Audience Outcome | The audience can state the three gaps the system targets (shared grounding, native editability, experience-level convergence), explain the staged-fill loop and why it converges, read Table 1 correctly (best aesthetics among automated systems, but lower PaperQuiz than denser systems), and name the two honest gaps the authors leave open |
| Core Message / Ask / Action | Treating the last mile as a native-editable, section-aligned workspace — one shared extractor, three editable generators, one convergence layer, each with a testable release gate — produces posters that VLM judges rate above the authors' own on aesthetics (3.56 vs 3.03) while keeping every artifact editable and cross-linked; the evaluation is proxy-bound and the pipeline cannot invent bespoke diagrams, and the deck says so |
| Delivery Context | A 25-minute presented walkthrough at a lab meeting or paper-reading group, then circulated as slides for people who missed it |
| Artifact Afterlife | Kept as the group's reference summary of the paper; figures and numbers must be quotable back to the source |
| Reading Mode | balanced |
| Content Strategy | Faithful to the single source (the arXiv v2 PDF converted to Markdown); every number, table cell, and claim is quoted from the paper; the paper's own figures are imported as evidence at original fidelity, never redrawn; observation, inference, and speculation keep the paper's wording; nothing outside the paper is added except the arXiv and project links the paper itself prints |
| Design Style | Research-talk restraint on a Swiss grid: white field, hairline rules, one claim line per page in a fixed position, figures dominant, color used only to encode condition (our Claude Code configuration, our Codex configuration, baselines, author ground truth) with the mapping fixed across every chart and table |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — workflow default (proactive policy true); notes carry the spoken explanation, the source location of every number, and transitions |
| Custom Animations | enabled — explicit user instruction (every example ships custom animations); object-level entrances plus Morph carry-overs on the recurring claim line and the pipeline figure |
| Narration Audio | disabled — workflow default |
| Created Date | 2026-09-05 |

- **Template Application**: the installed academic-research Style (`templates/design_spec.style.academic-research.md`) supplies the method only: constructive order question → prior work → approach → result → interpretation with a pyramid's trace inside it; one claim per page stated where it can be checked against the figure; observation / inference / speculation kept distinct; limitations on a real page; figures imported rather than redrawn; color as a declared condition variable. Its swiss-minimal seed is adopted as the preset visual style. No prototypes, no structure; pages are free-design flat SVG.

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | top 48 / bottom 40 / left 56 / right 56 |
| Content Area | x 56–1224, y 48–680; title band y 48–120 (title + claim line), content field y 140–620, footer (source line + page number) y 656–690 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: instructional, pyramid
- **Mode Behavior**: the deck follows the paper's constructive order — question, prior work, contribution, each skill as one teaching unit (requirements → solution → gate), then results, analysis, cost, applications, limitations, conclusion — because a research audience cannot evaluate a conclusion before its method. Inside that order every page keeps a pyramid's discipline: the title states what the page establishes (an assertion, not a section label), and the claim line under it names the exact evidence on the page that supports it. Sibling skills get parallel pages of the same shape so the audience can map them; signposts ("skill 2 of 5") orient the listener.
- **Visual style**: swiss-minimal
- **Theme**: a research talk that reads like a well-set paper: a fixed title band with the assertion in bold and one claim line beneath it, a hairline under both, the paper's own figure or a native table or chart dominating the field, the reading of that evidence in a narrow column beside it, and a footer citing the section, figure, or table of the paper the page draws from. The recurring motif is the hairline-ruled evidence frame with a small "Fig. N / Table N" caption tag; the five skills reuse one page shape so their differences read as content, not layout.
- **Tone**: precise, sober, checkable; the paper's own numbers and hedges, no added enthusiasm

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | Page field |
| Secondary background | #F3F5F8 | Table header band, requirement cards, appendix-like density blocks |
| Primary | #1B2430 | Titles, axes, author ground-truth condition, key numbers |
| Accent | #1D4ED8 | The ResearchStudio-Reel (Claude Code) condition everywhere: table row, chart series, badge, claim emphasis |
| Secondary accent | #0E9F8A | The ResearchStudio-Reel (Codex) condition everywhere |
| Body text | #2F3A48 | Body copy, table body |
| Secondary text | #6B7684 | Captions, unit lines, axis labels, footer, single-shot baseline condition |
| Divider | #C9D0D8 | Title-band hairline, table header rule, axes |
| Grid | #E6EAEF | Table row rules, chart gridlines, poster-pipeline baseline condition |
| Surface | #F3F5F8 | Evidence frame fill behind imported figures when the figure is on a white ground |
| Positive | #2E8B57 | The FULL verdict band, wins, checks |
| Warning | #E0A100 | SPARSE / SPILLAGE verdict bands, caution |
| Negative | #C0392B | EMPTY / OVERFLOW verdict bands, limitations, non-convergence |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | plain grotesque, bold, decisive assertion | Arial | Arial | sans-serif |
| Body | plain grotesque, regular, lecture-legible | Arial | Arial | sans-serif |
| Data | lining figures for tables and chart labels | Arial | Arial | sans-serif |

- **Title stack**: Arial
- **Body stack**: Arial
- **Data stack**: Arial
- **Role rationale**: one family keeps the research-talk plainness the Style asks for; `data` is the same face at a smaller size so table digits and chart labels align, and bold weight alone marks the best value per column.

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 16 |
| Title | 28 |
| Subtitle | 18 |
| Lead | 20 |
| Annotation | 12 |
| Footnote | 10 |
| Display | 44 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: title assertion first, then the claim line naming the evidence, then the evidence itself (figure, table, chart), then the reading column beside it, then the footer citation
- **Composition tendency**: fixed title band; the field splits asymmetrically — evidence dominant (about two thirds) with a narrow reading column — on figure and table pages; requirement/solution pages use a two-column requirement → solution table with the pipeline figure as a band above; the five skill pages share one shape
- **Cross-page continuity**: the title band, hairline, claim line position, "Fig. N / Table N" caption tag, section signpost (top right), footer citation and page number are fixed on every content page; the condition colors never change; Morph carries the pipeline figure from P04 into P05 and the claim line across the five skill pages
- **Spacing posture**: question, contribution, conclusion pages breathing; skill, result, analysis, cost, limitation pages dense; cover and sources anchor
- **Spacing anchors**: page margin 56; block gap 24; column gutter 32; corner radius 0; body leading 22

## VI. Icon Usage Specification

- **Primary bundled library**: none

| Icon Path | Suitable Scenarios |
| --- | --- |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P03 | table | comparison_matrix | Prior work by output type: representative systems, what they emit, what they leave open |
| P06 | table | record_table | Paper2Poster requirements A1–A5 against the solution the paper gives each |
| P07 | chart | stacked_bar_chart | The five fullRatio verdict bands as one stacked bar on the 0.60–1.20 axis |
| P08 | table | record_table | Paper2Video requirements B1–B5 against their solutions |
| P09 | table | record_table | Paper2Blog requirements C1–C5 against their solutions |
| P11 | table | comparison_matrix | Table 1: nine systems × six sub-criteria, two overalls, two PaperQuiz splits |
| P12 | chart | scatter_chart | Aesthetic overall vs PaperQuiz detail accuracy for the nine systems |
| P14 | chart | horizontal_bar_chart | Wall-clock minutes per skill subtotal from Table 4 |
| P16 | table | record_table | Five recurring failure modes L1–L5 with their mitigations |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| poster_beit.jpg | 1920x1152 | 5:3 | Cover evidence strip, left cell: a generated poster (Figure 1a) | Screenshot | `Three equal cells in one band under the title (#P3-02), each labeled with the artifact name` | no-crop | user | Existing | Figure 1a, the Paper2Poster output for the BEiT paper | none | local |
| video_frame_citransnet.jpg | 1005x567 | 16:9 | Cover evidence strip, middle cell: a talk-video frame (Figure 1b) | Screenshot | `Middle cell of the cover band` | no-crop | user | Existing | Figure 1b, a frame of the Paper2Video output for the CITransNet paper | none | local |
| blog_docx_en.jpg | 732x1332 | 11:20 | Cover evidence strip, right cell: the bilingual blog in Word (Figure 1c) | Screenshot | `Right cell of the cover band, portrait page shown complete` | no-crop | user | Existing | Figure 1c, the English Paper2Blog DOCX for the BEiT paper | none | local |
| fig2_pipeline.png | 1181x259 | 4.6:1 | Figure 2, the five-skill pipeline: one PDF in, three editable artifacts out, one shared extraction in the middle | Diagram | `Full-width band under the claim line (#P1-04); the contribution bullets sit below it` | no-crop | user | Existing | Figure 2 of the paper | none | local |
| fig3_poster_pipeline.png | 1221x379 | 3.2:1 | Figure 3, the Paper2Poster pipeline with the staged-fill loop | Diagram | `Band across the top of the field (#P1-04); the requirement table beneath` | no-crop | user | Existing | Figure 3 of the paper | none | local |
| fig4a_fill_initial.png | 343x767 | 4:9 | Figure 4a, debug overlay of the freshly composed draft | Screenshot | `Left of three equal-height panels in a sequence (#P3-06) beside the verdict-band chart` | no-crop | user | Existing | Figure 4a, Latent Diffusion Models poster, initial exploration | none | local |
| fig4b_fill_progress.png | 387x767 | 1:2 | Figure 4b, the fill loop in progress | Screenshot | `Middle panel of the sequence` | no-crop | user | Existing | Figure 4b | none | local |
| fig4c_fill_done.png | 409x767 | 8:15 | Figure 4c, the completed poster with every section FULL | Screenshot | `Right panel of the sequence` | no-crop | user | Existing | Figure 4c | none | local |
| fig5_video_pipeline.png | 1134x379 | 3:1 | Figure 5, the Paper2Video overview | Diagram | `Band across the top of the field; the requirement table beneath` | no-crop | user | Existing | Figure 5 of the paper | none | local |
| fig7_blog_pipeline.png | 1220x230 | 5.3:1 | Figure 7, the Paper2Blog pipeline | Diagram | `Band across the top of the field; the requirement table beneath` | no-crop | user | Existing | Figure 7 of the paper | none | local |
| fig9_reel_interaction.jpg | 1920x572 | 3.36:1 | Figure 9, the two Paper2Reel interaction states: hover highlights a section, double-click opens video + blog | Screenshot | `Full-width band dominating the field (#P1-04) with the reading in two columns beneath` | no-crop | user | Existing | Figure 9 of the paper | none | local |
| fig10a_author_gt.jpg | 1920x1280 | 3:2 | Figure 10, author ground-truth poster | Screenshot | `Top-left cell of a 3 × 2 small-multiples grid (#P3-04), each cell labeled with its configuration` | no-crop | user | Existing | Figure 10, top left: the human reference | none | local |
| fig10b_claude_max.jpg | 1920x1152 | 5:3 | Figure 10, Claude Code (claude-opus-4.8) at max reasoning | Screenshot | `Grid cell` | no-crop | user | Existing | Figure 10, top right per the caption | none | local |
| fig10c_claude_48.jpg | 1920x1152 | 5:3 | Figure 10, Claude Code (claude-opus-4.8) at high reasoning | Screenshot | `Grid cell` | no-crop | user | Existing | Figure 10 | none | local |
| fig10d_claude_47.jpg | 1920x1152 | 5:3 | Figure 10, Claude Code (claude-opus-4.7) | Screenshot | `Grid cell` | no-crop | user | Existing | Figure 10 | none | local |
| fig10e_claude_46.jpg | 1920x1152 | 5:3 | Figure 10, Claude Code (claude-opus-4.6) | Screenshot | `Grid cell` | no-crop | user | Existing | Figure 10 | none | local |
| fig10f_codex.jpg | 1920x1152 | 5:3 | Figure 10, Codex (gpt-5.5) | Screenshot | `Grid cell` | no-crop | user | Existing | Figure 10, bottom right | none | local |

Every image is a figure of the source paper, imported at original fidelity as evidence and never redrawn; each placement keeps the complete figure visible (`no-crop`) with a "Fig. N" caption tag and the paper's own caption sense in native text. No AI images and no web images.

## IX. Content Outline

### Part 1: Question and contribution

#### Slide 01 - Cover

- **Audience move**: not sure which paper this is → knows the paper, the venue-free arXiv identity, the authors' institutions, and sees the three artifacts the system produces
- **Relationships**: membership — poster, talk video, and blog are the three artifacts of one system
- **Composition**: title stack on the upper two thirds; a three-cell evidence band along the bottom showing Figure 1's poster, video frame, and blog page, each labeled; arXiv id and project link in the footer
- **Cover impact**: hook = "one paper PDF in, three editor-ready artifacts out" (binding); composition is a reference
- **Title**: ResearchStudio-Reel: Automate the Last Mile of Research from Paper to Poster, Video, and Blog
- **Core message**: this is a paper-reading deck of arXiv:2607.04438 (v2, 19 July 2026)
- **Content**: kicker "Paper reading · arXiv:2607.04438 · July 2026" · title · author line "Hugo He, Lingao Xiao, Yalun Dai, Yangyu Huang, Qihao Zhao, Wenshan Wu, Ruishuo Chen, Jin Jiang, Qianli Ma, Jiahuan Zhang, Xin Zhang, Ying Xin, Yang Ou, Yan Xia, Scarlett Li, Longbo Huang, Zhipeng Zhang, Yang He, Yap Kim Hui, Yan Lu" · institutions "Microsoft Research · National University of Singapore · Nanyang Technological University · Tsinghua University · Peking University · Shanghai Jiao Tong University · Westlake University · CFAR, A*STAR" · evidence band: (a) Poster — Paper2Poster, (b) Talk video — Paper2Video, (c) Bilingual blog — Paper2Blog (Figure 1) · footer "Project: https://aka.ms/ResearchStudio"
- **Images**: poster_beit.jpg, video_frame_citransnet.jpg, blog_docx_en.jpg

#### Slide 02 - Research question

- **Audience move**: thinks dissemination is a solved formatting chore → sees it as a separate layer with three concrete gaps the literature leaves open
- **Relationships**: membership — three artifacts form the dissemination layer; contrast — what recent multi-format systems do versus what remains open; order — G1 → G2 → G3
- **Composition**: claim line, then a three-column row of the three gaps as numbered blocks, with the framing sentence above them
- **Title**: The last mile of research is a separate layer, prepared in the days after acceptance, and three gaps remain open
- **Core message**: generating several formats is no longer the question; whether the artifacts stay grounded, editable, and navigable is
- **Content**: framing: the layer covers the conference poster, the talk video on the venue's virtual track or the lab's channel, and the blog piece for social media; each needs figure selection, layout, narration, or audience-appropriate writing; prepared right after the camera-ready · the shift: paper-to-poster [1–3], paper-to-video [4–6], paper-to-blog [7–10] plus multi-artifact suites PaperX and OmniPresent [11, 12] move the question from "can several formats be generated" to "do the artifacts remain native-editable and navigable" · G1 Shared grounding — combining artifact-specific systems repeats figure, caption, and metadata extraction and leaves cross-artifact references for the user to reconcile · G2 Native editability — a multi-format suite does not by itself give native-editable source files in PowerPoint and Word · G3 Experience-level convergence — parallel outputs do not bind poster regions, video segments, and blog passages into one interactive surface · footer "§1 Introduction"

#### Slide 03 - Prior work positioning

- **Audience move**: knows a few of the systems → can place them by output type and see which contract each leaves open
- **Relationships**: membership — systems grouped by output type; contrast — output contracts (PPTX / HTML / PDF / DOCX) and evaluation regimes differ
- **Composition**: one table across the field: four output-type rows (poster, slides and video, blog and long-form, multi-artifact suites) × representative systems, what they emit, and what remains open; a one-line positioning sentence beneath
- **Title**: Prior work is organized by output type; contracts differ in editability, and VLM scores are mostly used for evaluation rather than as release gates
- **Core message**: the paper positions itself on native editability and experience-level convergence, not on being the first multi-artifact generator
- **Content**: table rows — Paper-to-poster: Paper2Poster (PosterAgent, benchmark, PaperQuiz, PPTX) [1], PosterGen (specialized agents incl. color and typography) [2], P2P (HTML poster, fine-grained benchmark) [3], PosterForest, EfficientPosterGen, APEX (edits PPTX), SciPostLayout / SciPostGen, Any2Poster, PosterHarness; leaves open: VLM scores used for evaluation, not as runtime release gates · Slides and paper-to-video: PPSGen → D2S → DOC2PPT → SlideSpawn → PPTAgent / SlideGen; PresentAgent, VideoAgent, Paper2Video / PaperTalker (101-paper benchmark, cursor grounding, talking head), Preacher, AutoLectures; leaves open: a section-addressable timeline retained for downstream navigation · Blog and long-form: HERA, PTSPI, GoSum, LongDPO, ProjectMundo, lay summaries, Papers-to-Posts (interactive source outline); leaves open: editable Word output with layout-aware checks for a bilingual pair · Multi-artifact suites: PaperX (Scholar DAG → PPT, poster, PR posts), OmniPresent (concurrent; centralized HTML with cross-modal verify-and-repair, discussed qualitatively); leaves open: native-editable source files per artifact and experience-level convergence · positioning sentence: "Rather than claiming the first multi-artifact generator, ResearchStudio-Reel focuses on a native-editable, section-aligned dissemination workspace" (§5.5) · footer "§5 Related Works"
- **Visualization**: `related-systems` = 4-row × 4-column text table (output type, representative systems, output contract, what remains open); Native-ready: related-systems=yes

#### Slide 04 - Contribution claim

- **Audience move**: has the gaps → sees the five skills that answer them and the four contributions the authors claim, scoped to what the results support
- **Relationships**: link — G1 → Paper2Assets, G2 → native PowerPoint/Word deliverables, G3 → Paper2Reel; order — extractor → generators → convergence; membership — five skills form one workspace
- **Composition**: Figure 2 as a full-width band under the claim line; beneath it, left, the five skills as five labeled cells in pipeline order with the gap each answers; right, the four contribution bullets
- **Title**: The answer is a native-editable dissemination workspace: one shared extractor, three editable generators, one convergence layer, as five Claude Code / Codex skills
- **Core message**: Paper2Assets answers G1, native PowerPoint and Word answer G2, Paper2Reel answers G3; each artifact ships behind a release check
- **Content**: Figure 2 caption sense: one PDF in, three editor-ready artifacts out, one shared extraction in the middle; the same section ids, figure handles, and claim anchors keep the artifacts cross-referenced · skills: Paper2Assets (shared extractor → G1), Paper2Poster, Paper2Video, Paper2Blog (editable generators → G2), Paper2Reel (convergence layer → G3) · runtimes: Claude Code and Codex skill mechanisms; deterministic primitives — headless Chromium for HTML→PDF, LibreOffice + ffmpeg for slides→video, python-docx; Edge TTS for narration · contributions: (1) the workspace that turns one PDF into a print-ready poster, a narrated talk video, and a bilingual blog through composable skills; (2) Paper2Reel, an experience-level convergence layer binding poster regions, video segments, and blog passages in one navigable HTML surface; (3) a delivery contract of one shared Paper2Assets bundle plus native-editable sources — PowerPoint for poster and video deck, Word for the blog; (4) posters with the best scores among automated systems on all three aesthetic sub-criteria and best or tied-best on two of three information sub-criteria, exceeding the authors' own by ~17.5% on aesthetics (3.56 vs 3.03) and winning overall on 74 and 95 of 100 papers under the two judges; the video ships with narration-aligned highlights, burned-in and sidecar subtitles, and target-duration control; the blog ships in two languages with layout-aware DOCX repair · footer "§1, Figure 2"
- **Images**: fig2_pipeline.png
- **Motion suggestion**: the Figure 2 band carries over from this page to the Paper2Assets page so the audience sees the same pipeline zoomed into its first stage

### Part 2: The five skills

#### Slide 05 - Paper2Assets

- **Audience move**: sees the extractor as a box → knows what the bundle holds, the step sequence, and why figure cleanup runs once upstream
- **Relationships**: order — extraction steps run in sequence; membership — the bundle's contents; link — every generator reads the bundle and never reopens the PDF
- **Composition**: signpost "skill 1 of 5"; left two thirds a horizontal step flow (chevrons) of the extraction pipeline with the figure-cleanup chain as a second, smaller flow beneath; right column the bundle contents and the single-owner rule
- **Title**: Paper2Assets reads the PDF once and emits one bundle every generator consumes verbatim, so figure cleanup runs once instead of per artifact
- **Core message**: the bundle is the only interface; stable section ids, figure handles, and claim anchors make cross-artifact references free
- **Content**: pipeline steps: pull text and captions and crop each figure with a column-aware margin → synthesize metadata from the first page (and the arXiv abstract page) → write the nine-section summary (Problem, Motivation, Contribution, Method, Dataset/Benchmark, Key Result, Ablation, Headline Numbers, Takeaway), each with an essential entry, a supplementary entry in reserve, and a spoken script → fetch institution logos (Wikimedia Commons infobox marks, verified, slot hidden on failure) and the venue logo (Wikidata) → render QR codes → emit canonical record files; a second pass adds the inventory manifest with the PDF checksum, per-section records with stable ids, and the narration clip list in reading order · each step is a separate idempotent script that re-runs in isolation · figure cleanup chain: deterministic prefix strips chrome residue, caption strips, and white margins → a visual-AI step judges a tight bounding box → a fresh-context sub-agent verifier re-reads the original against the proposed crop → only a clean pass commits, splitting a raster that packs two figures; raw extract backed up once · bundle contents: full body text with page breaks, detected captions, per-figure manifest, cleaned figure images, metadata (title, authors, institutes, venue, paper and code links), nine-section summary, logos and QR codes, inventory manifest · rule: downstream skills read the bundle and never re-open the PDF (addresses G1) · footer "§2.1"

#### Slide 06 - Paper2Poster requirements and solutions

- **Audience move**: assumes poster generation is a layout problem → sees the five engineering requirements that took the most iteration and the answer to each
- **Relationships**: link — each requirement A1–A5 maps to one solution; order — A1 → A5 as the paper answers them
- **Composition**: signpost "skill 2 of 5"; Figure 3 as a band under the claim line; beneath it a five-row requirement → solution table
- **Title**: Paper2Poster composes along four orthogonal axes instead of a template bank, then fills the page with a measured loop and exports native PowerPoint shapes
- **Core message**: five recurring requirements (A1–A5) shaped the design more than the visual style did
- **Content**: Figure 3 caption sense: bundle → pick Method plus secondary figures → compose poster.html along layout / style / header / Scan-to-Read axes → staged-fill loop (measure slack + polish, edit one section per round) → narration audio and header logos → render PDF + PNG and an editable native-shape PowerPoint → mandatory deliverables gate · table rows: A1 Composition without a template explosion → four orthogonal axes: layout (full / half / three-column), style (a family of interchangeable CSS themes, 11 in Figure 3), header (five arrangements of venue logo, institution logos, QR), Scan-to-Read block; only the layout is fixed by a hard rule (the Method figure's shape), the rest sampled reproducibly; every section carries a distinct widget · A2 A fill loop that converges → a staged, discrete measured-fill loop with five categorical verdicts (next page) · A3 A page too large to re-read → each measurement returns only the verbatim source of off-target sections; the ~100 KB file never enters the context window or the output channel · A4 Figures that fill their cards → figures are sized through their height cap and held to a hard floor, so text edits never strand a figure as a small stamp · A5 A faithful editable export → the bridge rebuilds each slide from the live DOM: text → editable frames keeping bold/italic, figure → replaceable picture, equation → native equation, section card → styled shape · outputs: web page, print-resolution PDF, thumbnail, native PowerPoint, optional per-section narration audio · footer "§2.2.1–2.2.2, Figure 3"
- **Visualization**: `poster-requirements` = 5-row × 3-column table (id, requirement, solution); Native-ready: poster-requirements=yes
- **Images**: fig3_poster_pipeline.png

#### Slide 07 - The staged-fill loop

- **Audience move**: hears "fill loop" → can state the five verdict bands, the move each triggers, and the three damping mechanisms that make termination a fixed point
- **Relationships**: order — the five bands partition the fullRatio axis; link — each band maps to one remediation; order — draft → in progress → completed in Figure 4
- **Composition**: signpost; left, the verdict bands as one stacked horizontal bar on the 0.60–1.20 fullRatio axis with each band's remediation beneath; center-right, the three Figure 4 panels in sequence; a strip of the three damping mechanisms and the exit condition along the bottom
- **Title**: The fill loop is discrete: a section's fullRatio is quantized into five verdicts, one section is edited per round, and termination is a categorical fixed point
- **Core message**: verdict alone selects the move, moves are sized by the measured pixel delta, and a circuit breaker ships the best-measured state
- **Content**: fullRatio = painted content height ÷ inner card height (getBoundingClientRect) · bands: EMPTY < 0.70 → append a withheld supplementary paragraph or promote an optional section; SPARSE 0.70–0.90 → polish up (pad prose, enlarge a widget); FULL 0.90–0.98 → untouched (target); SPILLAGE 0.98–1.10 → polish down (tighten prose); OVERFLOW > 1.10 → drop a supplementary paragraph or an optional section · the Method figure is retuned under a separate figure-fill gate (≥ 90% of its card on one axis); the loop terminates only when every section reads FULL and no figure trips the gate · damping: moves sized by the signed pixel delta; no re-applying a move that already overshot on a section; an on-disk round counter trips a circuit breaker that ships the best-measured state (Figure 3: bounded ~12 rounds) · loose gate then render-time expand: the gate counts full at 90% because tightening toward 98% sharply raises rounds past 0.94; one render pass then stretches under-filled cards toward 98% by growing row whitespace, figures not resized, reverted if the canvas would grow · Figure 4: (a) initial explorations, (b) fill-loop in progress, (c) poster completed, overlay colors by verdict · footer "§2.2.2, Figure 4"
- **Visualization**: `verdict-bands` = one stacked horizontal bar (five band widths on the 0.60–1.20 axis, colored by verdict); Native-ready: verdict-bands=yes
- **Images**: fig4a_fill_initial.png, fig4b_fill_progress.png, fig4c_fill_done.png

#### Slide 08 - Paper2Video

- **Audience move**: thinks a good deck makes a good video → sees the five media-level requirements after the deck leaves the authoring workflow, and the package gate that tests them
- **Relationships**: link — B1–B5 each map to one solution; order — narration plan → deck → cues → audio and captions → render → gate; membership — three root deliverables
- **Composition**: signpost "skill 3 of 5"; Figure 5 band under the claim line; beneath, the B1–B5 requirement → solution table with the three root deliverables and the gate's checks in a narrow right column
- **Title**: Paper2Video plans duration before rendering, anchors narration to visible objects, and ships an editable deck with captioned and clean MP4s behind one package gate
- **Core message**: the deck comes from the full ppt-master route; the skill's contribution is the auditable media bundle and the timeline sidecar Paper2Reel navigates
- **Content**: root deliverables video.pptx, video.mp4, video_no_subtitles.mp4; intermediates under assets/ (audio, subtitle sidecars, frames, duration reports, cue plans, timelines, QA reports) · table rows: B1 Duration planned before rendering → the planner estimates the script before TTS and asks for semantic rewrites; a post-render duration report; small residuals repaired by a bounded speech-rate plan, large ones return to rewriting · B2 Attention guidance → the deck workflow attaches semantic anchors to objects the narration names; a cue resolver combines script, word timings, geometry, and anchors into visual_cues.json; normalized geometry survives resolutions; default style spotlight_laser · B3 Two caption contexts → burned-in subtitles in video.mp4, a clean video_no_subtitles.mp4 for the reel's own caption toggle; same frames, audio, and highlight timing · B4 Addressable after export → timeline.json maps each section or chunk to its audio window, cues, slide frame, and accepted visual cue · B5 Deterministic media checks → check_video_package.py: files exist and play, audio stream present, duration within tolerance, non-empty subtitle sidecar, final MP4 not byte-identical to the raw render, cue coverage and timing, no word-sized highlight boxes, blank frames and text overflow caught from the PPTX and frames, unsafe rate changes rejected · deck authoring through the full ppt-master workflow [22] · footer "§2.3, Figure 5"
- **Visualization**: `video-requirements` = 5-row × 3-column table (id, requirement, solution); Native-ready: video-requirements=yes
- **Images**: fig5_video_pipeline.png

#### Slide 09 - Paper2Blog

- **Audience move**: expects a bilingual summarizer → sees two separately written articles held to one evidence map and a layout gate that reads the DOCX as a page
- **Relationships**: link — C1–C5 each map to one solution; contrast — Chinese public-account register versus English research-blog register; membership — two root deliverables
- **Composition**: signpost "skill 4 of 5"; Figure 7 band; beneath, the C1–C5 table; right column the package-gate checks
- **Title**: Paper2Blog writes the Chinese and English articles separately from one shared evidence map, then gates the Word files on facts, figures, fonts, and page layout
- **Core message**: register is controlled at generation time through language-specific outlines; hard facts are checked deterministically afterwards
- **Content**: root deliverables: the Chinese article (WeChat public-account piece) and the English article (research-blog piece), same facts, figures, numbers, claims, and links · table rows: C1 One evidence base for two languages → one evidence map (hook, problem, method components, claims, quantitative results, limitations, links, figure roles); a missing hard fact is omitted, never guessed · C2 Register controlled during writing → the two articles are written separately from language-specific outlines and a style guide, not translated sentence by sentence · C3 Article-level figure selection → a small shared figure set placed next to the section that prepares the reader, with captions per language; readability after DOCX resizing checked · C4 A Word article, not plain text → fixed filenames, embedded media, editor-friendly fonts, Latin body font plus Chinese fallback · C5 Editor-ready layout → underfilled images, images pushed to the next page, orphan tails detected from the document structure; strict mode renders pages to catch near-blank pages and bottom whitespace · gate: both DOCX exist and are readable, enough text, images embedded not linked, no placeholder text, font declarations; embedded image count, identity, and order compared across languages, extracted numeric claims and technical terms cross-checked · footer "§2.4, Figure 7"
- **Visualization**: `blog-requirements` = 5-row × 3-column table (id, requirement, solution); Native-ready: blog-requirements=yes
- **Images**: fig7_blog_pipeline.png

#### Slide 10 - Paper2Reel

- **Audience move**: imagines a dashboard → sees a poster-first viewer whose section modal binds video, captions, slide thumbnails, and the bilingual blog through one alignment sidecar
- **Relationships**: link — one canonical section id maps to poster block, slide targets, video window, subtitle tracks, thumbnails, and blog blocks; order — hover → double-click → modal
- **Composition**: signpost "skill 5 of 5"; Figure 9 as a full-width band dominating the field; beneath it two columns — interaction design and content alignment — and a bottom strip for the two-part gate
- **Title**: Paper2Reel is a presentation surface, not a fourth summary: the alignment sidecar turns a poster block, a video segment, a slide, and a blog passage into views of one section
- **Core message**: convergence happens at the experience level over already-produced artifacts, which stay downloadable and independently editable
- **Content**: interaction: poster-first first screen; hover highlights a section; double-click opens the section modal — video left (subtitle-free source plus caption sidecars behind the viewer's toggle), blog right with an EN / 中文 switch, a draggable splitter, slide thumbnails that seek; the title area opens a full-paper modal; menu, help, audio, downloads stay out of the way · alignment: the sidecar maps each canonical section id to its poster block, slide targets, video start and end, subtitle tracks, thumbnails, and blog blocks; the viewer never scrapes filenames, the poster, or the video · incomplete inputs: invoked on a PDF, arXiv link, or partial bundle, it completes the missing stages through the full upstream workflows, preserving section ids and paths · bundle: poster, media, slides, blog, and downloads folders; root limited to the viewer, the alignment record, and the manifest · gate: static — every required asset present, no stale tabbed-viewer markers, no machine-local paths, raw pre-subtitle video as playback source; browser — served with a range-capable local server, headless checks of poster-first load, hover, modals, split pane, subtitle toggle, thumbnail and direct seeking, downloads, shortcuts, blog rendering, plus a file-browser gate for opening from disk · footer "§2.5, Figure 9"
- **Images**: fig9_reel_interaction.jpg

### Part 3: Evidence

#### Slide 11 - Main result, Table 1

- **Audience move**: has heard the headline → reads the full table: nine systems, six sub-criteria, two overalls, two PaperQuiz splits, and where the paper's configuration is and is not best
- **Relationships**: contrast — single-shot LLMs vs poster pipelines vs author ground truth; membership — three system families; contrast — aesthetic ordering vs PaperQuiz ordering
- **Composition**: claim line, then Table 1 across the full width with the two Reel rows in the condition colors, best value per column bold; a narrow footer line with the protocol
- **Title**: On the 100-paper Paper2Poster benchmark the Claude Code configuration is best among automated systems on all three aesthetic sub-criteria (3.56 overall vs the authors' 3.03) and best or tied-best on two of three information sub-criteria
- **Core message**: per paper it wins the overall score against the authors' poster on 74 of 100 papers under the Claude judge and 95 under the GPT judge; PaperQuiz ranks it lower than the denser systems
- **Content**: protocol: three families scored by the same pipeline — single-shot Claude-4.8 Opus, GPT-5.5, Gemini-3.1 Pro (one fixed prompt); poster pipelines Paper2Poster tool, P2P, PosterGen (reproduced), ResearchStudio-Reel under Claude Code (claude-opus-4.8) and Codex (gpt-5.5); author ground truth; two VLM judges claude-opus-4.8 and gpt-5.5, cells are their mean; posters downscaled to ≤ 2560 px and rendered at true content size; PaperQuiz is exact-match answer accuracy from the poster image alone · Table 1 rows (Elem, Engag, Layout, Aes. overall | Low, Logic, Cont, Info overall | Quiz detail %, Quiz underst. %): Claude-4.8 Opus 3.10 2.68 2.97 2.92 | 3.92 4.01 3.80 3.91 | 69.86 93.67; GPT-5.5 3.12 2.94 3.40 3.15 | 3.99 4.00 3.91 3.97 | 70.89 94.25; Gemini-3.1 Pro 3.07 2.89 3.27 3.08 | 3.95 4.00 3.65 3.87 | 65.36 93.59; Paper2Poster tool 2.86 2.30 3.00 2.72 | 3.46 3.41 3.34 3.40 | 69.95 95.02; P2P 2.68 2.34 3.15 2.72 | 3.92 3.78 3.70 3.80 | 75.40 95.60; PosterGen 2.93 2.23 2.98 2.71 | 3.80 3.76 3.37 3.64 | 57.45 91.85; Reel (Codex) 3.16 3.03 3.62 3.27 | 3.95 3.97 3.09 3.67 | 55.55 92.01; Reel (Claude Code) 3.53 3.17 3.99 3.56 | 3.99 4.03 3.41 3.81 | 56.79 92.16; Author ground truth 3.13 2.60 3.35 3.03 | 3.45 3.85 3.50 3.60 | 54.73 91.40 · best per column bold: Elem 3.53, Engag 3.17, Layout 3.99, Aes overall 3.56, Low 3.99 (tied), Logic 4.03, Cont 3.91, Info overall 3.97, Quiz detail 75.40, Quiz underst. 95.60 · overall score = mean of the two Overall columns: Claude Code 3.69 leads; single-shot 3.41–3.56 and Codex 3.47 form a second tier; reproduced pipelines 3.06–3.26 · win rate: 74 / 100 (Claude judge), 95 / 100 (GPT judge) = 85% and 100% of non-tied papers · footer "§3, Table 1; per-judge breakdown in Appendix D, Table 5"
- **Visualization**: `table1-results` = 9-row × 11-column numeric table with bold best-per-column; Native-ready: table1-results=yes

#### Slide 12 - Analysis and controlled comparisons

- **Audience move**: sees two rankings that disagree → understands the aesthetics-versus-comprehension tension and what the two in-table comparisons do and do not isolate
- **Relationships**: contrast — aesthetic overall vs PaperQuiz detail across the nine systems; link — same model with and without the composition + fill loop; link — same skill under two harnesses
- **Composition**: left, a scatter of aesthetic overall (x) against PaperQuiz detail accuracy (y) for the nine systems, labeled, conditions colored; right, a four-bar column chart of aesthetic overall for the two controlled comparisons plus the author reference; beneath, the paper's caution in its own words
- **Title**: The PaperQuiz ordering nearly reverses the aesthetic ordering: denser posters answer more questions, and the fill loop packs to a target density rather than to exhaustion
- **Core message**: the loop adds 0.64 aesthetic and over a full Layout point for the same model, and transfers to Codex at 3.27; the authors call the aesthetic margins a proxy signal, not proof
- **Content**: scatter points (aesthetic overall, quiz detail): Claude-4.8 Opus (2.92, 69.86), GPT-5.5 (3.15, 70.89), Gemini-3.1 Pro (3.08, 65.36), Paper2Poster tool (2.72, 69.95), P2P (2.72, 75.40), PosterGen (2.71, 57.45), Reel Codex (3.27, 55.55), Reel Claude Code (3.56, 56.79), Author GT (3.03, 54.73) · reading: P2P leads both Quiz splits because its portrait canvas is packed with near-verbatim prose at some of the lowest aesthetic scores; the Paper2Poster tool is close behind because its content is assembled from the benchmark's own Q&A extraction; author posters prune to headline results and place last on both Quiz splits; Reel sits deliberately between the poles · controlled comparison (i): claude-opus-4.8 single-shot 2.92 aesthetic / 2.97 Layout → the same model inside composition + measured fill 3.56 / 3.99, a gain of 0.64 and over a full Layout point, though prompting, call count, and inference budget also change · (ii): the identical skill under Codex + gpt-5.5 reaches 3.27 (per judge 3.29 and 3.25), second-highest in Table 1, ahead of every single-shot baseline (best gpt-5.5 3.15), every reproduced pipeline, and the author reference 3.03; trails Claude Code by about 0.3 · caution (verbatim sense): aesthetic appeal is subjective and audience-dependent; the sub-criteria are scored by VLM judges that stand in for but do not equal human preference; a higher judge score means the automated raters prefer the poster, not that human viewers would agree · footer "§3 Analysis and Controlled comparisons"
- **Visualization**: `aesthetics-vs-quiz` = scatter of nine labeled points; `controlled-bars` = four-column chart (single-shot claude-opus-4.8 2.92, Reel Codex 3.27, Reel Claude Code 3.56, author ground truth 3.03); Native-ready: aesthetics-vs-quiz=yes; controlled-bars=yes

#### Slide 13 - Qualitative comparison across configurations

- **Audience move**: has the numbers → sees six posters of the same paper: the human reference and five runs of one fixed skill under different harness, model, or reasoning effort
- **Relationships**: contrast — human reference vs generated; membership — five configurations of one skill; contrast — reasoning effort and harness
- **Composition**: a 3 × 2 small-multiples grid of Figure 10 filling the field, each cell labeled; the reading in one line beneath
- **Title**: Holding the skill, prompt, and pipeline fixed, five configurations each produce a full single page that differs in figure choice, phrasing density, and accent
- **Core message**: the remaining margin between Claude Code and Codex reflects finer visual hierarchy, not a failure of the skill under Codex
- **Content**: cells: Author ground truth (top left); Claude Code (claude-opus-4.8), max reasoning (top right per caption); Claude Code (claude-opus-4.8), high reasoning; Claude Code (claude-opus-4.7); Claude Code (claude-opus-4.6); Codex (gpt-5.5) at default effort · caption sense: all settings use high reasoning effort except the panel marked max reasoning; the Codex panel runs gpt-5.5 at its default effort · footer "§3, Figure 10"
- **Images**: fig10a_author_gt.jpg, fig10b_claude_max.jpg, fig10c_claude_48.jpg, fig10d_claude_47.jpg, fig10e_claude_46.jpg, fig10f_codex.jpg

#### Slide 14 - Operational profile

- **Audience move**: wonders what it costs → knows the per-skill wall-clock and token totals and which stage dominates each skill
- **Relationships**: membership — five skill subtotals sum to the full pipeline; contrast — the heaviest stage per skill; order — skills in pipeline order
- **Composition**: left, a horizontal bar chart of minutes per skill subtotal from Table 4; right, a compact table of the heaviest stage per skill with its minutes and share; a KPI strip along the bottom with the pipeline totals
- **Title**: A full four-artifact bundle takes about 89 minutes of summed stage time and 2.6M input / 276K output tokens per paper, with the fill loop and video rendering as the heaviest stages
- **Core message**: Paper2Poster and Paper2Video carry the largest subtotals; running the three generators in parallel reduces elapsed time
- **Content**: subtotals (min): Paper2Assets 8.6, Paper2Poster 23.3, Paper2Video 28.5, Paper2Blog 16.7, Paper2Reel 12.1; full pipeline 89.2 min, 675 turns, 2,568K input tokens, 108,546K cached re-reads (billed at ~10% of fresh input), 276K output tokens; mean over 5 papers on claude-opus-4-8 · heaviest stage per skill: extract & figures 8.6 min (18% of input); fill loop 14.8 min (100 turns, 18% of output); render & mux 9.2 min; QA gate & revision 10.0 min (17% of output); QA gate 6.2 min (8% of output) · notes: each skill is an isolated subprocess whose one-time context load folds into its first stage; when LaTeX source is available the pipeline can read original figure files instead of the PDF path · footer "§3 Operational profile, Table 4"
- **Visualization**: `minutes-by-skill` = five-bar horizontal bar chart (minutes per skill subtotal); `heaviest-stages` = 5-row × 4-column table (skill, heaviest stage, minutes, share); Native-ready: minutes-by-skill=yes; heaviest-stages=yes

### Part 4: Scope and interpretation

#### Slide 15 - Applications and capability coverage

- **Audience move**: sees a benchmark result → sees who the system is for and what the two capability audits document and do not measure
- **Relationships**: membership — three application contexts of one pipeline; contrast — cadence and scale differ (one-off, continuous, periodic batch); membership — the emitted objects the audits count
- **Composition**: three equal columns for the application contexts, each with who runs it, which artifacts they lean on, what they revise; a bottom band for the capability audits
- **Title**: Three contexts span the dissemination spectrum — the author's camera-ready week, a lab's publication intake, a course's paper-of-the-week packs — on the same pipeline at different cadences
- **Core message**: the capability audits (Tables 2–3) document breadth of the delivery contract; they do not measure editing effort or the usability of the aligned viewer
- **Content**: author's last mile: one Claude Code session per paper; editable .pptx, video.pptx + .mp4 pair, bilingual .docx pair, one reel.html that doubles as a review surface for co-authors · lab / org: wired into publication intake so every accepted paper auto-generates drafts; editable PowerPoint and Word make a draft-and-revise workflow; one interactive surface per paper for the comms team · course / reading group: paper-of-the-week briefing packs — lecture deck, asynchronous talk video, newsletter blog; instructors adjust framing or drop a slide; re-running on a corrected PDF re-issues the pack · capability audits: Table 2 (video) counts visual cues or cursor grounding, editable PPTX deck, duration control, narration audio; Table 3 (blog) counts layout checks, embedded figures, editable DOCX, paper-input summarization; ResearchStudio-Reel emits all of them, plus the shared bundle and the navigable surface · gap to human posters: a designer adds purpose-drawn diagrams and icons the paper does not contain; the pipeline reuses only content that appears in the paper; author taste spans a wide legitimate range · footer "§3 Capability coverage, §4 Applications"

#### Slide 16 - Limitations and threats

- **Audience move**: wants to know what could go wrong → sees five recurring failure modes with their mitigations, the untested domain scope, and what the evaluation does not cover
- **Relationships**: link — each failure mode maps to one mitigation; membership — three limitation classes
- **Composition**: left two thirds the L1–L5 table; right column the domain-scope and evaluation-coverage limits
- **Title**: Five failure modes recur in end-to-end runs, the system is calibrated on ML / CV / NLP venues only, and quantitative evaluation covers the poster alone
- **Core message**: each failure mode has a named mitigation inside the pipeline; the video and blog are compared only on capability coverage, and no human-rater study exists yet
- **Content**: table rows: L1 Figure-cleanup residue (caption strip or body text baked into a raster) → visual-AI decaption pass plus fresh-context verifier re-crops before any skill embeds the figure · L2 Fill-loop non-convergence (oscillation across the 90–98% band) → round counter and circuit breaker ship the best-measured state; render-time expand recovers the rest · L3 Slide–narration referential drift ("Figure 3" spoken while Figure 2 shows) → the shared alignment timeline lets the QA gate reject the render · L4 Bilingual blog drift (numbers, benchmark names, affiliations disagree) → evidence map plus layout-aware DOCX gate cross-check numeric claims, terms, and figure order · L5 Voice-mismatched narration (default Edge TTS reads a keynote deck flat) → re-run narration with another voice, e.g. en-US-GuyNeural or en-US-AriaNeural · domain scope: calibrated on ML, CV, NLP; transfer to biomedicine, physics, or design-heavy fields untested; primitives are domain-agnostic, each venue family should be validated end-to-end · evaluation coverage: quantitative results only for the poster under two VLM judges; the video benchmark of [4] not applied; audits do not measure human editing effort, fidelity after edits, or whether section-level navigation improves understanding; RRP is an in-loop signal, not a headline metric; a third-party human-rater study is left for future work · footer "Appendix A Limitations"
- **Visualization**: `failure-modes` = 5-row × 3-column table (id, failure mode, mitigation); Native-ready: failure-modes=yes

#### Slide 17 - Conclusion and future work

- **Audience move**: has followed the chain → can restate what the evidence supports and the two gaps the authors put ahead of broader coverage
- **Relationships**: contrast — what is established vs what remains; order — the argument closes back on the opening question
- **Composition**: breathing page: the conclusion as three short restatements on the left, mirroring the question page's three-column rhythm; the two future-work gaps as two blocks on the right
- **Title**: What the evidence supports: a native-editable, section-aligned workspace with testable gates; what it does not yet: reading-and-recall evaluation and bespoke diagrams
- **Core message**: the paper shifts the last mile from one-way automation toward a workflow authors can inspect, navigate, and revise, and names the limits of its own proxies
- **Content**: established: five composable skills, one Paper2Assets bundle, native-editable PowerPoint poster and video deck plus bilingual Word blog, bound by Paper2Reel; posters best among automated systems on all three aesthetic sub-criteria and best or tied-best on two of three information sub-criteria under two VLM judges, 3.56 vs 3.03 on aesthetics, wins on 74 and 95 of 100 papers; the pattern may extend to other targets with native authoring formats, deterministic renderers, and testable package criteria · future work 1, evaluation is proxy-bound: the aesthetic rubric and PaperQuiz pull in opposite directions and neither measures whether a reader absorbs the work; the honest next step is a controlled human reading-and-recall signal rather than a proxy a denser poster can always game · future work 2, the generative gap: the pipeline reuses only figures in the paper and cannot produce the bespoke method or overview diagrams designers add; faithful figure synthesis would reintroduce the hallucination risk the categorical gates suppress and push gate discipline onto factual content · footer "§6 Future Work, §7 Conclusion"

#### Slide 18 - Sources and links

- **Audience move**: wants to verify → has the paper, project, and code locations and knows every figure and number on the deck came from the paper
- **Relationships**: none
- **Composition**: ending page: three linked entries as a short list, a provenance note about figures and numbers, and the licensing lines the paper states
- **Title**: Sources
- **Core message**: everything shown is quoted from arXiv:2607.04438 v2; the figures are the paper's own
- **Content**: Paper — ResearchStudio-Reel: Automate the Last Mile of Research from Paper to Poster, Video, and Blog, arXiv:2607.04438 v2, 19 July 2026, link https://arxiv.org/abs/2607.04438 · Project — https://aka.ms/ResearchStudio · Code — https://github.com/microsoft/ResearchStudio, MIT license, each skill's SKILL.md as the source of truth · provenance: Figures 1–10 reproduced from the paper; Table 1 and Table 4 values quoted as printed; per-judge scores in Appendix D; the three single-shot baselines share one fixed prompt reproduced in Appendix G · licensing note from the paper: extracted paper figures follow the source paper's license; institution and venue logos follow Wikimedia Commons and Wikidata licenses; edge-tts accesses Microsoft Edge's online service · deck built with ppt-master (the deck-authoring dependency Paper2Video uses, reference [22]) · footer "Appendix B, C"
- **Hyperlinks**: "https://arxiv.org/abs/2607.04438" → https://arxiv.org/abs/2607.04438; "https://aka.ms/ResearchStudio" → https://aka.ms/ResearchStudio; "https://github.com/microsoft/ResearchStudio" → https://github.com/microsoft/ResearchStudio

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: each page's notes open with the takeaway in one sentence, then explain the evidence on the page in the order the eye reads it, name the paper section, figure, or table each number comes from, keep the paper's hedges, and close with a one-line transition to the next page; nothing outside the paper
- **Total duration**: 25 minutes (18 pages; skill and result pages about 2 minutes each, question, contribution, and conclusion pages about 1 minute)
- **Notes style**: formal
- **Presentation purpose**: walk a skeptical research audience through the paper in its own order so every conclusion can be traced to a figure, a table, or a stated method

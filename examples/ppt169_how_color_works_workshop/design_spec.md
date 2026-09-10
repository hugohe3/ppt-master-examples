<!-- ppt-master-schema: design-spec/v1 -->
# How Color Works - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | how_color_works_ppt169_20260910 |
| Canvas Format | PPT 16:9 — 1280 × 720 |
| Page Count | 14 |
| Primary Language | en-US |
| Target Audience | Working designers, front-end developers and marketers who choose colors every week — fluent in their tools, with no formal training in optics, color science or accessibility, sceptical of "design taste" arguments, and short on time |
| Communication Intent | Teach first, then persuade: give practitioners the minimum physical and physiological model they need, get them to apply it in two live exercises, and along the way keep what is a published rule separate from what is only an inherited convention, so they stop treating the two the same way |
| Desired Audience Outcome | Each participant can say why a specific color pair fails, check it against a WCAG threshold, extract and repair a five-color palette from a real image, and explain why a rainbow ramp is the wrong default for ordered data |
| Core Message / Ask / Action | Most color decisions that feel like taste are lightness decisions — separate hue from lightness, measure the lightness, and what is left is judgement you can defend |
| Delivery Context | Primary: a presenter-led 90-minute hands-on workshop with two working exercises at the participants' own screens. Secondary: the file is handed out afterwards and re-read alone |
| Artifact Afterlife | Reused as a self-serve reference and as material another facilitator can re-run; the source links must stay clickable |
| Reading Mode | balanced |
| Content Strategy | Balanced default (no material-divergence constraint stated). The research pair is the only fact source; every external number is cited by fact id and no figure is invented |
| Design Style | Studio Worksheet — a quiet warm-paper worksheet on a strict grid, where the only saturated color on any page is the color being taught |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — final Stage-2 proactive policy (`proactive_speaker_notes: true`) |
| Custom Animations | enabled — final Stage-2 proactive policy (`proactive_custom_animations: true`); the deck teaches by building swatches and states up in order |
| Narration Audio | disabled — final Stage-2 proactive policy (`proactive_narration_audio: false`) |
| Created Date | 2026-09-10 |

- **Template Application**: Adopt the Workshop Teaching method wholesale — its objective → minimum concept → worked demonstration → guided practice → common mistake → understanding check → recap sequence orders the roster, and its claim discipline becomes a visible labelling system on the pages (RULE / CONVENTION / RECOMMENDATION / PREFERENCE). Adopt its evidence obligations: charts teach a relationship and are labelled directly on the mark, the reference card is a native editable table, exercise pages stay visually distinct from teaching pages, and the incorrect and corrected states sit in direct correspondence. Adopt its color-behavior default of a light calm field with a fixed teaching mapping for new / changed / correct / wrong that survives without color alone, and its typography character of a warm legible sans with a genuinely monospaced companion for anything the learner types or reads as a value. Depart from its preferred `sketch-notes` visual style and rendering, and from its hand-adjacent decoration density, for one reason recorded in §III: this deck's subject is color itself, so the page's own palette and texture must recede completely; a warm-paper field with a strict grid and hairline rules keeps every saturated pixel available to the demonstrated colors, and precise swatch and contrast comparisons need exact edges rather than wobbled ones. The Style's functional annotation layer — an arrow that points at something specific, a mark on the part that changed — is kept, because it is the part of that decoration budget which carries information. The Style supplies no structure or roster, so the deck stays flat free design.

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 64 px left/right, 56 px top, 56 px bottom |
| Content Area | x 64–1216, y 56–664 (1152 × 608) |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: instructional
- **Mode Behavior**: Run the deck as one 90-minute teaching cycle rather than a topic tour: state the observable capability first, introduce each concept only at the moment it is needed to act, then demonstrate the whole task with real input and real output, hand the same task over for timed practice, show the two mistakes the learner is about to make with their actual cause, and close with a check that asks for application rather than recall. Titles say what the page teaches or what the learner does there. Every claim on a page is labelled as a rule, a convention, a recommendation or a preference, and a deliberate simplification is marked as one instead of being left to look complete.
- **Visual style**: custom
- **Visual Style References**: swiss-minimal, editorial, sketch-notes
- **Visual Style Behavior**: `swiss-minimal` owns the skeleton — a strict modular grid, flush-left alignment, exact square-cornered geometry, one large organizing plane per page and vast deliberate whitespace, strictly flat with no shadow or material. `editorial` owns the hierarchy — a kicker line above each page title, hairline rules instead of repeated cards, an asymmetric column split, and small labelled asides that carry the RULE / CONVENTION / RECOMMENDATION / PREFERENCE chips and the source lines. `sketch-notes` contributes only its functional annotation layer: a hand-weight arrow that points at one exact target, a ring around the part that changed, a short inline label next to it — never doodles, ribbons, wobbled containers or pastel blocks. The page field stays warm near-white and near-monochrome so that swatches, ramps, wheels and contrast pairs are the only saturated marks on the canvas.
- **Theme**: A studio worksheet — paper, a ruler-straight grid, ink, and the colors under examination pinned to it.
- **Tone**: Plain, unhurried, unsentimental; confident about what is measurable and honest about what is only convention.

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | `#FAF8F4` | The warm paper field of every page |
| Secondary background | `#EDE7DC` | Recessed panels: exercise blocks, reference card ground, aside tint |
| Primary | `#23201C` | Ink — page titles, rules that must read as structure, the darkest mark |
| Accent | `#A8452B` | The `new` teaching state: what is being introduced on this page; kicker rules and pointer marks |
| Secondary accent | `#3E5C6B` | The `changed` teaching state: what was just edited or repaired; hyperlink color |
| Body text | `#2E2A25` | All running text |
| Secondary text | `#6B6259` | Captions, annotations, source lines, footnotes |
| Divider | `#D8D0C3` | Hairline rules, column dividers, table borders |

Additional locked neutral and semantic tiers: `surface` `#FFFFFF` (the white card a swatch or chart sits on so a light demonstrated color still has an edge), `grid` `#E8E1D5` (chart hairlines, lighter than dividers), `positive` `#2E7D32` (the `correct` state), `negative` `#C62828` (the `wrong` state), `warning` `#F57C00` (a borderline result).

**Fixed teaching mapping, reused on every page and never re-assigned**: `new` = accent `#A8452B` plus a filled square marker; `changed` = secondary accent `#3E5C6B` plus a dashed outline on the edited element; `correct` = positive `#2E7D32` plus a check glyph and the word PASS; `wrong` = negative `#C62828` plus a cross glyph and the word FAIL. Every state carries a glyph and a word, so the deck's own status encoding survives being read by someone who cannot separate its hues — which is itself the point of P12.

**Demonstrated colors are content, not identity**: the five palette colors sampled from the P08 artwork, the hue-wheel wedges, the lightness ramp steps and the before/after contrast pairs are page-local content paint derived from the material, not palette roles, and never replace an anchor above.

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: ink-notes, editorial
- **Image Rendering Behavior**: Explanatory pen-on-paper drawing on the deck's own warm paper field. `ink-notes` owns the mark — confident medium-weight ink line work in the deck's body-text tone with a slight human wobble, flat, no shadow, no grain, backgrounds and fills left mostly empty so the line carries the explanation. `editorial` owns the composition — one dominant focal subject, deliberate alignment to invisible columns, generous negative space, and simple geometric forms rendered with editorial confidence rather than cartoon warmth. Color stays under 10% of each image and comes only from the deck's accent and secondary-accent roles, except where the drawing's own subject is light itself, where the spectrum it disperses is the subject and may be fully saturated.
- **Visual**: Ink line drawings of physical apparatus and anatomy — a prism on a bench, an eye in section, a press sheet beside a lit screen — drawn as if by a patient instructor mid-explanation, with everything not being explained left as bare paper.
- **Mood**: The margin of a good textbook: unhurried, exact, hand-made but not cute. Closest real-world analogy is a Mike Rohde sketchnote redrawn with an architect's discipline.

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | Humanist sans, warm, slightly calligraphic terminals | Trebuchet MS | — | — |
| Body | Humanist sans, open apertures, high legibility at distance | Segoe UI | — | — |
| Display | Monospaced, lining figures, exact digit widths | Consolas | — | — |
| Data | Monospaced, lining figures | Consolas | — | — |

- **Title stack**: `Trebuchet MS`
- **Body stack**: `Segoe UI`
- **Display stack**: `Consolas`
- **Data stack**: `Consolas`
- **Role rationale**: `Display` and `Data` leave the body family deliberately. Every number in this deck is a value the learner is expected to read exactly and often to type — hex triplets, contrast ratios, wavelengths, percentages — and the Style requires a genuinely monospaced companion for anything the learner types. `Display` carries the recurring hero ratios and percentages at scale; `Data` carries inline hex and ratio values inside running text and inside the reference table.

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 42 |
| Subtitle | 32 |
| Annotation | 18 |
| Cover title | 72 |
| Lead | 30 |
| Display | 64 |
| Data | 22 |
| Footnote | 16 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: A kicker line and a hairline rule at the top left establish where the page sits in the 90 minutes; the title states what happens here; attention then drops into one dominant demonstration region on the right or lower two-thirds, with the labelled claim chips and source line held at the bottom left where they never compete with the color being shown.
- **Composition tendency**: One large organizing plane or one dominant specimen region per page against wide margins; asymmetric splits rather than even columns; the demonstrated color always sits on the white `surface` tier so a pale sample still has an edge. Teaching pages keep a light two-region rhythm; the reference card and the check page may run denser under the same grid.
- **Cross-page continuity**: The kicker/rule/title lockup, the claim chips, the fixed four-state teaching mapping and the source line recur on every page. The hue wheel introduced on P05 is the same object on P06; the five sampled swatches introduced on P08 are the same five objects on P09 and are referenced again on P10. Exercise pages (P10) and the check page (P13) carry the recessed `secondary_bg` ground so a learner scanning the handout later finds them without reading.
- **Spacing posture**: Open on teaching and concept pages, deliberately denser on the reference card (P07) and the check page (P13), never uniform.
- **Spacing anchors**: page margin 64 px · block gap 32 px · column gutter 40 px · corner radius 4 px · body leading 36 px.

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| `tabler-outline/eye` | Vision, perception, what the viewer actually receives |
| `tabler-outline/bulb` | Light as a physical source; a point being introduced |
| `tabler-outline/palette` | Palette construction and color choice |
| `tabler-outline/color-swatch` | An individual sampled color, swatch handling |
| `tabler-outline/contrast` | Contrast, lightness comparison, the measurable rule |
| `tabler-outline/droplet` | Pigment, ink, subtractive mixing |
| `tabler-outline/device-desktop` | Screens, emitted light, additive mixing |
| `tabler-outline/printer` | Print output, physical reproduction |
| `tabler-outline/ruler` | Measurement, thresholds, checking a value |
| `tabler-outline/alert-triangle` | The common mistake, a warning about a tempting error |
| `tabler-outline/circle-check` | A passing result, a completed objective |
| `tabler-outline/circle-x` | A failing result |
| `tabler-outline/clock` | Timing inside the 90-minute run sheet, exercise duration |
| `tabler-outline/pencil` | Guided practice, something the learner does |
| `tabler-outline/help-circle` | The understanding check |
| `tabler-outline/link` | External tools and further reading |
| `tabler-outline/chart-bar` | Data encoding, ordered data |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P03 | chart | column_chart | Compare where the three cone types peak along the spectrum |
| P07 | table | comparison_matrix | Look up the required contrast ratio by text class and conformance level |
| P12 | chart | horizontal_bar_chart | Compare how common each type of red-green color vision deficiency is among men |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `prism_bench.jpg` | 1920×1072 | 16:9 | Cover hook: light arriving as one beam and leaving as a spectrum | Illustration | Full-canvas field the cover title sits inside, with the dispersed spectrum band low and right so the display title keeps clean paper above and left of it | adaptive | ai | Generated | An ink line drawing of a triangular glass prism standing on a plain workbench; a single narrow beam enters from the left and leaves the far face as a widening fan of spectral color that falls across the bench surface; the bench, the prism and the beam are bare line work on the deck's paper field, and the dispersed fan is the only saturated area | none | hero_page |
| `eye_cones.png` | 1032×444 | ~2.33:1 | Show that the eye samples the spectrum with three receptors rather than measuring it | Illustration | Transparent drawing sitting in the page's right region beside the chart, its inset aligned to the chart's category axis so the three receptors and the three chart columns read as the same three things | no-crop | slice | Generated | Derived from `teaching_sheet.png`; top cell | none | local |
| `press_and_screen.png` | 800×385 | ~2.08:1 | Anchor additive and subtractive mixing to the two physical systems the learner actually ships into | Illustration | Transparent drawing along the lower band of the page, the press half sitting under the subtractive diagram and the screen half under the additive one so each drawing labels the diagram above it | no-crop | slice | Generated | Derived from `teaching_sheet.png`; bottom cell | none | local |
| `great_wave_fit.jpg` | 1400×967 | ~1.45:1 | The real specimen the demonstration palette is sampled from | Photo | Shown complete on the left of the page as the specimen under examination, with the sampled swatches building down the right against it | no-crop | web | Sourced | Derived from `great_wave.jpg`; treatment=fit 1400x970 | none | local |

## IX. Content Outline

### Part 1: The contract

#### Slide 01 - Cover

- **Audience move**: Arrives expecting another opinionated talk about taste → understands within one screen that this session is about a physical system with measurable rules
- **Relationships**: One title, one subtitle and one run-time promise; no order, link or hierarchy among them beyond title → qualifier
- **Cover impact**: The hook is the prism itself — one beam in, a spectrum out — stated as the line "One beam goes in. Everything you argue about comes out." The composition is a Reference: display title on clean paper in the upper left, the dispersed band low across the canvas, nothing overlapping the title
- **Composition**: Full-canvas illustration field, display title flush left in the upper third on bare paper, a hairline rule under it, the subtitle and the 90-minute stamp below
- **Title**: How Color Works
- **Core message**: Color is a physical system you can reason about, and this session hands you the parts of it you can actually check.
- **Content**: Display title `How Color Works` · subtitle `A 90-minute hands-on workshop for people who choose colours every week` · hook line · run stamp `90 minutes · two exercises · bring a screen`
- **Images**: `prism_bench.jpg`
- **Motion suggestion**: The beam should arrive before the spectrum exists — the title and the incoming beam settle first, then the dispersed band spreads outward from the prism's far face
- **Fact IDs**: F001

#### Slide 02 - What you will be able to do

- **Audience move**: Wants to know whether this is worth 90 minutes → holds four concrete, observable capabilities and knows exactly when each one gets practised
- **Relationships**: Four learning objectives, each an observable action; the run sheet's five time blocks map onto them in order — objective → the block that delivers it
- **Composition**: Objective list dominant on the left as the contract; the run sheet as a quiet timed rail down the right, deliberately subordinate
- **Title**: By the end of this session you will be able to
- **Core message**: Four things you will be able to do — not four topics you will have heard about.
- **Content**: Four objectives as observable actions: name why a colour pair fails · check any pair against a WCAG threshold and read the result · pull a five-colour palette off a real image and repair the pair that fails · say why a rainbow ramp is the wrong default for ordered data · 90-minute run sheet with five blocks and their minutes · one honest note that this session simplifies and marks where it does
- **Motion suggestion**: The four objectives arrive one at a time in order; the run-sheet rail is already in place and does not move

### Part 2: The minimum model

#### Slide 03 - Your eye does not measure light

- **Audience move**: Assumes the eye reads colour the way a spectrometer does → understands that colour is a three-number summary the brain builds from three overlapping receptors
- **Relationships**: The spectrum is a continuous range; three cone types each sample it; each cone has one peak wavelength — parent (spectrum) to members (three cones), each member carrying one value
- **Composition**: A continuous spectrum band across the top as the thing being sampled; below it the three-column chart of the peaks on the left and the eye drawing on the right, the drawing's three receptors aligned to the chart's three categories
- **Title**: Your eye does not measure light — it samples it three times
- **Core message**: Everything you will ever see is reconstructed from three numbers, which is why colour behaves less like physics and more like a summary.
- **Content**: Visible light runs roughly 380–700 nm, and that boundary is soft — different authorities round it differently, so it is a convention not a constant `CONVENTION` · human vision is trichromatic: three cone types named S, M and L for where they peak `RULE` · measured mean peaks approximately 420 nm (S), 534 nm (M), 563 nm (L) `RULE` · about 6 million cones against about 120 million rods, roughly 5% of photoreceptors, concentrated in the fovea · marked simplification: the real curves overlap heavily and are not three clean spikes, and the full tabulated dataset lives at CVRL
- **Visualization**: `cone-peaks` — column chart, three categories (S cone, M cone, L cone), one series, values 420 / 534 / 563, axis labelled in nanometres from zero, each column labelled directly on the mark, each column filled with an approximation of the hue near its own peak so the chart is also a spectrum reading
- **Native-ready**: `cone-peaks`=yes
- **Images**: `eye_cones.png`
- **Motion suggestion**: The spectrum band exists first, then the three columns rise one at a time in wavelength order, each one pulling its matching receptor in the drawing into view
- **Fact IDs**: F001, F002, F003, F004, F005, F006

#### Slide 04 - Two ways colour mixes

- **Audience move**: Has been mixing screen colours and print colours with the same mental model → can say which system they are in and predict which way a mix will move
- **Relationships**: Two mixing systems in contrast; within each, three primaries combine pairwise and then all together; across the two, each additive primary is a subtractive secondary — a one-to-one correspondence
- **Composition**: A hard vertical split; three overlapping discs on the left starting from a dark field, three overlapping discs on the right starting from a white field, identical geometry so only the result differs; the drawing runs as a low band underneath, anchoring each half to its physical machine
- **Title**: Two ways colour mixes, and you ship into both
- **Core message**: Adding light and adding pigment move in opposite directions, and every argument about "the colour looked different" starts here.
- **Content**: Additive mixing starts from black and adds red, green and blue light; all three at full intensity give white; every screen works this way `RULE` · subtractive mixing starts from white paper and each cyan, magenta or yellow layer absorbs part of the spectrum, so more pigment gets darker; all physical print works this way `RULE` · the two primary sets are complements of each other — each additive primary is a secondary mixture in the subtractive system and the reverse · practical consequence: a colour picked on a screen has no obligation to be reachable in ink
- **Images**: `press_and_screen.png`
- **Motion suggestion**: Each side builds in the same order — one disc, two discs with their overlap, three discs with the centre — so the two systems are seen diverging step for step
- **Fact IDs**: F007, F008, F009

#### Slide 05 - Three dials, and the schemes built on one of them

- **Audience move**: Treats complementary and triadic schemes as rules handed down from the physics of light → recognises them as one teacher's teaching device drawn on one of three dials
- **Relationships**: One colour decomposes into three independent components; the named harmony schemes are angular selections on only the first of them — parent (hue dial) to members (four schemes), while saturation and lightness are siblings the schemes ignore
- **Composition**: A large hue wheel dominating the right two-thirds with the four scheme geometries drawn as selections on it; the three dials stacked as labelled tracks on the left; the claim chip sits on the scheme block, not the wheel
- **Title**: Three dials — and the schemes that only turn one of them
- **Core message**: Harmony schemes are conventions inherited from specific teachers, and they only ever touch one of the three dials.
- **Content**: HSL: hue as an angle 0–360° around a circle (red 0/360, green 120, blue 240), saturation 100% to 0% grey, lightness 0% black to 100% white `RULE` · complementary, analogous, triadic and split-complementary are angular picks on the hue dial `CONVENTION` · the vocabulary traces to Johannes Itten's twelve-hue wheel in *The Art of Color* (1961), from the colour course he taught at the Bauhaus, and he catalogued them as categories of contrast for teaching, not as laws · Munsell built a competing system on perceptually equal steps, and different models produce different "complementary" pairs, so the scheme depends on which wheel you drew it on · what to take from it: schemes are a fast way to get a starting set, and nothing more `RECOMMENDATION`
- **Motion suggestion**: The wheel arrives whole and stays; each scheme's geometry is drawn onto it in turn and cleared before the next, so the wheel is visibly the constant and the scheme the variable
- **Fact IDs**: F010, F024, F025

#### Slide 06 - Lightness is the dial that carries legibility

- **Audience move**: Believes a strong colour difference means a readable colour difference → can predict failure from lightness alone and knows there is a formula behind it
- **Relationships**: One dial of the three is singled out; the accessibility definition depends on it and on nothing else; two demonstration pairs contrast with each other — same hue and far apart in lightness passes, different hue and close in lightness fails
- **Composition**: The same wheel from the previous page, now with hue and saturation removed so only the lightness of each wedge remains, held in the same position; the two demonstration pairs stacked beside it with their measured ratios; the formula set as a quiet monospaced line beneath
- **Title**: Lightness is the dial that carries legibility
- **Core message**: The accessibility rule contains no hue term at all — only relative luminance — which is why two colours that look nothing alike can still be unreadable together.
- **Content**: The W3C's text-contrast rule is defined purely as a function of the two colours' relative luminance, with no hue or saturation term `RULE` · relative luminance is computed from gamma-linearised sRGB channels · demonstration A: two colours far apart in hue, close in luminance — reads as mud, FAIL · demonstration B: two tones of one hue, far apart in lightness — reads cleanly, PASS · the practical instruction: judge the pair in greyscale first, and only then argue about hue `RECOMMENDATION`
- **Mathematical content**: L = 0.2126R + 0.7152G + 0.0722B
- **Motion suggestion**: Continuous with the previous page — the wheel stays exactly where it is and drains of hue in place; only then do the two demonstration pairs enter
- **Fact IDs**: F011, F012

### Part 3: The rule you can check

#### Slide 07 - The numbers you actually have to hit

- **Audience move**: Knows "4.5:1" as a slogan → can look up the exact threshold for their case, including large text and non-text elements, and knows what counts as large
- **Relationships**: Two conformance levels against three element classes form a grid of required minimums; the definition of large text is a qualifier attached to one row; the ratio formula is the shared method beneath the whole grid
- **Composition**: Reference-card density under a strict grid — the table dominant and centred, the formula and the large-text definition as flanking asides, lookup optimised over reading order
- **Title**: The numbers you actually have to hit
- **Core message**: There are five numbers in the whole rule, and you can check any of them in about ten seconds.
- **Content**: Contrast ratio is `(L1 + 0.05) / (L2 + 0.05)` using the lighter and darker relative luminances, ranges from `1:1` to `21:1`, and must not be rounded before it is compared with a threshold `RULE` · large text means at least 18 pt, or at least 14 pt bold, or an equivalent visual size for CJK — roughly 24 px and 18.5 px `RULE` · SC 1.4.11 puts a `3:1` floor on user-interface components and on graphical objects needed to understand the content, which is what governs your icons and your chart lines `RULE` · reference card: keep this page, it is the one you will come back to
- **Visualization**: `wcag-thresholds` — comparison matrix; rows are Normal text, Large text, Non-text and UI components; columns are Level AA and Level AAA; cells hold `4.5:1`, `7:1`, `3:1`, `4.5:1`, `3:1`, and `3:1 (no higher AAA requirement)`; each cell also carries the governing success criterion number
- **Native-ready**: `wcag-thresholds`=yes
- **Fact IDs**: F013, F014, F015, F016, F017, F018, F019

### Part 4: Worked demonstration

#### Slide 08 - Demonstration, step 1: pull five colours off one print

- **Audience move**: Has never sampled a palette from an image in a defensible way → has watched the whole extraction done once, including the unglamorous part
- **Relationships**: One source image yields five sampled colours; each swatch links back to a named region of the print; the five together form an ordered set from darkest to lightest
- **Composition**: The complete print held on the left as the specimen; the five swatches building down the right as a column, each with its sampled region named and its hex value set in monospace
- **Title**: Demonstration — five colours out of one print
- **Core message**: A palette is a set of samples taken from something real, with the sampling decisions visible.
- **Content**: The specimen: Hokusai, *Under the Wave off Kanagawa*, from *Thirty-six Views of Mount Fuji*, colour woodblock print, c. 1830–32, The Metropolitan Museum of Art, released under the Met's Open Access programme (launched 7 February 2017) as CC0 · the method, stated as steps: sample the largest area first, then the darkest, then the lightest, then two accents from regions that carry meaning rather than area · every swatch keeps the region it came from written next to it · the unglamorous step said out loud: the raw samples are not yet a palette, because nothing has been measured
- **Images**: `great_wave_fit.jpg`
- **Motion suggestion**: The print is in place first; each swatch then leaves its region and settles into the column in sampling order, so the origin of every colour is seen once
- **Fact IDs**: F029, F030

#### Slide 09 - Demonstration, step 2: measure it, then repair the one that fails

- **Audience move**: Assumes a palette that looks harmonious is usable → has watched a real pair fail a real threshold and be repaired by moving lightness only
- **Relationships**: The same five colours from the previous page are tested pairwise against one threshold; each pair carries a pass or fail state; exactly one failing pair is then changed, and the change is on the lightness dial only
- **Composition**: The five swatches carried across in the same order, now laid out as a small pairwise grid of results; the failing pair lifted out and shown before and after in direct correspondence, the repaired swatch ringed as the changed element
- **Title**: Now measure it — and repair the one pair that fails
- **Core message**: Measuring turns a palette argument into a two-minute edit, and the edit is almost always a lightness edit.
- **Content**: Test each pair you intend to actually put together against the `4.5:1` body-text threshold `RULE` · the grid: which pairs pass, which fail, with the computed ratios shown · the failing pair, isolated, with its ratio · the repair: hold the hue, hold the saturation, move the lightness until the ratio clears — and show the new ratio · what did not happen: no hue was changed, so the palette still reads as the same palette · honest note: a palette that passes is not automatically good, it is only usable `PREFERENCE`
- **Motion suggestion**: The five swatches are already present and do not re-enter; only the pair results, then the isolated failing pair, then its repaired state arrive
- **Fact IDs**: F013, F019

### Part 5: Your turn

#### Slide 10 - Guided practice: 12 minutes

- **Audience move**: Has watched the task done → does the same task on their own material with a stated success condition and a stated escape route
- **Relationships**: One task decomposed into four ordered steps; one success condition; one escape route; the steps depend on each other in sequence
- **Composition**: The exercise page must look unlike a teaching page at a glance — recessed ground, the task and its success condition boxed and dominant, explanation reduced to a single line, timing and the escape route on a quiet rail
- **Title**: Your turn — 12 minutes
- **Core message**: Build a five-colour palette from an image you brought, then prove one pair of it passes.
- **Content**: Task: open any image you own, sample five colours by the order used in the demonstration, then measure the pair you would actually use for body text on background · Starting point: your own image, and the contrast checker from the last page of this deck · Success condition, stated exactly: five hex values written down, one measured ratio, and that ratio at or above `4.5:1` · If you get stuck: stop sampling for meaning and sample by area, largest first · Time: 12 minutes, then we compare three of them out loud
- **Motion suggestion**: The four steps enter in order and stay; nothing else on the page moves once the task is up

### Part 6: What goes wrong

#### Slide 11 - Mistake 1: saturation is not contrast

- **Audience move**: Reaches for a more saturated colour when text is hard to read → recognises that move as the mistake and knows the correction is on a different dial
- **Relationships**: One incorrect state placed in direct correspondence with one corrected state; the cause links to the rule established on P06; the tempting reason is named beside the error rather than after it
- **Composition**: A hard before/after pairing at equal size and equal position so only the treatment differs, with the actual cause set between them and an arrow pointing at the one thing that changed
- **Title**: Mistake 1 — turning up the saturation
- **Core message**: Saturation makes a colour louder; it does not make it more readable, because the rule never looks at saturation.
- **Content**: What it looks like: a caption that is hard to read, "fixed" by pushing the accent to full chroma · Why it is tempting: the colour genuinely does look stronger, and on a large bright monitor it may even look fine to you `PREFERENCE` · The actual cause: relative luminance barely moved, so the measured ratio barely moved — shown with both ratios · The correction: change the lightness, keep the hue, re-measure `RECOMMENDATION` · both states shown in greyscale beneath, where the failure is obvious without any measurement
- **Motion suggestion**: The incorrect state is present first and stays; the corrected state arrives beside it, and only then the pointer to the single property that changed
- **Fact IDs**: F011, F013

#### Slide 12 - Mistake 2: a rainbow ramp for ordered data

- **Audience move**: Uses a spectral colour map because it looks rich and uses the whole range → can give three concrete reasons it distorts and knows who it locks out
- **Relationships**: One incorrect encoding against one corrected encoding; three named defects of the incorrect one; a separate population fact that compounds every hue-only encoding — the two link as cause and multiplier
- **Composition**: Before/after ramp pairing across the top in the same frame the previous page used, with the horizontal prevalence chart carrying the lower band and one arrow tying the chart back to the ramp
- **Title**: Mistake 2 — a rainbow ramp for ordered data
- **Core message**: A rainbow ramp has no perceptual order, and the people it fails hardest are already about one in twelve of the men in the room.
- **Content**: Three documented defects, from Borland & Taylor (2007): it lacks perceptual ordering, so equal-looking colour steps are not equal data steps; its uncontrolled luminance variation across hues obscures the data; and it can create gradients unrelated to anything in the data `RULE` · Crameri, Shephard & Heron (2020, *Nature Communications*) find rainbow-like and red-green maps still common in published science, visually distorting data and unreadable to people with colour-vision deficiency, and propose perceptually uniform maps instead `RECOMMENDATION` · about 1 in 12 men have a colour vision deficiency (US National Eye Institute); worldwide, red-green deficiency runs about 8% of men and 0.5% of women, rising to roughly 10–11% of men in some Northern European populations · blue-yellow deficiency and total colour blindness are far rarer, on the order of 1 in 30,000–50,000 · the correction: a ramp that increases monotonically in lightness, so it survives greyscale and survives being read by anyone
- **Visualization**: `cvd-types` — horizontal bar chart, four categories (Deuteranomaly, Deuteranopia, Protanomaly, Protanopia), one series, values 5 / 1 / 1 / 1 in percent of men, each bar labelled directly with its value, with the 8% total stated as an annotation rather than a fifth bar
- **Native-ready**: `cvd-types`=yes
- **Motion suggestion**: The rainbow ramp and its replacement hold the same frame as the previous page's before/after; the four bars then grow in order from the most common
- **Fact IDs**: F020, F021, F022, F023, F027, F028

### Part 7: Close

#### Slide 13 - Check for understanding

- **Audience move**: Believes they followed along → tests that belief against three questions that require applying the rule rather than recalling it
- **Relationships**: Three independent application questions, each traceable to one earlier objective; each has a verifiable answer the learner can check themselves; the answers are separated from the prompts
- **Composition**: Recessed ground like the exercise page so it is findable later; the three questions dominant and evenly weighted; the verifiable answers held apart in a quiet band at the bottom rather than beside their questions
- **Title**: Check yourself — three questions
- **Core message**: If you can answer these three from the page, the session did its job.
- **Content**: Q1 — you have two colours with a measured ratio of `3.8:1` and you must use them for 16 px body text: what exactly do you change, and why that and not the hue? · Q2 — a colleague says a palette is "harmonious because it is triadic": which part of that is a rule and which part is a convention? · Q3 — you have a sequential heat map in a rainbow ramp: name two things that go wrong before you consider anyone's vision at all · Answers, verifiable against this deck: `4.5:1` is the AA threshold for that text size, so lightness must move until the measured ratio clears it, because the formula has no hue term · none of it is a rule — triadic is an angular convention on one dial, and harmony is not a measurable property · no perceptual ordering, and uncontrolled luminance variation across hues
- **Motion suggestion**: The three questions arrive together and hold; the answer band arrives only once, as a single later state, so the questions can be read alone first
- **Fact IDs**: F013, F015, F027

#### Slide 14 - Recap and where to go next

- **Audience move**: Holds four new capabilities and no idea where to continue → leaves with the four capabilities restated against the opening contract and six named destinations they can open immediately
- **Relationships**: The four recap points map one-to-one back onto the four opening objectives; six external destinations, each linked to the specific capability it extends
- **Closing impact**: The binding takeaway is the core message stated once as a working instruction — separate hue from lightness, measure the lightness, then argue. Composition is a Reference: the recap mirrors the P02 objective list so progress is visible, with the destinations as a linked rail
- **Composition**: Two-column close — the recap on the left in the exact shape of the P02 contract, the six destinations on the right as an ordered linked list with what each one is for
- **Title**: What you can do now, and where to go next
- **Core message**: Separate hue from lightness, measure the lightness, and argue about what is left.
- **Content**: Four recap points mirroring the four opening objectives, each phrased as the action now available · six destinations with live links: WebAIM Contrast Checker (compute a ratio and read AA/AAA pass-fail) `https://webaim.org/resources/contrastchecker/` · W3C How to Meet WCAG quick reference (every success criterion and technique, filterable) `https://www.w3.org/WAI/WCAG22/quickref/` · Coblis (upload an image and see it under each type of colour vision deficiency) `https://www.color-blindness.com/coblis-color-blindness-simulator/` · ColorBrewer (choose sequential, diverging and qualitative schemes properly) `https://colorbrewer2.org/` · Adobe Color (build themes, including the harmony generators from P05) `https://color.adobe.com` · CVRL at the UCL Institute of Ophthalmology (the primary cone-fundamentals data behind P03) `http://www.cvrl.org/` · one honest closing note naming what this session simplified: the cone curves overlap far more than three columns suggest, and contrast ratio is a floor, not a measure of quality
- **Motion suggestion**: The recap points arrive in the same order as the P02 objectives so the two lists visibly correspond; the destination rail is already in place
- **Fact IDs**: F031, F032, F033, F034, F035, F036

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: Written for a facilitator running this live for the first time. Each page's notes give the transition in from the previous page, the one thing to say that the slide deliberately does not print, the question the learner is most likely to ask at that moment with its answer, and — on the two exercise-adjacent pages — the exact timing call and what to do if the room is behind. Every number stated in the notes is one already sourced on the page; the notes introduce no fact that is not in the research pair. Where the deck simplifies, the notes say what the simplification is so a facilitator asked a harder question can answer honestly.
- **Total duration**: 90 minutes total session; approximately 55 minutes of presented material across the 14 pages, with 12 minutes of guided practice at P10 and the remainder in discussion and comparison
- **Notes style**: Conversational and patient, in the instructional register — define before using, analogy then principle, signpost every transition
- **Presentation purpose**: Teach first, then persuade — deliver the minimum model, get it applied live in two exercises, and keep published rules distinct from inherited conventions

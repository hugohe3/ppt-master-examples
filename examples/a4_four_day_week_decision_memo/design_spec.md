<!-- ppt-master-schema: design-spec/v1 -->
# Four-Day Week Decision Memo - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | four_day_week_memo_a4_20260910 |
| Canvas Format | A4 Print (1240×1754) |
| Page Count | 10 |
| Primary Language | en-GB |
| Target Audience | The executive committee of a 200-person UK professional-services firm — managing partner, COO, finance director, HR director and two practice heads. They know the four-day week as a headline and a recruitment talking point, not as an evidence base; they care about client service, realisation and utilisation, cost, and senior retention, and they are sceptical of advocacy numbers. |
| Communication Intent | Put a go/no-go decision in front of the committee. First establish what the public evidence actually supports and where it is weak or absent; then set out the options and their trade-offs; then ask for a decision on a bounded pilot. Argue honestly rather than persuasively — the memo must survive hostile reading and being quoted back later. |
| Desired Audience Outcome | Each member can state, unprompted, which findings are robust and which are self-reported or statistically insignificant; can name the two or three conditions that would make this fail at this firm; and can approve, reject, or defer a defined pilot with named owners, metrics and kill criteria. |
| Core Message / Ask / Action | The wellbeing case is strong, replicated and controlled; the business case is unproven rather than disproven, on the pilots' own admission; and professional services is precisely where the model has been observed to fail. So the defensible move is a six-month, redesign-first pilot on 100-80-100 in two practice groups with pre-agreed kill criteria — not a firm-wide commitment and not a compressed week. |
| Delivery Context | Primary: a reader-led A4 memo, printed and circulated as a PDF 48 hours before the committee meeting, read alone with no presenter. Secondary: the working document in a 30-minute committee discussion, annotated in the margin. No live presentation, no projection. |
| Artifact Afterlife | The decision record for this question: filed in the board pack, cited in the minutes, audited later against what was known at the time, and reused as the terms of reference if a pilot is approved. |
| Reading Mode | text (read-close; the A4 print equivalent of a document-carried deck) |
| Content Strategy | Reshape the research supplement freely into an answer-first decision argument — regroup, reframe and sequence as the committee's decision requires. Every figure keeps its source, period and basis; no figure is invented, and the only unsourced values are the pilot's own design parameters and the risk ratings, each labelled illustrative. |
| Design Style | Printed decision record — swiss-minimal grid discipline in a portrait print memo: a fixed running header and footer, a two-column measure on evidence pages, hairline rules instead of cards, one burnt-vermilion accent reserved for the answer and the recommendation, and a slate second accent reserved for counter-evidence. |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — workflow default retained; on a reader-led memo the notes carry the "if asked in the room" reasoning and the provenance of each figure, which the afterlife (minutes, later audit) needs |
| Custom Animations | enabled — explicit run instruction requiring custom animations, light entrances on the main content units only |
| Narration Audio | disabled — workflow default; there is no presenter and no recorded delivery |
| Created Date | 2026-09-10 |

- **Template Application**: Adopt the Consulting Decision style as the communication method and the design direction only — it carries no prototypes, so every page is composed freely. Take its pyramid argument flow (governing question → overall answer → key supports → page message → evidence) and its assertion-title discipline as binding on the roster; take its page-role vocabulary as the roster's spine, using executive synthesis, situation/complication/resolution, driver decomposition, current-state diagnosis, comparison/benchmark (twice — once for persistence, once for comparability), recommendation, roadmap, risk/mitigation and appendix/evidence, and omitting process/operating model because no operating flow is being decided. Keep its claim discipline literally: facts, assumptions, implications and recommendations stay semantically distinct and visibly labelled. Keep its swiss-minimal visual preference and its restrained-accent colour behaviour; keep its chart rules (direct labels, no legends or chart furniture, retained units and source lines) and its table rules (columns derived from the decision logic, aligned units and periods, colour only where it carries declared meaning). Its "minimalist-swiss" image rendering is retained as the deck's rendering identity but no image is acquired — see §III. Identity is unowned by the template, so the palette and type system below are this project's.

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | A4 Print |
| Dimensions | 1240 × 1754 |
| viewBox | `0 0 1240 1754` |
| Margins | 80 px on all four sides (≈13.5 mm at 150 dpi-equivalent print scale; 1240 px = 210 mm, so 1 mm ≈ 5.905 px) |
| Content Area | x 80–1160 (1080 wide), y 80–1674 (1594 tall); running header occupies y 80–140 and the footer rule sits at y 1620 with footer text below it, leaving a body field of y 180–1600 |

## III. Visual Theme

### Theme Style

- **Mode**: pyramid
- **Visual style**: swiss-minimal
- **Theme**: A printed decision record. The page is a document, not a slide: a fixed masthead carrying the memo title, date and page number; a strict single grid whose columns change measure but never position; hairline rules doing the work that cards and shadows would do on screen; and evidence given more ink than framing. One burnt-vermilion accent has exactly one job — it marks the answer, the recommendation, and the single decision-relevant delta on a chart — and appears nowhere else. A slate second accent has exactly one job — it marks counter-evidence, control groups and caveats — so that the reader can see the shape of the argument's honesty before reading a word.
- **Tone**: Sober, exact, unsold. Assertion titles state a judgement; annotations state a basis. Nothing is claimed more strongly than its source supports, and where the source says "not statistically significant" the page says so at the same size as the number.

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | The page. Paper, unfilled, on every page |
| Secondary background | #F2F0EB | Evidence and appendix bands, table header fills, the one tint that separates a reasoning layer |
| Primary | #16232E | Ink: assertion titles, structural rules, dominant chart marks, established findings |
| Accent | #B4471C | One job only — the answer, the recommendation, and the single decision-relevant delta on a chart |
| Secondary accent | #4A6B7C | One job only — counter-evidence, control groups, caveats, and the critical reading of a study |
| Body text | #16232E | Running body text and table cells |
| Secondary text | #5C6871 | Captions, source lines, periods, bases, fact ids |
| Divider | #D6D2C9 | Hairline rules, table borders, the evidence-margin line |
| Surface | #F7F6F3 | Panel lift where a block must sit off the paper without a card |
| Grid | #E7E3DB | Chart gridlines and internal table rules, deliberately lighter than dividers |
| Muted | #6E777E | "No measurable effect" / "not statistically significant" marks and their labels |

Evidence strength is encoded as three tints of one system rather than a rainbow: established findings in Primary, self-reported or critical readings in Secondary accent, non-significant results in Muted. Body contrast on the page field is 15.3:1; Accent 5.4:1, Secondary accent 5.8:1, Secondary text 5.9:1 and Muted 4.6:1 all clear WCAG AA at body size.

### Cross-page motif

A single vertical hairline at x=430 divides an evidence margin (labels, periods, sources, fact ids) from the argument column on every body page. On synthesis and recommendation pages the argument column crosses it; on evidence pages it does not. Its continuity job is to make the claim-to-source path visible at a glance on every page, and it is the only decoration in the deck. Executor may adjust its position or decline it per page.

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | Neutral grotesque, bold, tightly tracked — decisive without shouting | Arial | — | Arial |
| Body | Neutral grotesque, regular — economical at print measure, silent under the evidence | Arial | — | Arial |
| Display | Heavy grotesque — used only for the answer line and hero numerals so the cover has a distinct voice without a second text family | Arial Black | — | Arial Black |

- **Title stack**: Arial
- **Body stack**: Arial
- **Display stack**: Arial Black
- **Role rationale**: Title and Body deliberately concord on one grotesque — swiss-minimal and consulting-decision both derive hierarchy from weight, scale, alignment and rule-work, and a second text family would add a voice the evidence layer does not need. Display (Arial Black) is the one deliberate exception, carrying the P01 answer line and the hero numerals only. Both faces have exact per-glyph advance data in this repository's width estimator, which matters on a dense A4 page where a wrapped assertion title changes the whole page's vertical rhythm. Data, Annotation and Footnote are size roles within the Body family and add no family override.

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 26 |
| Display | 84 |
| Title | 44 |
| Subtitle | 34 |
| Lead | 30 |
| Data | 22 |
| Annotation | 20 |
| Footnote | 16 |

Body is deliberately set well below the `a4` advisory band (44–58 px). That band derives from a poster-distance formula in `canvas-formats.md`; this artifact is a hand-held print memo, where 26 px on a 1240 px-wide A4 page is 4.4 mm ≈ 12.5 pt — the correct body size for print. A 51 px body would fit roughly 45 characters per full-width line and turn a nine-page argument into thirty pages.

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: Top-down and answer-first. The assertion title is read first and is always a complete judgement; the lead sentence beneath it states the basis of that judgement; the evidence block sits below or beside it and is visually subordinate but never small; the source line closes the page. Attention never has to travel back up.
- **Composition tendency**: One to three primary regions per page, stacked in the portrait direction rather than columned. Evidence pages use a narrow evidence margin (labels, period, basis, fact ids) beside a wide argument column; synthesis and recommendation pages let the argument span the full measure and breathe. At least one page sets running body text in two equal columns to test the print measure. No cards, no filled callout boxes, no elevation.
- **Cross-page continuity**: The masthead (memo title, date, page number, "Illustrative client" marker) and the footer rule recur unchanged on every page. The evidence hairline recurs on body pages. The accent's job and the slate's job never change. Section numbering runs 1–9 in the header on body pages.
- **Spacing posture**: Variable by page rhythm — `anchor` pages open, `dense` evidence pages tight but never below the body leading.
- **Spacing anchors**: page margin 80 px · block gap 40 px · column gutter 40 px · corner radius 0 px · body leading 38 px

## VI. Icon Usage Specification

- **Primary bundled library**: chunk-filled

| Icon Path | Suitable Scenarios |
| --- | --- |
| chunk-filled/checkmark | An outcome the evidence establishes |
| chunk-filled/x | An outcome the evidence refutes, or a firm that stopped |
| chunk-filled/minus | No measurable or significant effect |
| chunk-filled/triangle-exclamation | A caveat or a live risk |
| chunk-filled/circle-question | An open question or an unmeasured quantity |
| chunk-filled/arrow-trend-up | A measured increase |
| chunk-filled/arrow-trend-down | A measured decrease |
| chunk-filled/clock | Hours, period, duration |
| chunk-filled/users | Workforce, headcount, participants |
| chunk-filled/building | An organisation or participating company |
| chunk-filled/file | A report or primary source |
| chunk-filled/link | A live source reference |
| chunk-filled/flag | A decision gate |
| chunk-filled/target | A metric or kill criterion |
| chunk-filled/calendar | A phase or milestone |
| chunk-filled/coin | Cost, revenue, saving |

`chunk-filled` is chosen over the stroke library on print grounds: the icon README records that `tabler-outline`'s thin strokes weaken when printed, and this artifact's primary delivery is paper. Icons are used only where they encode a state, never as decoration or as a grid.

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P02 | chart | horizontal_bar_chart | Expose the gap between the week before and the hours actually worked after, study by study |
| P04 | chart | horizontal_bar_chart | Rank the UK 2022 pilot's measured changes and separate the significant from the not-significant |
| P05 | chart | column_chart | Compare how much of each cohort was still on reduced hours, on a stated basis and period |
| P06 | table | comparison_matrix | Set every study against the same comparability criteria for this firm |
| P09 | table | record_table | Hold the risk register: one row per risk with likelihood, impact, mitigation and owner |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

No image resource is planned. The deck's subjects are studies, magnitudes and a decision; none is an externally verifiable place, product, person or artefact the committee must recognise, so no image carries a factual or evidentiary job. The installed style's image direction ("use images only when they provide evidence, necessary context, or a causal explanation that shapes the decision … avoid atmospheric imagery that weakens the argument") makes a stock office photograph an active liability on a page whose credibility is the whole point. The `minimalist-swiss` rendering identity is retained as the deck's rendering candidate so that any later image request inherits it; it is not exercised here.

## IX. Content Outline

### Part 1: The answer

#### Slide 01 - Executive synthesis: should we move to a four-day week?

- **Audience move**: Arrives holding a headline and a recruitment argument → leaves holding one answer, the three things that make it credible, and the one gap that stops it being stronger.
- **Relationships**: One governing question; one overall answer; three supports beneath that answer (wellbeing evidence strong, business evidence unproven, sector evidence adverse) in order of decision weight; one material evidence gap that qualifies all three — parent → supports, plus contrast between support 1 and supports 2–3.
- **Cover impact**: The hook is the collision the whole memo turns on — 89% of the UK cohort were still running a four-day week a year later, and their own report states the business results are not statistically significant. Composition Reference: masthead, the governing question set small, then the answer at display scale across the full measure, then three hero numbers on a single rule with their supports beneath.
- **Composition**: One focal claim over three parallel supports; the answer dominates the upper third; the gap sits alone at the foot, on the accent rule.
- **Title**: Yes — as a bounded pilot in two practice groups, not as a firm-wide commitment
- **Core message**: The evidence supports trying this carefully here; it does not support promising it.
- **Content**:
  - Governing question · scope marker: a 200-person UK professional-services firm, illustrative and unnamed; every firm-specific figure in this memo is labelled illustrative
  - The answer, at display scale: run a six-month redesign-first pilot on 100-80-100 in two practice groups, with pre-agreed kill criteria; do not commit the firm
  - Support 1 — the wellbeing effect is large, controlled and replicated: burnout 2.8 → 2.34 and stress 3.07 → 2.74 across the UK cohort; a controlled six-country study of ~2,900 workers in 141 organisations finds the same gains absent in controls
  - Support 2 — the business case is unproven, not disproven: revenue +1.4% start-to-end and resignations 2.0 → 0.8 per 100, but the pilot's own report states these trends are not statistically significant
  - Support 3 — professional services is the observed failure mode: the single organisation of 28 that discontinued at twelve months was a consultancy, which stopped over client and stakeholder expectations despite reporting benefits
  - The gap: the cohort was overwhelmingly tiny firms — 37% had 1–10 staff, only 10% above 100 people — and no large UK professional-services firm with published results was found
  - Hero numbers: 89% still on reduced hours at 12 months · 0 business metrics reaching statistical significance · 1 of 1 professional-services discontinuation
- **Visualization**: three hero numerals with their basis lines, drawn natively; no keyed data object on this page
- **Fact IDs**: F005, F006, F008, F010, F012, F013, F018, F022, F028, F062, F067
- **Motion suggestion**: the answer line settles first, then the three supports in their stated order of decision weight, then the gap last; nothing else moves

### Part 2: The situation

#### Slide 02 - Situation, complication, resolution: the nominal week is not the worked week

- **Audience move**: Believes the choice is "four days or five" → understands the choice is "how many hours are actually recoverable here, and at what cost to clients".
- **Relationships**: Situation (what 100-80-100 means and where UK hours and productivity stand) → complication (in every measured pilot the realised reduction was smaller than the nominal one) → resolution (restated governing question); order, and contrast between nominal and actual within the complication.
- **Composition**: Three stacked bands in reading order; the chart owns the middle band and carries the contrast; the resolution sits alone under the footer rule area on the accent.
- **Title**: Every pilot promised eight hours back and delivered four to five
- **Core message**: The decision is about recoverable hours, not about a day of the week.
- **Content**:
  - Situation — the definition: 100-80-100 is 100% pay, 80% of the time, 100% output; created in 2018 by Andrew Barnes and Charlotte Lockhart at Perpetual Guardian and defined by 4 Day Week Global as a 32-hour week, not compressed hours
  - Situation — the UK baseline: average actual weekly hours for UK full-time workers were 36.7 in April–June 2026, so a 32-hour week is about a 13% cut against the national norm rather than 20%; UK output per hour was £46.92 in 2021, 10% below the average of the other G7 nations excluding Japan
  - Complication — the realised reduction: UK 2022 pilot 38 → 34 hours, not 32, with 71% reporting fewer hours and 15% reporting more; Portugal 41+ → 36.5 hours; the six-country study averaged about five hours, not eight
  - Resolution — restate the governing question: not "should we adopt a four-day week" but "how many hours can this firm recover through redesign, and what does removing the rest cost in client service?"
- **Visualization**: `nominal-vs-actual-hours` — clustered horizontal bar chart, one category per study (UK 2022 pilot, Portugal 2023–24, South Cambridgeshire DC) and two series, weekly hours before and weekly hours after, value axis titled "Weekly hours" from a zero baseline with direct value labels to one decimal. The planned dumbbell was replaced because the native chart payload has no dumbbell type and the object must stay natively editable; the clustered pair carries the same two values per study and the same gap. Native-ready: `nominal-vs-actual-hours=yes`
- **Fact IDs**: F011, F040, F063, F064, F068, F069

#### Slide 03 - Driver decomposition: what actually determines whether this works here

- **Audience move**: Treats the decision as a values question → treats it as four testable conditions, one of which the firm cannot control.
- **Relationships**: One governing outcome decomposed into four drivers (recoverable hours, client tolerance, redesign effort, retention economics); parent → branches, with a real overlap between recoverable hours and redesign effort, and a stated asymmetry — client tolerance is the only branch the firm does not own.
- **Composition**: A driver tree reading left to right across the full measure, the governing outcome at the left edge, four branches with their evidence stated beneath each; the client-tolerance branch marked as external.
- **Title**: Three of the four drivers are ours; the one that stopped a consultancy is not
- **Core message**: Whether 100-80-100 holds here is decided by recoverable hours, client tolerance, redesign effort and retention economics — and only client tolerance sits outside our control.
- **Content**:
  - Driver 1 — recoverable hours: the pilots' main levers were shorter and fewer meetings with clearer agendas, email-etiquette reform, protected focus periods, automated reporting, and in several cases a signed "efficiency charter"; Germany's participants named meeting culture and reduced distraction as the main levers
  - Driver 2 — client tolerance (external): the UK cohort's only twelve-month discontinuation was a small consultancy that could not manage client and stakeholder expectations in an industry that had not adopted working-time reduction, and could not apply the policy equitably across a small team; Belgium's reduced-hours pilot drew one fully participating company, citing legal uncertainty and concerns about reputation, teamwork and sectoral expectations
  - Driver 3 — redesign effort: only 8% of Portuguese companies that made two or more organisational changes reverted to five days, against 38% of those that made none or one; 75% made at least one change and 87% reported active worker participation in redesigning processes
  - Driver 4 — retention economics: resignations fell 2.0 → 0.8 per 100 employees in the UK pilot and Awin reports regrettable turnover down 33%; the most-cited UK replacement cost is £30,614 per employee, but that is an Oxford Economics figure published in February 2014 and is not inflation-adjusted, so any saving derived from it is illustrative arithmetic, not a finding
  - Implication (labelled as such): three drivers respond to preparation; the fourth responds only to evidence we do not yet have about our own clients
- **Visualization**: qualitative driver tree — one governing node, four branches, each with an evidence stub; drawn with preset shapes and connectors, no keyed data object
- **Fact IDs**: F008, F021, F028, F029, F037, F045, F050, F065, F070
- **Motion suggestion**: the governing node appears, then the four branches in stated order, then the external marker on branch 2; the branch geometry is the object that continues onto the next page

### Part 3: The evidence

#### Slide 04 - Current-state diagnosis: what the evidence establishes, and what it does not

- **Audience move**: Reads "four-day week works" as one claim → separates a robust wellbeing finding from an unproven business finding, and can say why.
- **Relationships**: Two contrasting groups of findings (established / not established) over the same cohort, each tied to its measured change; plus one membership relationship — every study in this memo shares the same four methodological limits.
- **Composition**: Dominant evidence, takeaway beneath. The chart holds the upper two-thirds with its significance marking; the methodological pattern runs as a labelled band beneath it.
- **Title**: The wellbeing result is established; the business result is unproven on the pilots' own admission
- **Core message**: Nothing in the public record establishes that revenue or retention improves; the wellbeing improvement is the finding that survives control groups.
- **Content**:
  - Established — worker wellbeing: a controlled study of nearly 2,900 workers across 141 organisations in six countries found improvements in burnout, job satisfaction, and mental and physical health that were absent in control organisations; Germany's pilot, instrumented with within-organisation controls, smartwatches and cortisol hair samples, found significant falls in stress and burnout, 38 minutes more sleep per week than controls, and substantially improved life satisfaction
  - Not established — the business case: the UK 2022 report states that because of small sample numbers and labour-market contingencies the resignation, new-hire and absence trends cannot be called statistically significant; Germany found sick days, turnover and profit changed only slightly and not significantly, and no strong evidence of any positive change in overall job satisfaction
  - Assumption to name (labelled as such): every revenue figure in this evidence base is self-reported by the participating firm
  - The standing methodological pattern, documented in the primary reports rather than asserted by critics: participation is self-selected by management; company financial data is self-reported; control arms are absent, small or non-random; follow-up samples shrink — 28 of 61 at twelve months, and only 44–51 of 61 supplied performance data at all
  - Implication: this evidence can justify a controlled trial; it cannot justify a commitment
- **Visualization**: `uk-2022-measured-changes` — horizontal bar chart of the UK 2022 pilot's measured changes: revenue +1.4% (start to end, 23 companies), revenue +34.5% (versus the same six months a year earlier, 24 companies), headcount −1.3% (34 organisations), resignations −57% (2.0 → 0.8 per 100), absence −65% (2.0 → 0.7 days per employee per month), burnout −16% (2.8 → 2.34 on a 1–5 composite). Bars whose trend the report declines to call significant are drawn in the slate counter-evidence role and carry a "not statistically significant" mark at label size; percent labels use an explicit percentage number format; the x-axis is titled "Change during the six-month trial". Native-ready: `uk-2022-measured-changes=yes`
- **Fact IDs**: F006, F007, F008, F009, F010, F012, F019, F024, F050, F051, F052, F062
- **Motion suggestion**: the established group resolves before the not-established group, so the reader meets the strong finding first and the caveat second

#### Slide 05 - Benchmark: how much of each cohort was still on reduced hours

- **Audience move**: Hears "92% continued" as proof → reads a persistence rate together with its base, its period and its self-selection.
- **Relationships**: Four cohorts compared on one measure with different bases; order by period, contrast between the largest base and the smallest, and one link — persistence is not the same as permanence.
- **Composition**: Equal comparison. The chart owns the page; each column carries its base beneath it; the two qualifying facts sit as a labelled block on the accent rule.
- **Title**: Persistence is high everywhere — and highest where the base is smallest
- **Core message**: The continuation rates are real, but they measure self-selected cohorts and they are not the same as a contractual entitlement.
- **Content**:
  - UK 2022 at the end of the trial: 56 of 61 companies (92%) continuing, 18 already permanent
  - UK 2022 at twelve months: at least 54 of 61 (89%) still running a four-day week; five (8%) discontinued and two did not respond; at least 31 (51%) permanent
  - Germany 2024 after the pilot: 34% extended, 39% ended the trial but kept reduced hours, 20% returned to a five-day 40-hour week, and two large organisations dropped out early citing economic reasons
  - UK 2024–25 pilot: all 17 companies continued a shorter week — but a 100% rate on 17 self-selected companies is a weaker signal than 89% on 61, and this memo does not lead with it
  - Qualification 1: of the 28 organisations in the twelve-month follow-up, 39% were permanent with updated terms and 39% permanent without changing contracts — an opt-in policy the employer can withdraw
  - Qualification 2: universal or staggered day-off models converted to permanent in 95% of cases against 60% for more flexible models, on a sample the authors state is too small for significance
- **Visualization**: `cohort-persistence` — column chart, one column per cohort (UK 2022 trial end · UK 2022 at 12 months · Germany 2024 still on reduced hours · UK 2024–25 pilot), y-axis titled "Share of participating organisations still on reduced hours" with an explicit percentage number format and a 0–100 domain; each column labelled directly with its value and, beneath the axis, its base (n=61, n=61, n=45, n=17). Native-ready: `cohort-persistence=yes`
- **Fact IDs**: F005, F022, F023, F025, F029, F053, F071

#### Slide 06 - Comparability: which of these studies is evidence about us

- **Audience move**: Treats Iceland and Belgium as supporting precedents → knows that one measured a one-to-three-hour cut in the public sector and the other is not an hours reduction at all.
- **Relationships**: Seven studies against five shared comparability criteria; membership in one comparison frame, with two explicit conflicts recorded inside the frame rather than resolved.
- **Composition**: Dense evidence page. The table spans the full measure under a short lead; the two recorded conflicts sit beneath it as labelled notes, each showing both readings.
- **Title**: Only two of these seven studies are evidence about a firm like ours
- **Core message**: Stated on a common basis, most of the frequently cited precedents are about different interventions, different sectors or different scales.
- **Content**:
  - UK 2022 — 61 companies, ~2,900 workers, June–December 2022, no control group, self-reported financials; professional services was the second-largest sector with seven firms; comparability moderate but the scale is wrong, since only 10% of the cohort was above 100 people
  - UK twelve-month follow-up (2024) — 28 of the original 61 participated; the one discontinuation was a consultancy; comparability high on sector, low on base
  - Iceland 2015–2019 — Reykjavík City Council and the national government, over 2,500 plus about 440 workers, 40 → 35/36 hours, productivity and service provision the same or improved, revenue neutral; and, on the same trials, Anthony Veal records that in 61 of 66 workplaces the reduction was only one to three hours and that the national agreements which followed formalised 35 minutes a week in the private sector and 65 in the public sector, with no monitored control sample and a probable Hawthorne effect; comparability low — public sector, small reduction
  - Belgium 2022 — the Labour Deal permits a 38-hour week to be worked in four days at 9.5 hours a day, from 20 November 2022, with pay and total hours unchanged; a Federal Planning Bureau and Ghent University study found one company fully participated in its reduced-working-time pilot; comparability none — this is compression, not a reduction, and is not evidence for 100-80-100
  - Portugal 2023–24 — 41 companies and more than 1,000 workers, coordinated six-month test from June 2023, with a control group of interested non-adopters; actual hours fell 12% from over 41 to 36.5 while the control group did not move; the report states that because no financial incentives were offered the participants are not representative and it serves only as a "Proof of Concept"; comparability high on design, moderate on sector
  - Germany 2024 — 45 organisations across consulting, services, manufacturing, care, IT and media, six months from 1 February 2024, within-organisation control groups and physiological instruments; many organisations reduced hours across five days rather than moving to four; comparability high on method, moderate on intervention
  - South Cambridgeshire District Council — 32 hours from 1 April 2024, 86.5% of contracted hours, pay maintained, independently evaluated; comparability low — public sector, statutory services
  - Recorded conflict 1 (both readings shown, neither resolved): Iceland as a transformative national success versus Iceland as a one-to-three-hour reduction whose national legacy is under an hour a week
  - Recorded conflict 2: South Cambridgeshire's own July 2025 communications report 21 of 24 services improved or stayed the same, leavers down over 40%, applications up over 120% and a yearly saving of nearly £400,000; the independent statistical evaluation reports 11 outcomes significantly better, 2 significantly worse — the percentage of housing rent collected and the average days to re-let housing stock — and the rest indistinguishable, and states the analysis alone cannot prove the trial caused any of the changes
- **Visualization**: `study-comparability` — comparison matrix, rows = the seven studies, columns = "What changed" · "Scale and period" · "Control group" · "Headline result" · "Comparability to this firm"; the comparability column is the only one carrying colour, encoding a declared three-level rating whose meaning is stated in the table's own key. Native-ready: `study-comparability=yes`
- **Fact IDs**: F001, F018, F022, F024, F028, F030, F031, F033, F034, F035, F036, F037, F039, F040, F046, F050, F052, F054, F056, F057, F058

### Part 4: The decision

#### Slide 07 - Recommendation: a six-month, redesign-first pilot in two practice groups

- **Audience move**: Holds a yes/no question → holds a specific, bounded, reversible proposal with named criteria, and knows what is deliberately not being proposed.
- **Relationships**: One recommended action with four design choices beneath it, each traced to a diagnosis on P03–P06; plus a contrast set — three alternatives explicitly not recommended, each with its reason.
- **Composition**: The action dominates the upper half at display scale with its rationale visibly adjacent; the "not recommended" contrast set sits beneath on the slate, deliberately subordinate.
- **Title**: Pilot 100-80-100 in two practice groups for six months, after ten weeks of redesign
- **Core message**: Commit to the trial and its kill criteria, not to the policy.
- **Content**:
  - The action: two whole practice groups, approximately 60 people (illustrative scope), on 100% pay, a universal day off, and a target 32-hour week; ten weeks of redesign first; six months of operation; one interim gate; contractual position unchanged for the duration
  - Design choice 1 — redesign before, not during: reversion tracks redesign effort, with 8% reverting after two or more organisational changes against 38% after none or one; the consistent preparation figure across the UK, Portuguese and six-country studies is two to three months
  - Design choice 2 — a universal day off, not a flexible model: universal or staggered models converted to permanence in 95% of cases against 60% for flexible ones, on a sample too small for significance
  - Design choice 3 — measure before you promise: half the Portuguese companies found it difficult to define productivity metrics at all and over a third struggled to change the internal culture around time management, so metrics are agreed in the redesign phase, not after
  - Design choice 4 — no entitlement: nearly half of the permanent cases in the UK follow-up never changed contracts, which is what makes the policy withdrawable; this pilot is explicitly stated as non-contractual
  - Kill criteria, agreed before the start and reviewed at the interim gate (Data class: scenario — these thresholds are the firm's to set and are illustrative here): client-satisfaction score, on-time delivery rate, realisation rate, utilisation, voluntary attrition
  - Not recommended, and why: a firm-wide permanent commitment — no evidence base at this scale or sector; a compressed four-day week — Belgium's model keeps total hours and is not 100-80-100; an hours reduction spread across five days — the German pilot shows this drifts away from the intervention being tested
- **Visualization**: the action stated as native geometry — one bounded six-month band with its ten-week redesign lead-in; no keyed data object
- **Fact IDs**: F002, F025, F029, F035, F045, F047, F048, F052, F063, F064
- **Motion suggestion**: the action line settles, then the four design choices in order, then the not-recommended set; the six-month band is the object that continues onto the roadmap

#### Slide 08 - Roadmap: ten weeks of redesign, six months of operation, two gates

- **Audience move**: Accepts the recommendation in principle → can see who does what, when the firm can stop, and what each gate decides.
- **Relationships**: Five sequenced phases with two decision gates; order and dependency, with the redesign phase as a hard precondition of the pilot phase.
- **Composition**: A single horizontal progression across the full measure, phases as bands and gates as marks on the sequence; ownership and the gate question sit under each phase rather than in a separate legend.
- **Title**: Two gates, and the firm can stop at either one
- **Core message**: The pilot is reversible by design, and the points of reversal are fixed before it starts.
- **Content**:
  - Phase 0 — Redesign, weeks 1–10 (COO): meeting and admin reduction as the primary lever, following the pilots' own most-common changes; agree the metric set; agree the client communication plan, following Portugal's eight preparation sessions over three months covering format choice, communication with workers and with clients, evaluation metrics and process change
  - Phase 1 — Operate, months 1–6 (practice heads): two practice groups, universal day off, contractual position unchanged
  - Gate A — month 3 (executive committee): are the kill criteria holding? The Portuguese report found most indicators slipped slightly between three and six months, which its authors could not fully explain, so a month-3 read is expected to be the high-water mark, not the trend
  - Phase 2 — Evaluate, month 7 (finance director with an independent reader): compare against the non-participating practice groups as a control, the design Portugal used and the UK 2022 pilot lacked
  - Gate B — month 8 (executive committee): extend, adjust, or stop; a decision to extend is a decision to re-open contracts
  - Ownership and dates are illustrative (Data class: scenario)
- **Visualization**: qualitative sequence — five phase bands and two gate marks with dependency connectors; drawn with preset shapes and connectors, no keyed data object
- **Fact IDs**: F021, F040, F043, F048, F050

#### Slide 09 - Risk and mitigation: what would stop this, and who owns it

- **Audience move**: Sees the risks as generic change-management risk → sees six specific documented risks, each with the evidence that it is real and a named owner.
- **Relationships**: Six risks positioned by likelihood against impact, each paired one-to-one with a mitigation and an owner; correspondence, plus one contrast — the highest-impact risk is the one the firm does not control.
- **Composition**: Risk and response in direct visual correspondence — a likelihood-by-impact field in the upper region with the six risks placed on it, and the register directly beneath so each row reads across from its position.
- **Title**: The risk that stopped the only comparable firm is the one we cannot mitigate away
- **Core message**: Client expectation is the binding risk; everything else is a preparation problem.
- **Content**:
  - Risk 1 — client and stakeholder expectations (high likelihood, high impact; owner: practice heads): the UK cohort's only twelve-month discontinuation was a consultancy that stopped on exactly this, and Belgium's pilot uptake failed partly on sectoral expectation. Mitigation: client communication agreed in Phase 0; no reduction in stated response times; cover rotas published to clients
  - Risk 2 — hours creep, where a nominal 32-hour week becomes 34–36 worked (high, medium; owner: COO): observed in the UK pilot at 38 → 34 hours with 15% working more, and in Portugal at 36.5. Mitigation: measure actual hours, not the policy; treat creep as a kill-criterion input
  - Risk 3 — no agreed definition of productivity (medium, high; owner: finance director): half the Portuguese companies found it difficult to define productivity metrics at all. Mitigation: metrics fixed in Phase 0 and published before the pilot starts
  - Risk 4 — benefit fade after month 3 (medium, medium; owner: HR director): most Portuguese indicators slipped between three and six months for reasons the authors could not fully explain. Mitigation: Gate A treated as the high-water mark; six-month read is the decision read
  - Risk 5 — entitlement dispute on withdrawal (medium, medium; owner: HR director): in the UK follow-up, 39% of permanent cases never changed contracts, which makes the policy withdrawable and therefore disputable. Mitigation: non-contractual status stated in writing at the start and acknowledged by each participant
  - Risk 6 — inequitable application across a small team (medium, medium; owner: practice heads): the discontinuing consultancy cited exactly this alongside client expectations. Mitigation: whole-practice-group scope rather than individual opt-in
  - Assumption (labelled as such): likelihood and impact ratings are the firm's judgement, not findings — Data class: scenario. The evidence column is sourced; the rating column is not
  - External note: a Best Value Notice was issued to South Cambridgeshire District Council in November 2023, reissued in May 2024 and allowed to expire in November 2024, alongside a statement that it is not government policy to support a general move to a four-day week for five days' pay — relevant to a private firm only as a signal about external legitimacy, not as a constraint
- **Visualization**: `risk-register` — record table, one row per risk with columns Risk · Likelihood · Impact · Evidence that it is real · Mitigation · Owner; likelihood and impact use one declared ordinal scale, and the accent marks only the single binding risk. A likelihood-by-impact field above it positions the same six risks as native geometry. Native-ready: `risk-register=yes`
- **Fact IDs**: F011, F025, F028, F037, F040, F043, F047, F059

### Part 5: The trace

#### Slide 10 - Appendix: every figure in this memo, and where it comes from

- **Audience move**: Has read an argument → can audit it, follow any figure to its primary source, and see what this memo deliberately did not claim.
- **Relationships**: A source ledger grouped by study, each entry linked to the pages that use it; membership and link, plus a separate set of standing limitations that apply across all of them.
- **Closing impact**: The binding takeaway is that nothing in this memo has to be taken on trust — every number is one click from its primary report, and the two places where credible sources disagree are named rather than reconciled. Composition Reference: a dense two-column ledger of live source links under a short standing-limitations block; this is the page that sets the running body text in two equal columns.
- **Composition**: Dense appendix. Two equal columns of source entries under a full-measure limitations block; higher density than any other page, with the claim-to-source path still legible.
- **Title**: Every figure above is one link from its primary source
- **Core message**: The argument is auditable; where the sources disagree, this memo shows both.
- **Content**:
  - Source ledger, each entry a live hyperlink with its publisher, period and the pages that use it: the UK 2022 pilot report; the twelve-month follow-up; the Iceland report and Veal's critique; the Belgian Labour Deal provisions and the Federal Planning Bureau study; the Portuguese final report of July 2024; the German pilot results; the South Cambridgeshire independent evaluation and the council's own communications; the peer-reviewed six-country study; the ONS hours and productivity series; the Oxford Economics replacement-cost study; the 4 Day Week Global definition; the named company accounts (Awin, Atom Bank) and the two North American law firms
  - Standing limitations that apply to every study above: management self-selects participation; company financial data is self-reported; control arms are absent, small or non-random; follow-up samples shrink
  - Definitions: 100-80-100 as defined by 4 Day Week Global; "continuation" as still operating the policy, which is not the same as a contractual entitlement; "not statistically significant" as stated by the reporting authors
  - Deliberately not claimed: any figure for this firm; any productivity forecast; any saving derived from the 2014 replacement-cost figure as anything other than illustrative arithmetic
  - Named company accounts are self-published and labelled as such: Awin reports regrettable turnover down 33% and sick leave down 21%; Atom Bank reports applications up 49% year on year; neither is an independent evaluation
- **Visualization**: no keyed data object; a dense two-column source ledger set as native text with hyperlink carriers
- **Fact IDs**: F010, F019, F024, F033, F046, F056, F058, F062, F063, F064, F065, F066, F067, F070

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: One note per page, written for a reader who must defend the page in the room rather than present it. Each note states the page's governing question, the provenance and period of every figure on the page, the single most likely challenge to it and the honest answer, and what the page deliberately does not claim. Notes never introduce a figure that is not on the page and never soften a caveat the page states. Facts are grounded in the imported research pair and cited by fact id.
- **Total duration**: not time-bound — this is a reader-led print memo with no presented duration; notes are sized to one screen per page (roughly 120–180 words)
- **Notes style**: formal, defensive, evidence-first
- **Presentation purpose**: Put a go/no-go decision in front of the committee — establish what the evidence supports and where it is weak, set out the options and trade-offs, and ask for a decision on a bounded pilot.

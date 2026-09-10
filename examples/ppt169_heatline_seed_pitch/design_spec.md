<!-- ppt-master-schema: design-spec/v1 -->
# Heatline Seed Pitch - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | Heatline Seed Pitch |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 15 |
| Primary Language | en-GB |
| Target Audience | Seed-stage investors at climate-tech and vertical-software funds — partners and associates who follow energy-transition headlines but have never seen inside an installer business |
| Communication Intent | Persuade first, then obtain a decision: establish that installer capacity, not consumer demand, is the binding constraint on residential heat-pump deployment; show that Heatline sells the planning layer that lifts it; and secure a seed round on the stated terms. Leave a diligence trail that survives the meeting. |
| Desired Audience Outcome | Investors can restate the capacity bottleneck in their own words, can tell achieved from contracted from projected in every Heatline number, and can take a first-meeting decision on the ask |
| Core Message / Ask / Action | Electrifying home heating is now limited by installer capacity, not demand. Heatline sells the capacity-planning layer that lets an installer business grow crews and throughput, and is raising a £4.2M seed round to reach that market while European policy guarantees the demand floor. |
| Delivery Context | Primary: presenter-led 15-minute seed pitch to an investment committee. Secondary: reader-led circulation inside the fund afterwards, so every page must carry its own claim without a presenter. |
| Artifact Afterlife | Diligence hand-off and internal circulation; the appendix, metric definitions and source links must survive forwarding |
| Content Strategy | Free re-architecture of the researched material into a pitch narrative. Every externally verifiable number stays sourced to `sources/heatline_pitch_research.facts.json`; every company, product, customer, traction, pipeline and financial figure is fictional and carries a visible illustrative marker on the page, not only in the notes. |
| Design Style | Field Notes — warm, high-contrast editorial page architecture with a schematic annotation layer; one ember accent reserved for evidence |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — final Stage-2 proactive policy |
| Custom Animations | enabled — final Stage-2 proactive policy (continuity-aware solution: the capacity curve and the ask are planned as visible states across adjacent pages) |
| Narration Audio | disabled — final Stage-2 proactive policy |
| Created Date | 2026-09-10 |

- **Template Application**: Adopt the investor-pitch Style as communication method and expression discipline only. Its thirteen page roles set the deck's spine in the order given, one role per page, with use of funds split onto its own page beside the ask so the ask page stays unmistakable. Its claim discipline binds: page titles are written as claims, each metric carries its definition where it first appears, achieved / contracted / pipeline / projected stay distinguishable by texture as well as colour, market size is derived bottom-up in view, and competition is compared on axes that decide purchases without naming a vendor as inferior. Its evidence obligations bind: source and date sit on the page that carries a third-party figure, and traction, unit-economics, market and financial-plan objects are authored as editable native charts and tables. Its visual defaults are candidates, not identity: the preferred dark-tech field and corporate-photo rendering are replaced by the warm editorial system recorded in §III, for the reason recorded there, while its density rule (sparse in the arc, dense only in the appendix), its restrained-decoration rule and its rare-accent rule are adopted unchanged. No prototypes, canvas or structure come from this Style; pages stay flat free design.

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
- **Mode References**: narrative, pyramid
- **Mode Behavior**: Run the investor-pitch arc as a story with one turn — the world changed, the change created a bottleneck nobody is staffed for, here is the tool that lifts it, here is the evidence it works, here is what the money buys. Inside that arc every page states its conclusion in the title as a claim and puts its evidence directly beneath, so a forwarded page argues on its own. The turn sits at the problem→solution pair and is carried by one continuing object rather than a new frame. Appendix pages drop the arc and become retrieval surfaces.
- **Visual style**: custom
- **Visual Style References**: editorial, blueprint
- **Visual Style Behavior**: A warm paper field organised by an editorial column grid and heavy horizontal hairline rules: a rule under the claim line at a fixed height on every page, a second rule closing the evidence block, and no card unless a real container is needed. Type does the work — a large statement scale for claims and hero numbers, a quiet monospace for measurements, definitions and attribution. The blueprint contribution is an annotation layer, not a field: leader lines, tick marks, dimension ticks and monospace callouts label the product mockup, the capacity curve and the market derivation, so the deck reads as engineering field notes rather than marketing. Decoration is otherwise near zero — no gradient meshes, glow, floating devices or ornamental infographics; the ember accent appears at most twice per page and only on evidence.
- **Theme**: Engineering field notes on warm paper — a hardware business argued with measurements
- **Tone**: Confident, plain-spoken, unhurried; specific where it matters and explicitly uncertain where it is

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FBF7F1 | Warm paper field; the deck's dominant surface |
| Secondary background | #EFE7DA | Recessed evidence blocks, appendix bands, table header rows |
| Primary | #16233A | Claim lines, hero numerals, rules, chart structure |
| Accent | #D65A1E | Reserved for evidence — the decisive figure, the actual series, the ask |
| Secondary accent | #2E6F5E | Achieved / verified state where it must differ from projected |
| Body text | #1F2733 | Body copy and table cells |
| Secondary text | #6B6154 | Captions, definitions, source lines, illustrative markers |
| Divider | #C9BCA8 | Hairline rules, grid lines, table borders |

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: corporate-photo, editorial
- **Image Rendering Behavior**: Real editorial photography of ordinary working situations, shot in warm low-angle daylight with a shallow but honest depth of field; no studio gloss, no anonymous stock professionals, no abstract technology. The editorial contribution is framing and restraint — a single clear subject with usable quiet space on one side for type, natural colour that sits inside the deck's warm paper and deep-ink range, visible material texture in metal, brick and workwear, and no synthetic text, screens or interface anywhere in the frame.
- **Visual**: Working installers and real domestic hardware, photographed close and plainly, with one quiet region reserved for the page's claim line
- **Mood**: Early-morning trade work — the register of a good newspaper business-section photograph rather than a manufacturer brochure

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | Display grotesque / maximum weight, built for claim lines and hero numerals | Arial Black | — | sans-serif |
| Body | Humanist sans / warm, high x-height, legible on a laptop | Calibri | — | sans-serif |
| Data | Monospace / tabular figures for aligned metrics, measurements and definitions | Consolas | — | monospace |
| Display | Display grotesque / hero numerals at statement scale, sharing the Title character | Arial Black | — | sans-serif |

- **Title stack**: `Arial Black, sans-serif`
- **Body stack**: `Calibri, sans-serif`
- **Data stack**: `Consolas, monospace`
- **Display stack**: `Arial Black, sans-serif`
- **Role rationale**: `Display` shares the Title family rather than inheriting the body family, because every hero number on the why-now, ask and metric pages must carry the same grotesque weight as the claim lines. `Data` is a genuine third family — every metric table, chart annotation, unit-economics figure, definition line and illustrative marker in this deck aligns in columns and needs tabular figures, which neither Arial Black nor Calibri supplies; it also carries the blueprint annotation layer named in §III.

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 42 |
| Subtitle | 32 |
| Annotation | 18 |
| Display | 108 |
| Lead | 30 |
| Data | 20 |
| Footnote | 16 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: Claim line first at a fixed height, then the single dominant evidence object, then the quiet layer — definition, source, illustrative marker — along the bottom rule
- **Composition tendency**: One claim and one dominant element per page on a warm field; evidence blocks recessed rather than boxed; the annotation layer labels the object instead of a legend floating beside it
- **Cross-page continuity**: The claim line's fixed height and the rule beneath it recur on every page; the capacity curve is one continuing object across the problem and solution pages; the ask figure's segments become the use-of-funds bars on the following page; the ember accent recurs only where evidence sits
- **Spacing posture**: Open through the narrative arc, deliberately dense only on the competition matrix and the diligence appendix
- **Spacing anchors**: page margin 64 px, block gap 32 px, column gutter 32 px, corner radius 4 px, body leading 34 px

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| tabler-outline/tools | Installer work, field crew, service capability |
| tabler-outline/home | Residential property, the installed base |
| tabler-outline/calendar | Scheduling horizon, booking window |
| tabler-outline/users | Crew size, headcount, team |
| tabler-outline/trending-up | Growth, rising demand, expansion |
| tabler-outline/building-factory | Manufacturer channel, industry partners |
| tabler-outline/certificate | Accreditation, training, qualification |
| tabler-outline/clock | Lead time, payback period, delay |
| tabler-outline/route | Go-to-market motion, sequence of channels |
| tabler-outline/target | Milestone, target penetration, objective |
| tabler-outline/alert-triangle | Risk, exposure, constraint |
| tabler-outline/coin | Price, revenue, cost, funding |
| tabler-outline/chart-line | Metric, measured series, reporting |
| tabler-outline/file-text | Contract, document, compliance record |
| tabler-outline/flame | Heating, fossil boiler, the thing being replaced |
| tabler-outline/bolt | Electrification, the heat pump itself |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P02 | chart | column_chart | Compare EU annual heat-pump installations across 2022–2025 to show the fall and the return |
| P06 | chart | line_chart | Show the full available history of live engineer seats month by month |
| P07 | chart | waterfall_chart | Trace gross contract value down to gross contribution per customer per year |
| P08 | table | record_table | Hold each derivation stage with its seats, its arithmetic and whether it is real or illustrative |
| P09 | table | comparison_matrix | Compare the three real alternatives against the criteria that decide a purchase |
| P10 | chart | column_chart | Compare customers acquired by each go-to-market channel, including the untested one |
| P12 | chart | stacked_bar_chart | Show revenue composition by named driver across the plan, actual and projected |
| P14 | table | record_table | Itemise the use of funds with amount, share, what it buys and the milestone it reaches |
| P15 | table | metric_table | Hold each metric's definition, measurement period and system of record for diligence |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_installation_dawn.jpg | 1920×1072 | 16:9 | Cover hero: ground the deck in the physical work before any claim | Photo | Full-bleed field carrying the cover; the subject sits right of centre so the left third stays quiet under a real scrim for the title lockup | adaptive | ai | Generated | An installer in workwear kneeling beside a newly fitted outdoor air-source heat-pump unit on a gravel pad against a brick house wall, early-morning light raking across the fins, breath visible in cold air; quiet sky and wall on the left third; no text, no screens, no logos | none | hero_page |
| problem_capacity_yard.jpg | 1024×1024 | 1:1 | Problem page: make the capacity shortage a specific situation rather than a category | Photo | Editorial crop occupying the page's right column beside the capacity curve; subject faces back into the page | adaptive | ai | Generated | Two installers loading a van at a depot before dawn, a third checking a clipboard, a rack of unfitted heat-pump units waiting behind them; the emphasis is on the small crew against the size of the stock, warm sodium and daylight mixed; no text, no screens, no logos | none | local |
| solution_survey_handover.jpg | 1200×896 | 4:3 | Solution page: show the human moment the software coordinates | Photo | Supporting image below the claim line, cropped tight so the two hands and the document dominate; sits opposite the continuing curve | adaptive | ai | Generated | Close crop of an installer and a homeowner at a kitchen doorway handing over a survey sheet, radiator and pipework visible behind, warm interior daylight; hands and paper dominate the frame, faces partly out of frame; no readable text, no screens, no logos | none | local |

## IX. Content Outline

### Part 1: The shift and the bottleneck

#### Slide 01 - Cover

- **Audience move**: Expecting another climate-software deck → primed that this is about the physical trade, and warned in advance that every company figure is illustrative
- **Relationships**: none
- **Cover impact**: The hook is the reversal — the demand for home electrification is now legislated, and the thing that is short is people. Composition is a Reference: full-bleed photograph with a real scrim on the left third, title lockup and the deck-wide illustrative notice on the bottom rule.
- **Composition**: Full-bleed image field; title lockup in the quiet left third over a scrim; a single hairline rule at the fixed claim height carries the round and date on the right.
- **Title**: Europe has legislated the demand. Nobody has staffed the supply.
- **Core message**: Heatline sells capacity planning to residential heat-pump installers, and is raising a seed round.
- **Content**:
  - Company line: Heatline · capacity planning and job scheduling for residential heat-pump installers
  - Round line: Seed · £4.2M · September 2026
  - Deck-wide illustrative notice: Heatline is a fictional company. All company, product, customer, traction and financial figures in this deck are illustrative. External figures are sourced and cited on the page where they appear.
- **Images**: `cover_installation_dawn.jpg` as the field; the scrim is real, not a fade, so the claim line stays legible on a laptop.
- **Motion suggestion**: The claim line and the round line arrive first; the illustrative notice settles last. The photograph does not move.
- **Data class: scenario** — the round size, the date and the company itself are invented.
- **page_rhythm**: anchor

#### Slide 02 - Why now

- **Audience move**: Believes heat pumps are a slow, subsidy-dependent story → sees a market that fell hard, turned in 2025, and now has a legislated floor under it
- **Relationships**: order (2022 → 2023 → 2024 → 2025 annual installations); contrast (the 2024 collapse against the 2025 return); link (the EPBD fossil-boiler rules to the floor under future demand)
- **Composition**: Hero figure top-left carrying the turn, the native column chart occupying the lower two-thirds full width, policy line as a quiet band along the bottom rule with its sources.
- **Title**: The market fell 21%, then turned — and the exit is now written into law
- **Core message**: 2025 is the inflection: Europe grew again for the first time since 2022, and the fossil-boiler alternative is being legislated out to 2040.
- **Content**:
  - Hero figure: +11% — European heat-pump sales in 2025, the first growth since 2022
  - Chart block: EU annual installations 2.8m (2022) · 2.7m (2023) · 2.11m (2024) · 2.34m (2025, preliminary, 13 Member States)
  - Turn line: 2024 was the largest decline ever recorded in Europe, −21%; Germany fell almost 50%. 2025 reversed it, led by Germany at +55% in the first half, and was the first year heat pumps outsold gas boilers in Europe.
  - Floor line: EPBD Article 17(15) ends financial incentives for new stand-alone fossil boilers from 1 January 2025; national plans must aim at complete phase-out by 2040.
  - Source line: IEA Global Energy Review 2025 and 2026 · European Commission, Energy · retrieved 2026-09-10
- **Visualization**: `eu-annual-installations` — native column chart, four annual values in millions of units, y-axis from zero, axis title "EU installations (million units)", data labels at one decimal. `Native-ready`: eu-annual-installations=yes
- **Fact IDs**: F002, F003, F005, F006, F007, F008, F013, F014, F021
- **Motion suggestion**: The hero figure arrives, then the columns rise in year order so the fall and the return are read as a sequence; the policy band settles last.
- **page_rhythm**: dense

#### Slide 03 - Problem

- **Audience move**: Assumes the constraint is consumer demand or subsidy → understands that the binding constraint is installer headcount, and that installers say so themselves
- **Relationships**: contrast (installers needed against installers available); link (the workforce gap to the throughput ceiling each firm hits); membership (the firms with six or more staff as the segment where staffing is the top barrier)
- **Composition**: Left two-thirds carries the capacity curve — demand rising, capacity nearly flat, the gap between them shaded and labelled; the right column carries the depot photograph; the survey evidence sits on the bottom rule.
- **Title**: The bottleneck is people: Europe needs 750,000 more installers
- **Core message**: Demand is being legislated upward while the installer workforce grows slowly, and the firms that already have work say staffing — not demand — is what stops them doing more.
- **Content**:
  - Hero figure: 750,000 — additional installers the European Commission estimates are needed; at least 50% of existing installers must be reskilled
  - Curve block: a schematic capacity gap — required installation capacity rising against installer headcount rising slowly, the widening area between them labelled "the gap"
  - Scale line: around 117,000 people worked in the European heat-pump industry, about 37% of them in manufacturing; EHPA puts the need at a minimum 500,000 skilled full-time-equivalent employees by 2030, against 7 million installations a year up from about 2 million in 2021
  - UK ratio: about 3,000 heat-pump engineers against at least 27,000 needed by 2028 and 62,000 by 2035 — 5,000 to 7,000 trained every year for a decade
  - Installer evidence: in a survey of 345 UK installers, 30% named finding suitable additional staff as the biggest barrier to doing more installations, rising to 41% among firms with six or more staff; 81% of those firms expected to hire within twelve months
  - Honest reading: across the whole trade, lack of customer demand was cited more often (41%). Staffing is the binding constraint for the firms that already have work — which is exactly the segment we sell to.
  - Source line: European Commission · EHPA · Nesta · retrieved 2026-09-10
- **Visualization**: `capacity-gap-schematic` — a hand-authored schematic of two diverging lines with the gap shaded and annotated; it is an illustration of a relationship, not a measured series, and is deliberately not a data chart. `Native-ready`: capacity-gap-schematic=no
- **Images**: `problem_capacity_yard.jpg` in the right column, cropped so the waiting stock reads as larger than the crew.
- **Motion suggestion**: The demand line draws first, the capacity line second, the gap fills last; the gap is the object that continues onto the next page.
- **Fact IDs**: F020, F022, F023, F024, F027, F028, F029, F030, F031, F032
- **page_rhythm**: dense

### Part 2: What we built and what it does

#### Slide 04 - Solution

- **Audience move**: Understands the gap → understands that the lever is throughput per engineer, and that Heatline is a planning layer rather than another dispatch tool
- **Relationships**: link (the gap on the previous page to the throughput lever); order (survey → install → commission as the chain being planned); contrast (planning months ahead against dispatching on the day)
- **Composition**: The capacity curve arrives from the previous page and bends upward under the claim; the three-part mechanism sits beneath it as a labelled sequence with connectors; the handover photograph balances the right side.
- **Title**: You cannot hire your way out in one season — so raise throughput per engineer
- **Core message**: Heatline plans crew capacity months ahead against accreditation, survey backlog and commissioning windows, so an installer business books more work with the engineers it already has.
- **Content**:
  - Mechanism, three parts: forecast capacity by crew and accreditation months ahead · sequence the survey → install → commission chain against part lead times · hold the grant and compliance paperwork on the same job record
  - Lever line: the curve bends because each engineer completes more jobs, not because more engineers appear
  - Boundary line: Heatline does not train engineers and does not sell equipment; it plans the capacity a business already has and the capacity it is about to add
  - Illustrative marker: product capability described here is illustrative
- **Visualization**: `capacity-gap-schematic-resolved` — the same two-line schematic as P03 with the capacity line bending upward and the gap narrowing; the continuation is the point. `Native-ready`: capacity-gap-schematic-resolved=no
- **Images**: `solution_survey_handover.jpg` supporting the mechanism block.
- **Motion suggestion**: The curve is the same object as the previous page and should be seen to bend rather than to reappear; the three mechanism parts arrive in chain order afterwards.
- **Data class: scenario** — the product and its capabilities are invented.
- **page_rhythm**: breathing

#### Slide 05 - Product evidence

- **Audience move**: Has heard the mechanism described → has seen the actual planning surface and can judge that it exists
- **Relationships**: parent (the capacity planner containing the crew rows); order (weeks along the horizontal axis); membership (each engineer belonging to a crew and to an accreditation class); overlap (a booked job overlapping its part lead time)
- **Composition**: Full-frame product surface with minimal chrome, drawn as native SVG — a left rail of crews, a horizontal schedule grid of weeks, capacity bars, an accreditation column, and one leader-line callout per feature that carries the claim.
- **Title**: This is the planning surface: twelve weeks of crew capacity on one screen
- **Core message**: The capacity planner is a real, working surface — crews down the side, weeks across the top, committed and available capacity visible together.
- **Content**:
  - Surface blocks: crew rail with engineer counts · twelve-week horizontal grid · committed capacity bars against available capacity · accreditation column marking who may commission which unit class · a flagged part-lead-time conflict
  - Callouts, three: "committed vs available on the same bar" · "accreditation limits who can close a job" · "a lead-time conflict surfaces before the booking is confirmed"
  - Disclosure line: illustrative mockup drawn to scale from the product specification; data shown is illustrative
- **Motion suggestion**: The grid frame stays; the capacity bars fill left to right; the conflict flag arrives last so it reads as the punchline.
- **Data class: scenario** — every crew name, number and booking on the surface is invented.
- **page_rhythm**: dense

### Part 3: Evidence that it is working

#### Slide 06 - Traction

- **Audience move**: Accepts that the product exists → sees a measured growth curve with its definitions and can judge the shape rather than a headline
- **Relationships**: order (months from January 2025 to August 2026); link (the September 2025 inflection to its named cause)
- **Composition**: The curve dominates the page full width; the metric definition sits directly under the axis title; the inflection is marked in place with its cause; the cohort basis runs along the bottom rule.
- **Title**: 430 engineer seats live across 41 installer businesses
- **Core message**: Seats have grown every month since launch, with the inflection in September 2025 when the first manufacturer training partner began referring its accredited installers.
- **Content**:
  - Chart block: live engineer seats, monthly, January 2025 to August 2026, full history, unbroken axis from zero
  - Metric definition: a live engineer seat is one engineer with an active licence on the last day of the month; seats are counted per engineer, not per business
  - Cohort basis: all customers since launch; no cohort excluded; no month restated
  - Companion figures: 41 installer businesses · £0.93M ARR at 31 August 2026 · net revenue retention 118% over the trailing twelve months · logo churn 4% annualised
  - Inflection note: September 2025 — first manufacturer training partner begins referring accredited installers
  - Illustrative marker: all Heatline traction figures are illustrative
- **Visualization**: `live-engineer-seats` — native line chart, twenty monthly points, y-axis from zero titled "Live engineer seats", x-axis titled "Month", value labels on the first, inflection and last points only. `Native-ready`: live-engineer-seats=yes
- **Motion suggestion**: The axis frame stays; the line draws in time order; the inflection marker and its cause arrive after the line passes it.
- **Data class: scenario** — every seat count, revenue, retention and churn figure on this page is invented.
- **page_rhythm**: dense

#### Slide 07 - Business model

- **Audience move**: Has seen growth → can see the arithmetic that turns a seat into contribution, and the payback period that follows from it
- **Relationships**: order (gross contract value through each deduction to gross contribution); link (gross contribution to the payback period); parent (the annual contract value containing its deductions)
- **Composition**: The waterfall carries the page centre; the assumption strip sits beneath it in the monospace data role; the payback figure sits to the right as the one accented number.
- **Title**: £180 per engineer per month pays back acquisition in 5.2 months
- **Core message**: A ten-seat installer business produces £14,870 of annual gross contribution against £6,400 of acquisition cost, so the payback is under half a year and expansion is the cheap growth.
- **Content**:
  - Pricing line: £180 per engineer per month, annual term, minimum five seats
  - Waterfall block: gross contract value £21,600 · launch discount −£3,240 · hosting and support −£2,570 · payment and partner fees −£920 · gross contribution £14,870
  - Basis line: one representative ten-seat customer, twelve months, GBP, unaudited
  - Payback figure: 5.2 months, from £6,400 blended customer acquisition cost against £1,239 monthly gross contribution
  - Comparator line: published list pricing for small-trade field-service software runs from $49 per month for a single user to $499 per month for five, with additional users at $29 — a per-seat market, and the reference point our pricing sits against
  - Illustrative marker: Heatline pricing, costs and acquisition cost are illustrative; the comparator is published list pricing
  - Source line: Jobber published pricing · retrieved 2026-09-10
- **Visualization**: `unit-economics-waterfall` — native waterfall chart, one starting value, three negative contributions, one ending total, currency labels with no decimals. `Native-ready`: unit-economics-waterfall=yes
- **Fact IDs**: F033
- **page_rhythm**: dense

#### Slide 08 - Market opportunity

- **Audience move**: Wonders whether the market is large enough → can follow every step from a public workforce figure down to a reachable revenue number, and can attack any one of them
- **Relationships**: order (each derivation stage narrowing the one above); parent (European installer seats containing the launch markets, containing the reachable firms); link (reachable seats to revenue through the published price)
- **Composition**: The funnel runs down the left two-thirds with each stage labelled by its own arithmetic in the monospace role; the resulting revenue figure sits alone on the right; assumptions are listed under the bottom rule, each marked real or illustrative.
- **Title**: 5,500 reachable seats is £11.9M of ARR — here is every step
- **Core message**: The market is derived bottom-up from the European Commission's own workforce estimate and our published price, and each assumption is stated so it can be argued with.
- **Content**:
  - Stage 1 — European installer seats at full build-out, 824,000: about 74,000 today (117,000 industry employees less the 37% in manufacturing) plus the 750,000 additional installers the European Commission estimates are needed
  - Stage 2 — our four launch markets, 118,000 seats: UK, Ireland, Germany and the Netherlands at their share of European installation volume
  - Stage 3 — reachable firms today, 46,000 seats: businesses with six or more engineers, the segment that reports staffing as its binding constraint
  - Stage 4 — target penetration by 2031, 5,500 seats: 12% of the reachable base
  - Revenue line: 5,500 seats × £180 × 12 = £11.9M ARR
  - Assumption marks: stages 1 real and derived from cited sources; stages 2 to 4 illustrative
  - Source line: European Commission · EHPA · Nesta · retrieved 2026-09-10
- **Visualization**: `market-derivation` — native table, four derivation stages by three fields (seats, how it is derived, real or illustrative). A funnel was rejected during authoring: the stages span a 150-fold range, so the last two bars would be invisible and ChartEx funnels accept no data labels. `Native-ready`: market-derivation=yes
- **Mathematical content**: 5{,}500 \times 180 \times 12 = 11{,}880{,}000
- **Fact IDs**: F020, F021, F023, F030
- **Motion suggestion**: Stages arrive top to bottom in derivation order so the narrowing is read as reasoning; the revenue figure lands last.
- **Data class: scenario** — stages 2, 3 and 4, the penetration rate and the resulting revenue are invented; stage 1 is derived from cited sources.
- **page_rhythm**: dense

#### Slide 09 - Competition

- **Audience move**: Assumes generic field-service software already covers this → sees where each real alternative genuinely wins and what none of them plans
- **Relationships**: contrast (three alternatives across five purchase criteria); overlap (day-of dispatch, where generic tools and Heatline both operate)
- **Composition**: A full-width comparison matrix, criteria down the left in purchase order, three alternatives across; the honest-win row is not hidden; the closing line sits under the bottom rule.
- **Title**: Spreadsheets are free and flexible; field-service tools dispatch well; neither plans capacity
- **Core message**: The real alternatives win on cost, flexibility and day-of dispatch maturity — and none of them models the accreditation-constrained capacity of a crew months ahead.
- **Content**:
  - Alternatives: shared spreadsheets and calendars · generic field-service software · Heatline
  - Criteria: plans crew capacity months ahead · models engineer accreditation and training state · sequences survey → install → commission against part lead times · holds grant and compliance paperwork on the job record · published price per engineer per month
  - Honest wins: spreadsheets — free, instantly flexible, no implementation; field-service software — mature day-of dispatch, invoicing and payments, large integration ecosystems
  - Price row: spreadsheets £0 · generic field-service software from $49/month for one user to $499/month for five, additional users $29 · Heatline £180 per engineer per month
  - Closing line: we are not claiming these tools are bad. We are claiming none of them answers the question an installer business asks in January about August.
  - Illustrative marker: Heatline capability and price are illustrative; competitor pricing is published list pricing and no vendor is named
  - Source line: Jobber published pricing · retrieved 2026-09-10
- **Visualization**: `competition-matrix` — native table, five criteria rows by three alternative columns plus a criteria header column, cells carrying short factual states rather than ticks alone. `Native-ready`: competition-matrix=yes
- **Fact IDs**: F033
- **page_rhythm**: dense

### Part 4: How it scales, who builds it, what it costs

#### Slide 10 - Go-to-market

- **Audience move**: Has seen one inflection → understands which motion produced it and in what order the next two arrive
- **Relationships**: order (three channels sequenced by year); link (the manufacturer channel to the September 2025 inflection on the traction page); contrast (direct outbound economics against channel economics)
- **Composition**: A horizontal timeline across the page centre built from preset shapes and connectors, one channel per station with its evidence beneath; the repeatable motion is visually primary and the untested channel is visibly lighter.
- **Title**: The manufacturer channel is the repeatable motion — direct sales proved it first
- **Core message**: Direct sales to firms with six or more engineers proved the product; manufacturer training academies made acquisition repeatable; trade-body accreditation partners are next and are not yet proven.
- **Content**:
  - Channel 1, direct — 2025: firms with six or more engineers; 9-week median sales cycle; blended acquisition cost £6,400; proved the product and produced the first 24 customers
  - Channel 2, manufacturer academies — 2025 onward: partners refer newly accredited installers at the moment they need planning; acquisition cost £2,900; produced the September 2025 inflection and 17 customers since
  - Channel 3, trade-body accreditation partners — 2027: planned, not yet tested; no acquisition cost claimed
  - Segment basis: 81% of surveyed firms with six or more staff expected to hire within twelve months — the moment planning capacity stops being optional
  - Illustrative marker: all channel counts, cycle times and acquisition costs are illustrative
  - Source line: Nesta installer survey · retrieved 2026-09-10
- **Visualization**: `channel-customers` — native column chart, three channels by customers acquired, y-axis from zero titled "Customers acquired", value labels on each column. `Native-ready`: channel-customers=yes
- **Fact IDs**: F031
- **Motion suggestion**: The timeline rail and its stations stay; each channel's evidence arrives in year order, and the untested third channel arrives visibly last.
- **Data class: scenario** — every customer count, cycle time and acquisition cost is invented.
- **page_rhythm**: dense

#### Slide 11 - Team

- **Audience move**: Has judged the business → understands why these three people specifically can build it, from operating history rather than titles
- **Relationships**: membership (three founders and one advisor forming the team); link (each person's prior work to the specific part of the problem they own)
- **Composition**: Three people at real prominence across the page, portraits drawn as native geometric monograms rather than photographs, each with one line of earned history and the part of the problem they own; the advisor sits smaller under the bottom rule.
- **Title**: The rota that became this product was run by hand for nine years
- **Core message**: The team is one operator who lived the scheduling problem, one scheduling engineer who has solved it at scale elsewhere, and one trainer who knows the accreditation system that constrains it.
- **Content**:
  - Maya Oduya, CEO — nine years operating a 40-engineer heating contractor; built and ran by hand the crew rota that became Heatline's first prototype; owns the customer definition of capacity
  - Tom Brenner, CTO — eleven years building constraint-solver scheduling for logistics fleets; owns the planner and the solver
  - Priya Raman, Head of Customer — trained more than 400 engineers on heat-pump commissioning at a national training provider; owns accreditation modelling and onboarding
  - Advisor: a former operations director of a national installer network, unnamed here pending permission
  - Illustrative marker: Heatline's team is fictional; no real person is depicted or named
- **Motion suggestion**: The three monograms hold their frame; each history line arrives in turn beneath its portrait.
- **Data class: scenario** — every person, history and role on this page is invented.
- **page_rhythm**: breathing

#### Slide 12 - Financials and plan

- **Audience move**: Has a payback figure → can see which named drivers produce the plan, and can tell the one actual year from the three projected ones at a glance
- **Relationships**: order (FY2026 through FY2029); parent (each year's revenue composed of three drivers); contrast (actual against projected)
- **Composition**: A stacked column per year across the page, the actual year solid and the projected years hatched and labelled; the driver arithmetic runs beneath in the monospace role rather than a polished output table.
- **Title**: Expansion seats, not new logos, carry the plan from FY2027
- **Core message**: Revenue is driven by three named quantities — new seats, expansion seats within existing customers, and manufacturer-channel seats — and expansion overtakes new business in FY2028.
- **Content**:
  - Chart block: revenue by driver, £m — FY2026 actual: new 0.62, expansion 0.31, channel 0.00, total 0.93 · FY2027P: 1.45 / 0.72 / 0.18, total 2.35 · FY2028P: 2.90 / 1.74 / 0.66, total 5.30 · FY2029P: 4.80 / 3.60 / 1.70, total 10.10
  - Driver arithmetic: new seats × £180 × 12 · expansion at 118% net revenue retention held flat · channel seats at the £2,900 acquisition cost already measured
  - Actual-vs-projected rule: FY2026 is solid and labelled actual; FY2027 to FY2029 are hatched and labelled projected, and the difference is texture as well as colour
  - Exposure line: the plan assumes retention holds at 118% and that the manufacturer channel scales past one partner. Neither is proven. If retention falls to 105%, FY2029 revenue falls by roughly a quarter.
  - Illustrative marker: all financial figures are illustrative
- **Visualization**: `revenue-by-driver` — native stacked column chart, four years by three drivers, y-axis from zero titled "Revenue (£m)", value labels at two decimals on totals. `Native-ready`: revenue-by-driver=yes
- **Motion suggestion**: The axis frame stays; the actual year rises first and alone, then the three projected years together, so the boundary between them is visible before the trend is.
- **Data class: scenario** — every revenue, driver and retention figure is invented.
- **page_rhythm**: dense

#### Slide 13 - The ask

- **Audience move**: Has the whole argument → knows exactly what is being raised, over what period, and what has to be true at the end of it
- **Relationships**: link (the amount to the runway and to the milestone it reaches); parent (the round containing the five funded areas that appear on the next page)
- **Composition**: One page, one figure at display scale, built from five visibly separable segments; runway and milestone sit beneath it on a single rule. Nothing else on the page.
- **Title**: We are raising £4.2M
- **Core message**: £4.2M buys 24 months, two new markets and the manufacturer API, and reaches £5.3M ARR.
- **Content**:
  - Ask figure: £4.2M seed
  - Runway line: 24 months of runway to Q3 2028
  - Milestone line: £5.3M ARR, two additional markets live, manufacturer API in production with three partners
  - Illustrative marker: the round, runway and milestones are illustrative
- **Closing impact**: The binding takeaway is that the ask is unambiguous and tied to a named end state. Composition is a Reference: the figure is the page, and its segments are already the shape of the next page.
- **Motion suggestion**: The figure arrives as one object; the five segments become separable only as the page settles, preparing the split on the next page.
- **Data class: scenario** — the round size, runway and milestones are invented.
- **page_rhythm**: anchor

#### Slide 14 - Use of funds

- **Audience move**: Knows the amount → can see what each pound buys and which milestone it reaches
- **Relationships**: parent (the £4.2M containing five funded areas); order (areas by size); link (each area to the milestone it reaches)
- **Composition**: The ask figure's five segments arrive from the previous page and settle into a proportional bar along the top; the native table sits beneath with amount, share, what it buys and the milestone.
- **Title**: Forty-four pence in every pound goes into the planner
- **Core message**: The round is weighted to product and to the two markets that make the manufacturer channel repeatable, with a stated reserve rather than an implied one.
- **Content**:
  - Table rows: engineering and product £1.85M (44%) — capacity planner v2 and the manufacturer API — API in production with three partners · go-to-market £1.30M (31%) — Germany and the Netherlands live — 40% of new seats from outside the UK · customer success and training £0.55M (13%) — onboarding at a 10-day median — net revenue retention held at 118% · data and compliance £0.30M (7%) — grant and accreditation reporting automated — reporting shipped for two national schemes · reserve £0.20M (5%) — three-month buffer — not allocated
  - Total line: £4.20M, 100%
  - Illustrative marker: all amounts, shares and milestones are illustrative
- **Visualization**: `use-of-funds` — native table, five funded areas by four fields (amount, share, what it buys, milestone), with a total row; currency to two decimals and share as whole percent. `Native-ready`: use-of-funds=yes
- **Motion suggestion**: The five segments are the same objects as the ask figure and should be seen to separate into the proportional bar; the table rows follow in size order.
- **Data class: scenario** — every amount, share and milestone is invented.
- **page_rhythm**: dense

#### Slide 15 - Diligence appendix

- **Audience move**: Is ready to ask hard questions → can find each metric's definition, measurement period and system of record, and can open every external source directly
- **Relationships**: membership (each metric belonging to the definitions set); link (each external claim to its source URL)
- **Composition**: Deliberately dense and organised for retrieval: the definitions table occupies the upper two-thirds, the source list runs beneath it as linked lines, and the illustrative boundary is restated at the foot.
- **Title**: Definitions, measurement periods and every external source
- **Core message**: Every internal metric has a fixed definition and a system of record; every external figure in this deck is one click from its source.
- **Content**:
  - Definitions table: live engineer seat — one engineer with an active licence on the last day of the month — monthly, since 2025-01 — billing system · ARR — live seats × list price × 12, net of discount — at month end — billing system · net revenue retention — trailing twelve months, existing customers only, excludes new logos — monthly — billing system · customer acquisition cost — blended sales and marketing spend ÷ new customers, same quarter — quarterly — finance ledger · payback — acquisition cost ÷ monthly gross contribution — per cohort — finance ledger
  - Source links, each a native hyperlink on its title: IEA Global Energy Review 2026 · IEA Heat Pump Monitor 2026 via Heat Pumping Technologies · European Commission — Heat pumps · European Commission — phasing out fossil-boiler financing · EHPA — half a million heat pump workers · Nesta — the heat pump installer gap · Nesta — staff shortages survey · Ofgem — Boiler Upgrade Scheme monthly update · GOV.UK — Boiler Upgrade Scheme grants · IRS — OBBB section 25C FAQ · Jobber — published pricing
  - Policy reference retained for questions: to 31 July 2026 the UK Boiler Upgrade Scheme had received 151,136 applications, issued 101,029 vouchers, redeemed 93,364 and paid £661,303,000; the grant is £7,500 for an air- or ground-source heat pump with £1,500 more off gas grid until March 2027; the US section 25C credit is not allowed for property placed in service after 31 December 2025
  - Illustrative boundary restated: Heatline is fictional. Every company, product, customer, traction, pipeline and financial figure in this deck is illustrative. Every external figure is sourced above.
- **Visualization**: `metric-definitions` — native table, five metrics by three fields (definition, measurement period, system of record). `Native-ready`: metric-definitions=yes
- **Fact IDs**: F015, F016, F017, F018
- **page_rhythm**: dense

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: Ground every note in what is visible on its own final SVG. Carry the presenter's transition into the page, the one sentence that makes the claim land, and the detail deliberately kept off the slide — the derivation behind a figure, the honest reading of a survey, the assumption most likely to be attacked. Every note that mentions a Heatline figure states that it is illustrative; every note that mentions an external figure names its source. Notes never introduce a number that is absent from the page and its facts file.
- **Total duration**: about 15 minutes for the fifteen pages, weighted toward the problem, traction and ask pages
- **Notes style**: conversational but precise — spoken sentences a founder would actually say, with the defensible version of each number ready
- **Presentation purpose**: Persuade that installer capacity is the binding constraint, then obtain a first-meeting decision on a £4.2M seed round, leaving a diligence trail that survives forwarding

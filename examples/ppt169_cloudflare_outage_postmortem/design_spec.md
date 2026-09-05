<!-- ppt-master-schema: design-spec/v1 -->
# Cloudflare Outage Postmortem - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | cloudflare_outage_postmortem |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 15 |
| Primary Language | en |
| Target Audience | Site-reliability and platform engineers, incident commanders, and the engineering leaders they report to, at organizations whose availability depends on Cloudflare; secondary readers are reliability reviewers who will reuse this account as a worked example of a blameless postmortem. They know what a reverse proxy and a config rollout are; they have not read the 22,000-character source post. |
| Communication Intent | Record and hand off first: establish an accurate, source-anchored account of the 18 November 2025 Cloudflare outage that can be cited without reopening the blog. Then explain the mechanism by which a database permissions change became a global HTTP 5xx event. Then align readers on which conditions persist, which corrective actions Cloudflare committed to, and which questions the published account leaves open. Never argue about fault. |
| Desired Audience Outcome | A reader who was not there can restate the trigger, the mechanism, the impact window, and the detection-versus-diagnosis gap from memory; can tell an observed fact from an inference and from an unconfirmed item; and can name both the corrective actions and what the published account does not settle. |
| Core Message / Ask / Action | A routine database permissions change at 11:05 UTC doubled a Bot Management feature file; a fixed 200-feature preallocation limit turned that oversized file into an unhandled panic in the core proxy; the failure was detected in three minutes but took nearly three hours to diagnose because a five-minute regeneration cycle made it look like an attack. The condition that made it global — internally generated configuration propagated worldwide without staged rollout or consumer-side validation — is the same condition behind the 2 July 2019 outage. |
| Delivery Context | Primary: reader-led. A written postmortem circulated asynchronously and read end to end by people who were not in the incident channel. Secondary: presented in a 30-minute incident-review meeting where the timeline and corrective-action pages are projected. |
| Artifact Afterlife | Review, audit, and archive. Individual pages — the summary, the timeline, the corrective actions — will be quoted and forwarded on their own, so each must stand alone. Reused as a structural reference for internal postmortems. |
| Reading Mode | text |
| Content Strategy | Stay close. Every number, timestamp, product name, identifier, and quoted string comes from the published Cloudflare accounts of 18 November 2025 and 2 July 2019. Nothing is estimated, rounded for effect, or supplied from outside those two documents; where the source does not state a value, the page says NO DATA or marks the item unconfirmed. Elapsed durations are arithmetic on published timestamps and are labeled as derived. |
| Design Style | Incident Postmortem method (installed Style workspace) realized as a neutral achromatic record: white field, hairline rules, a fixed left-to-right time direction, and colour reserved entirely for the four declared severity states, each always paired with a text label. |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — workflow default (no explicit user instruction; proactive Stage-2 value `true`) |
| Custom Animations | enabled — explicit user instruction: the deck must carry a hand-authored `animations.json` with at least two Morph pairs |
| Narration Audio | disabled — workflow default |
| Created Date | 2026-09-05 |

- **Template Application**: The installed `incident-postmortem` Style supplies the communication method and the design defaults, and nothing else — it owns no structure, so every page is composed freely and flat. Adopted deliberately: its argument flow (facts, then interpretation, then action), its claim discipline (observed event / inferred sequence / contributing factor / hypothesis kept distinct, unconfirmed items marked, systems and roles named instead of people), its page-role vocabulary as the roster's skeleton, its evidence rules (one timestamp precision and one stated time zone throughout, native editable tables for timeline and actions, no redrawn monitoring graph presented as the record), its restraint defaults (effectively no decoration, colour only for declared severity, always with a label), and its Fallback Colour Scheme and typographic character (plain neutral sans plus a genuinely monospaced companion) — taken as identity because no Brand or Deck workspace is active. Two Style tendencies are deliberately not followed: its `digital-dashboard` image rendering and its evidence-image guidance are inert because this deck carries no images at all (the only legitimate evidence images are Cloudflare's copyrighted screenshots), and its instruction to keep monitoring graphs as captured evidence rather than redrawing them is honoured by labelling the one time-series page a schematic reconstruction rather than a record. Its Review Focus section is not activated.

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

- **Mode**: briefing
- **Visual style**: swiss-minimal
- **Theme**: A record, not a report about a record. A white field with a strict two-band grid, hairline rules instead of boxes, and a time direction that never changes: earlier is always left, later is always right, on the chart, on the timeline tables, and on the severity strip that runs across the deck. The only chromatic events on any page are the four declared severity states.
- **Tone**: Factual, unhurried, and unembarrassed. The account describes what responders could see at each moment; it never uses hindsight vocabulary and never attributes an outcome to a person.

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | Neutral ground for a factual record; every page |
| Secondary background | #F2F4F6 | Grouped regions, table banding, evidence and code blocks |
| Primary | #1F2933 | Primary text, page titles, rules, table ink |
| Accent | #B4342C | Severity `Critical` — the full impact window and the breached limit; always with its label |
| Secondary accent | #B7791F | Severity `Degraded` — partial impact, detection gap, elevated risk; graphic use only, never body text (3.7:1 on the field) |
| Body text | #1F2933 | Running body copy |
| Secondary text | #5A6673 | Captions, annotations, source lines, footnotes |
| Divider | #D7DDE3 | Hairline rules, table borders, band separators |

Two further neutral roles carry stable meaning across the deck and are locked with the palette: `surface` #F2F4F6 (panel lift, table banding) and `grid` #E8ECEF (chart hairlines, one step lighter than dividers). Two further severity roles complete the declared four-state scale: `normal` #4A5568 (pre-incident baseline and unaffected state) and `recovered` #2E7D5B (mitigation effective, service restored). Each state also carries one recurring tint used as the severity cell field in every table and nowhere else — `normal` #EDEFF2, `degraded` #FAF0DC, `critical` #F7E4E2, `recovered` #E4F0EA — so the state reads at a glance while its label stays in body ink at full contrast. The severity mapping is fixed for the whole document and every use is paired with its text label, so it survives greyscale printing.

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | Neutral grotesque; hierarchy from weight and alignment, never from containers | Arial | — | sans-serif |
| Body | Same neutral grotesque at reading weight | Arial | — | sans-serif |
| Data | Genuinely monospaced companion for timestamps, identifiers, and table time columns | Consolas | — | monospace |
| Code | Same monospace at excerpt size for the SQL fragment and the panic string | Consolas | — | monospace |
| Display | Monospaced at hero scale so a hero window or duration keeps the same figure forms as every other timestamp | Consolas | — | monospace |

- **Title stack**: Arial
- **Body stack**: Arial
- **Data stack**: Consolas
- **Code stack**: Consolas
- **Display stack**: Consolas
- **Role rationale**: The Style requires a plain neutral sans with a genuinely monospaced companion, so Title and Body concord on one family and the contrast is carried by the mono roles. `Data` recurs on six pages (every timestamp, every identifier, the time column of three tables); `Code` recurs on two (the SQL fragment and the panic line) and needs a smaller anchor than `Data` so an unwrapped log line stays on one line; `Display` recurs on three (cover, summary, detection) for the published windows and derived durations, and stays monospaced so a hero figure and a table timestamp share one digit form.

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 20 |
| Title | 36 |
| Subtitle | 28 |
| Annotation | 16 |
| Lead | 26 |
| Data | 18 |
| Code | 16 |
| Display | 56 |
| Cover title | 64 |
| Footnote | 12 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: Title states what the page establishes; a single lead line carries the governing assertion; evidence sits below it in one band. The eye moves top-left to bottom-right once, with no competing focus.
- **Composition tendency**: One fact per page under a strict grid. A fixed 12-column field with a persistent left rule; timeline and chart pages give the full width to chronology; summary, systemic-condition, what-went-well, and action pages get real vertical air.
- **Cross-page continuity**: A severity strip — a thin horizontal band spanning 11:05 to 17:06 UTC, segmented into the four declared states — recurs on the pages that place a moment in the window, always at the same y and always with the same left-to-right direction, with the page's own moment marked. A hairline rule under every page title. A source line in `Annotation` at the foot of every evidence page. Pages that carry no chronology omit the strip rather than decorate with it.
- **Spacing posture**: Variable by page rhythm — anchor pages breathe, the four table pages carry real density without truncating any identifier.
- **Spacing anchors**: page margin 64 px, block gap 28 px, column gutter 32 px, corner radius 0 px, body leading 30 px.

## VI. Icon Usage Specification

- **Primary bundled library**: chunk-filled
- **Brand-logo library**: simple-icons

| Icon Path | Suitable Scenarios |
| --- | --- |
| chunk-filled/circle-minus | Severity `Normal` — baseline or unaffected state, always beside the word Normal |
| chunk-filled/triangle-exclamation | Severity `Degraded` — partial impact or detection gap, always beside the word Degraded |
| chunk-filled/circle-x | Severity `Critical` — full impact window or breached limit, always beside the word Critical |
| chunk-filled/circle-checkmark | Severity `Recovered` — mitigation effective, always beside the word Recovered |
| chunk-filled/clock | Event class: an elapsed-time fact stated as a derived duration |
| simple-icons/cloudflare | The subject organization appearing as itself on the cover and the sources page |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P03 | table | record_table | One row per impacted product surface with the impact description published for it |
| P05 | chart | line_chart | Relative 5xx volume against the published event clock, as a schematic reconstruction |
| P06 | table | record_table | Timeline entries 11:05–13:05 UTC with status and description |
| P07 | table | record_table | Timeline entries 13:37–17:06 UTC with status and description |
| P13 | table | record_table | Published corrective actions with the factor each addresses and its unpublished owner/date/verification |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

No image resource is planned. The Style admits images only as evidence, and the only evidence images that exist for this incident are Cloudflare's copyrighted screenshots and monitoring captures, which this deck may not redistribute. Conceptual or atmospheric imagery is forbidden by the Style in a factual record. The one time-series page is therefore a native chart labelled as a schematic reconstruction, not a captured record.

## IX. Content Outline

### Part 1: What happened

#### Slide 01 - Cover

- **Audience move**: Has heard "Cloudflare was down on 18 November" → knows the event's exact window, that it was not an attack, and that the account below is sourced from Cloudflare's own post.
- **Relationships**: none
- **Cover impact**: The binding hook is the source's own strongest sentence — the outage was not caused, directly or indirectly, by a cyber attack or malicious activity of any kind — set against the window it actually occupied.
- **Composition**: Full-width title band over a single hero window `11:28 → 17:06 UTC`; the severity strip runs beneath it at its deck-wide position, fully segmented; the Cloudflare mark and the source line sit at the foot.
- **Title**: A database permissions change, not an attack, stopped Cloudflare's core traffic on 18 November 2025
- **Core message**: The event has a precise published window and a precise published non-cause.
- **Content**: Deck title · hero window `11:28 → 17:06 UTC` with the derived label `5 h 38 min` · the source's non-attack sentence quoted verbatim · source line naming the blog post, its author, and the note that all times are UTC.
- **Fact IDs**: source-2025 timeline rows 11:28 and 17:06; source-2025 paragraph 3.
- **Motion suggestion**: The severity strip is the deck's recurring carrier; it establishes itself here before any page places a moment on it.

#### Slide 02 - Incident summary

- **Audience move**: Knows the window → can restate trigger, mechanism, blast radius, and recovery in one breath, from a page that can be forwarded alone.
- **Relationships**: link — the permissions change causes the duplicate rows, which cause the oversized file, which meets the fixed limit, which causes the 5xx; order — the four published moments 11:05, 11:28, 14:30, 17:06 run in time order.
- **Composition**: One glanceable page: a four-cell fact band across the top (trigger / mechanism / scope / recovery), the governing assertion as a lead line beneath it, and the four published moments on the severity strip.
- **Title**: One feature file doubled in size and a fixed 200-feature limit turned it into a global 5xx event
- **Core message**: A permissions change made a generated configuration file exceed a preallocation limit in the core proxy, and everything downstream of that limit returned errors.
- **Content**: Trigger — a change to a database system's permissions deployed 11:05 UTC · Mechanism — a Bot Management feature file that doubled in size, past a 200-feature runtime limit against ~60 features in use · Scope — core CDN and security services, Turnstile, Workers KV, Dashboard, Email Security, Access · Recovery — core traffic largely flowing as normal by 14:30, all systems normal at 17:06 · lead line: the failure was in the ingestion of Cloudflare's own generated configuration, not in traffic · source line.
- **Fact IDs**: source-2025 timeline rows 11:05, 11:28, 14:30, 17:06; source-2025 impact table; source-2025 memory-preallocation section.

#### Slide 03 - Impact by product surface

- **Audience move**: Knows the event was global → knows exactly which surface failed and in which way, including the two surfaces that did not fail outright.
- **Relationships**: membership — six product surfaces belong to one impact set; contrast — Email Security and Dashboard degraded rather than failed, while core CDN, Turnstile, Workers KV, and Access returned errors.
- **Composition**: Full-width native table under a short lead; severity chip in the leading column, label always beside the mark.
- **Title**: Six product surfaces failed, and two of them degraded rather than stopped
- **Core message**: The impact was not uniform; the published account distinguishes error-returning surfaces from degraded ones.
- **Content**: Native table, one row per surface with Cloudflare's own impact description, condensed without changing its claim: Core CDN and security services (Critical, HTTP 5xx) · Turnstile (Critical, failed to load) · Workers KV (Critical, significantly elevated 5xx from the KV front-end gateway) · Dashboard (Degraded, mostly operational but most users could not log in) · Email Security (Degraded, temporary loss of an IP reputation source, reduced spam-detection accuracy, some Auto Move failures, all reviewed and remediated, no critical customer impact observed) · Access (Critical, widespread authentication failures until the rollback was initiated at 13:05; existing sessions unaffected) · footnote: elevated CDN latency during the impact period, caused by debugging and observability systems consuming CPU to enrich uncaught errors.
- **Visualization**: `impact-by-surface` — native table, six rows, columns Severity / Service or product / Published impact. `Native-ready`: impact-by-surface=yes
- **Fact IDs**: source-2025 impact table; source-2025 latency paragraph.

#### Slide 04 - Two proxy generations

- **Audience move**: Assumes every Cloudflare customer saw the same errors → knows the failure presented in two different ways depending on proxy generation, and that some customers saw nothing.
- **Relationships**: contrast — FL2 returned 5xx while FL returned a bot score of zero; membership — customers who did not use bot score in rules belong to neither failure mode.
- **Composition**: Two equal columns under one lead, divided by a hairline; a third, quieter line beneath both for the customers who saw no impact.
- **Title**: The same bad file produced errors on the new proxy and silent false positives on the old one
- **Core message**: An unrelated in-flight migration split the incident into two distinct customer experiences.
- **Content**: Context — customer traffic was being migrated to a new proxy engine, FL2, unrelated to this incident; both versions were affected but the observed impact differed · FL2 — customers observed HTTP 5xx errors · FL — no errors, but bot scores were not generated correctly and all traffic received a bot score of zero, so customers with rules that block bots would have seen large numbers of false positives · customers not using bot score in their rules saw no impact · claim label: this is an observed distinction from the published account, not an inference.
- **Fact IDs**: source-2025 FL/FL2 paragraphs.

#### Slide 05 - The five-minute cycle

- **Audience move**: Wonders why a global outage took hours to diagnose → sees that the system recovered and failed repeatedly, and understands why that pattern read as an attack.
- **Relationships**: order — the file was regenerated every five minutes; contrast — a good file and a bad file alternated until every node produced the bad one; link — the alternation caused the attack hypothesis.
- **Composition**: Wide time-series across the full content width with the published moments marked on the axis; a short explanation column beneath; the schematic disclaimer directly under the plot, not in a footnote.
- **Title**: The error rate rose and fell every five minutes until every database node produced the bad file
- **Core message**: The failure oscillated because only part of the cluster had been updated, and that oscillation is what made responders suspect an attack.
- **Content**: The feature file was generated every five minutes by a query on a ClickHouse cluster that was being gradually updated · bad data was produced only when the query ran on an already-updated part of the cluster, so each cycle could yield a good or a bad file · the system would fail and then recover, which the post calls very unusual behaviour for an internal error · eventually every ClickHouse node generated the bad file and the fluctuation stabilised in the failing state · required page label: Schematic reconstruction from the published account, not the original monitoring record · marked event moments 11:05, 11:28, 13:05, 14:30, 17:06.
- **Visualization**: `error-rate-schematic` — native line chart, one series, x = published event clock 11:00–17:30 UTC, y = relative 5xx volume with no published scale. `Native-ready`: error-rate-schematic=yes
- **Fact IDs**: source-2025 outage section; source-2025 timeline.
- **Data class: scenario** — every y value on this chart is invented to show shape only; the published account states the fluctuation and the event times but no error-rate magnitude. The x-axis moments are sourced.
- **Motion suggestion**: The severity strip's critical segment is established here and is the carrier that continues onto the timeline pages.

### Part 2: The reconstruction

#### Slide 06 - Timeline, 11:05 to 13:05

- **Audience move**: Has the shape of the event → can follow the first ninety-seven minutes entry by entry, with each timestamp and its status.
- **Relationships**: order — five published entries in time order; link — the 11:05 deployment causes the 11:28 first customer errors.
- **Composition**: Full-width native table owning the page; the severity strip above it with the covered range highlighted; consistent timestamp precision to the minute.
- **Title**: From the 11:05 access-control change to the first bypass at 13:05
- **Core message**: The first mitigation landed one hour and thirty-seven minutes after customer impact began, and before the trigger was known.
- **Content**: Native table rows from the published timeline — 11:05 Normal, database access control change deployed · 11:28 Impact starts, deployment reaches customer environments and first errors are observed on customer HTTP traffic · 11:31 first automated test detects the issue; 11:32 manual investigation begins; 11:35 the incident call is created · 11:32–13:05 the team investigates elevated traffic levels and errors to Workers KV; the initial symptom appeared to be a degraded Workers KV response rate causing downstream impact; traffic manipulation and account limiting were attempted · 13:05 Workers KV and Access bypass implemented, falling back to a prior core proxy version, and impact is reduced · derived line: 1 h 37 min from impact start to first bypass · source line.
- **Visualization**: `timeline-part-1` — native table, five rows, columns Time (UTC) / Status / What happened. `Native-ready`: timeline-part-1=yes
- **Fact IDs**: source-2025 timeline rows 11:05, 11:28, 11:32–13:05, 13:05.
- **Motion suggestion**: The severity strip carries over from the previous page and its highlighted range shifts to this page's window.

#### Slide 07 - Timeline, 13:37 to 17:06

- **Audience move**: Knows impact was reduced but not fixed → can follow the diagnosis, the stop, the test, and the two-stage recovery.
- **Relationships**: order — four published entries in time order; link — stopping file generation enables the known-good restore, which enables the global recovery.
- **Composition**: Identical to the previous page so the two read as one table split across a fold; the severity strip highlight moves right and its recovered segment appears.
- **Title**: From confidence in the trigger at 13:37 to full restoration at 17:06
- **Core message**: Once the bad file was identified, stopping its propagation and restoring a known-good version returned core traffic within six minutes of the global deploy.
- **Content**: Native table rows from the published timeline — 13:37 work focuses on rolling the Bot Management configuration file back to a last-known-good version, with multiple workstreams and the file restore as the fastest · 14:24 creation and propagation of new Bot Management configuration files is stopped, after identifying the Bot Management module as the source of the 500 errors · 14:24 test of the new file complete; recovery observed using the old version and the fix is accelerated globally · 14:30 main impact resolved; a correct configuration file is deployed globally and most services operate correctly · 17:06 all services resolved; all downstream services restarted and all operations fully restored · derived lines: 3 h 02 min from impact start to main resolution, 5 h 38 min to full resolution · source line.
- **Visualization**: `timeline-part-2` — native table, five rows, columns Time (UTC) / Status / What happened. `Native-ready`: timeline-part-2=yes
- **Fact IDs**: source-2025 timeline rows 13:37, 14:24 ×2, 14:30, 17:06.
- **Motion suggestion**: The strip's marked moment moves from 13:05 to 17:06 and the recovered segment completes.

#### Slide 08 - Detection and diagnosis

- **Audience move**: Assumes a slow response → sees that detection was almost immediate and that the gap was entirely in diagnosis, then understands why.
- **Relationships**: contrast — 3 minutes to detect against 2 h 53 min to identify the module; link — the alternating failure and the coincidental status-page outage sustained the attack hypothesis.
- **Composition**: Two hero durations side by side under one lead, with the gap between them named; the three reasons the diagnosis stalled listed beneath as prose, not as blame.
- **Title**: Detection took three minutes; identifying the failing module took two hours and fifty-three
- **Core message**: The alerting worked; what took the time was the hypothesis, and the published account says why.
- **Content**: The first automated test detected the issue at 11:31, three minutes after impact starts at 11:28; manual investigation started at 11:32 and the incident call was created at 11:35 · the Bot Management module was identified as the source of the 500 errors at 14:24, two hours and fifty-three minutes after detection · three published reasons the diagnosis was slow, each an observed fact and not a judgement: the system recovered and failed repeatedly as good and bad files alternated, which the post calls very unusual for an internal error; Cloudflare's status page, hosted completely off Cloudflare's infrastructure with no dependencies on Cloudflare, went down at the same time, which the post calls a coincidence and which led some responders to believe an attacker was targeting both; the internal incident channel considered a continuation of recent high-volume DDoS activity · inferred sequence label: the attack hypothesis is what the published account says the team held, not a criticism of holding it.
- **Fact IDs**: source-2025 timeline row 11:32–13:05; timeline row 14:24; source-2025 status-page and DDoS paragraphs.

### Part 3: What allowed it

#### Slide 09 - Mechanism

- **Audience move**: Knows what happened → can trace the exact path from an SQL metadata query to a thread panic, with the two published strings in front of them.
- **Relationships**: link — five stages in strict causal order, each the cause of the next; parent — the `default` and `r0` databases are two schemas behind one distributed table.
- **Composition**: A five-stage horizontal chain across the full width, each stage a labelled band rather than a box; the SQL fragment and the panic line sit below it in monospaced blocks on the surface tint.
- **Title**: A query that filtered on table name but not database name became an unhandled panic in the core proxy
- **Core message**: Every stage of the chain behaved as written; the failure is in the assumptions that connected them.
- **Content**: Stage 1 — at 11:05 an access change made previously implicit permissions on the underlying `r0` database explicit, so users could see metadata for those tables as well · Stage 2 — the Bot Management feature-generation query selected name and type from `system.columns` filtered only on `table = 'http_requests_features'`, with no database predicate, so it began returning duplicate columns for `r0` as well as `default` · Stage 3 — the feature file's row count more than doubled · Stage 4 — the bots module preallocates memory for a maximum of 200 machine-learning features against roughly 60 in use, and the oversized file exceeded that limit · Stage 5 — the FL2 check on that limit produced an unhandled error and the thread panicked, returning HTTP 5xx for any traffic that depended on the bots module, and with it Workers KV and Access · monospaced excerpt of the published query · monospaced panic line `thread fl2_worker_thread panicked: called Result::unwrap() on an Err value` · claim label: stages 1–4 are observed facts from the published account; the ordering between them is the account's own inferred sequence.
- **Fact IDs**: source-2025 query-behaviour-change section; source-2025 memory-preallocation section.

#### Slide 10 - Contributing factors

- **Audience move**: Looking for the root cause → accepts that four conditions had to hold at once, two technical and two procedural.
- **Relationships**: membership — four factors belong to one incident; contrast — two are properties of code, two are properties of process; overlap — factors 1 and 2 are both assumptions that held until an input changed.
- **Composition**: Four equal-weight bands stacked down the page, each with its class label at the left rule; deliberately not a single-box root-cause diagram.
- **Title**: Four conditions had to hold at once, and no single one of them is the cause
- **Core message**: A single-cause reading of this incident would misdescribe it; the published account names conditions in code and in process.
- **Content**: Technical — a query in the feature-generation path assumed that table metadata would only ever be returned for the `default` database, an assumption the post says was made in the past and was not restated when the permissions model changed · Technical — a fixed preallocation limit of 200 features guarded memory but had no bounded failure path, so an oversized input became a panic rather than a rejected file · Procedural — Cloudflare-generated configuration was ingested with less validation than user-generated input, which the post's first remediation item makes explicit by committing to harden it in the same way · Procedural — the permissions change propagated gradually across the cluster, so the generated output alternated between good and bad every five minutes and the failure signature resembled an attack rather than a deployment · each factor carries the label observed / inferred and the timeline evidence it traces to.
- **Fact IDs**: source-2025 query-behaviour-change section; memory-preallocation section; remediation list; outage section.
- **Motion suggestion**: The fourth factor, rapid global propagation of internally generated configuration, is the unit that continues onto the next page as its subject.

#### Slide 11 - Systemic condition

- **Audience move**: Treats this as a one-off bug → recognises the same propagation condition behind Cloudflare's 2019 outage and understands why the condition outlives the trigger.
- **Relationships**: contrast — 2019 and 2025 differ in trigger and duration; overlap — both share global-in-seconds propagation of internally generated configuration with no staged rollout; link — the shared condition is why a kill switch is the remediation in both.
- **Composition**: The carried-over factor becomes the page's headline band; two dated columns beneath it compare the two events across trigger, propagation path, mitigation, and duration; a closing line names what persists.
- **Title**: Rapid global propagation of internally generated configuration is the condition both 2019 and 2025 share
- **Core message**: The trigger changes; the condition that turns a local defect into a global outage has not.
- **Content**: 2 July 2019 — a new WAF managed rule containing a regular expression that backtracked enormously exhausted CPU on every core handling HTTP/HTTPS traffic worldwide, customers saw 502 errors, and the service was down for 27 minutes; the rules were distributed through the Quicksilver key-value store, which pushes changes globally in seconds, and by design the WAF did not use the staged DOG/PIG/Canary/Global process because it must respond rapidly to threats; the mitigation was a global kill switch — a global terminate executed at 14:07, with traffic and CPU back to expected levels by 14:09 · 18 November 2025 — a Bot Management feature file regenerated every five minutes propagated to all the machines that make up the network, and the published remediation commits to enabling more global kill switches for features · the shared condition: internally generated configuration reaches every machine in minutes or seconds, is trusted more than user input, and has no per-feature off switch until one is added after the fact · the post states this was Cloudflare's worst outage since 2019 and that in the last six-plus years no other outage had caused the majority of core traffic to stop flowing through the network · claim label: the shared condition is an inference drawn across two published accounts, and it is labelled as such on the page.
- **Fact IDs**: source-2025 remediation list; source-2019 WAF/Quicksilver/global-terminate sections.

### Part 4: What follows

#### Slide 12 - What went well

- **Audience move**: Reads the account as a list of failures → can name three controls that measurably limited the damage and must be protected.
- **Relationships**: membership — three protective controls belong to one set; link — each control is tied to the specific harm it bounded.
- **Composition**: A breathing page. Three items with generous vertical air, each a short assertion plus the harm it bounded; no icons beyond the recovered severity mark.
- **Title**: Three controls limited the damage and are the ones to protect
- **Core message**: Automated detection, a usable bypass, and a graceful older code path each bounded the impact, and a review that lists only failures would lose them.
- **Content**: Automated detection worked and was fast — the first automated test detected the issue at 11:31, three minutes after impact began at 11:28, and manual investigation began the following minute · A bypass path existed and was used before the trigger was known — at 13:05 internal system bypasses failed Workers KV and Cloudflare Access back to a prior core proxy version, reducing impact for every downstream system that depends on Workers KV, including Access itself · The older proxy generation degraded instead of failing — customers on FL did not see errors, and customers who were not using the bot score in their rules saw no impact at all · claim label: each item is an observed fact from the published account; the judgement that they are worth protecting is this review's.
- **Fact IDs**: source-2025 timeline rows 11:28, 11:32–13:05, 13:05; source-2025 other-impact and FL/FL2 paragraphs.

#### Slide 13 - Corrective actions

- **Audience move**: Wants to know what changes → has the four published commitments, the factor each addresses, and an explicit record that owner, date, and verification were not published.
- **Relationships**: link — each action addresses one named contributing factor; membership — four commitments belong to one published remediation list; contrast — prevention, detection, and mitigation are distinguished.
- **Composition**: Full-width native table; the three unpublished columns are shown and filled with NO DATA rather than dropped, so the omission is visible.
- **Title**: Four corrective actions are published, and none of them carries an owner, a date, or a verification method
- **Core message**: The commitments are real and traceable to factors; the accountability metadata a postmortem needs is absent from the published account.
- **Content**: Native table, one row per published action — hardening ingestion of Cloudflare-generated configuration files in the same way as user-generated input (prevention; addresses the procedural validation factor) · enabling more global kill switches for features (mitigation; addresses the propagation factor) · eliminating the ability for core dumps or other error reports to overwhelm system resources (mitigation; addresses the observability-CPU latency effect) · reviewing failure modes for error conditions across all core proxy modules (prevention; addresses the unbounded-failure-path factor) · every Owner, Due date, and Verification cell reads NO DATA, with a footnote stating that the published account contains no owner, date, or verification method for any of the four.
- **Visualization**: `corrective-actions` — native table, four rows, columns Action / Class / Factor addressed / Owner / Due / Verification. `Native-ready`: corrective-actions=yes
- **Fact IDs**: source-2025 remediation list; source-2025 latency paragraph.

#### Slide 14 - Open questions

- **Audience move**: Believes the account is complete → knows precisely which five items the published record leaves unsettled and what evidence would settle each.
- **Relationships**: membership — five unresolved items belong to one set; contrast — two are internal inconsistencies in the published timestamps, three are absences.
- **Composition**: A breathing page. Five short items, each a question followed by the evidence that would answer it; the two timestamp conflicts sit first and quote both published values.
- **Title**: Five questions the published account does not settle
- **Core message**: The unresolved items stay visible rather than being closed with a plausible narrative.
- **Content**: When did impact begin — the opening paragraph states that the network began experiencing significant failures at 11:20, while the incident timeline records impact starts at 11:28; the two values are not reconciled in the post, and this deck uses 11:28 for every derived duration and says so · When was the Workers KV bypass effective — the narrative gives 13:04 for the patch and 13:10 for restoration, while the timeline gives 13:05 for the bypass; three values describe one mitigation · What did it cost — no error count, request volume, affected-customer count, duration-weighted availability figure, or financial figure is published; NO DATA · Who owns the four corrective actions and by when — no owner, date, or verification method is published; NO DATA · Whether other core proxy modules share the unbounded-failure pattern — the post commits to reviewing failure modes across all core proxy modules but does not state whether any others were found; unconfirmed · closing line: each item names the evidence that would settle it, and none is answered by inference here.
- **Fact IDs**: source-2025 opening paragraph; source-2025 timeline rows 11:28 and 13:05; source-2025 other-impact paragraph; source-2025 remediation list.

#### Slide 15 - Sources

- **Audience move**: Has read a summary → can reach every underlying document and re-verify any claim in this deck.
- **Relationships**: order — primary source, comparison source, live status record; link — each source is tied to the pages it supports.
- **Closing impact**: The binding takeaway is that every number in this deck is checkable in one click, and the deck says exactly where each came from.
- **Composition**: An anchor page. Three source entries with live links, each followed by the pages it supports; a standing note on time-zone and derivation policy; the Cloudflare mark at the foot.
- **Title**: Every figure in this deck traces to one of three published records
- **Core message**: This is a derived account; the record itself is one link away.
- **Content**: Primary — Cloudflare, Cloudflare outage on November 18, 2025, by Matthew Prince, published 18 November 2025, linked to `https://blog.cloudflare.com/18-november-2025-outage/`, supporting slides 1–10 and 12–14 · Comparison — Cloudflare, Details of the Cloudflare outage on July 2, 2019, linked to `https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/`, supporting slide 11 · Live status record — Cloudflare System Status, linked to `https://www.cloudflarestatus.com/`, listed as the operator's own event record and not consulted for any figure in this deck · policy note: all times are UTC to the minute, exactly as published; elapsed durations are arithmetic on published timestamps and are labelled derived; no figure originates outside these documents; the schematic chart on slide 5 carries no published magnitudes.
- **Fact IDs**: source-2025 header and author line; source-2019 header.

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: One note per slide, grounded in that slide's final SVG and in the two published Cloudflare accounts. Notes carry the interpretation and the transitions that the page deliberately does not: why a figure is stated the way it is, which claim class each item belongs to, and what a reader should not conclude. Notes never introduce a number, timestamp, or product name that is not on the page or in the sources, and never soften an unconfirmed item into a settled one.
- **Total duration**: approximately 22–26 minutes at a measured reading pace across 15 slides
- **Notes style**: formal
- **Presentation purpose**: Record and hand off an accurate account of the 18 November 2025 Cloudflare outage, explain its mechanism, and align readers on the persisting condition, the committed actions, and the open questions.

<!-- ppt-master-schema: design-spec/v1 -->
# The Night Shelf - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | The Night Shelf — campaign pitch for Fog & Fern Books |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 13 |
| Primary Language | en-US |
| Target Audience | The owner and the four-person team of Fog & Fern Books, a fictional independent bookstore in a mid-size English-speaking city — people who know their shop and their regulars intimately, who have never commissioned a campaign before, and who will judge the work by whether it sounds like their shop rather than by advertising craft |
| Communication Intent | Persuade first, then align: make the team feel one idea and believe it came from a real truth about how people actually spend their evenings; then align them on what the late-autumn campaign is, what it asks of the shop, and what happens next. Evidence carries the opening; the idea carries the middle; production reality closes. |
| Desired Audience Outcome | The team can repeat the campaign line exactly after one hearing, can name the audience truth it rests on, and agrees to take the campaign into production for late autumn |
| Core Message / Ask / Action | The last hour of the day is the only reading time still available, and it currently belongs to a screen; "The Night Shelf" takes it back — approve the campaign for late autumn |
| Delivery Context | Presenter-led, in the shop, one meeting, roughly twenty minutes with the deck on a screen; secondary use as a leave-behind the owner reads again alone before deciding |
| Artifact Afterlife | Review and approval, then hand-off to production as the scope-of-work reference; the sources must stay checkable in the file |
| Reading Mode | presentation |
| Content Strategy | Free — no source outline exists; the argument, the campaign and the whole visual identity are invented for this pitch. Hard boundary: every externally verifiable number stays sourced to the imported facts file, and every invented client, commercial, or production figure is marked illustrative on the page where it appears. |
| Design Style | Showcase argument in a photo-editorial deck whose own voice stays quiet so the campaign's identity is the only thing with colour and character |
| AI Image Acquisition Path | auto (Path A — `image_gen.py --manifest`) |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — workflow default retained at final Stage 2 (`proactive_speaker_notes: true`) |
| Custom Animations | enabled — explicit run instruction requiring per-page custom animations, which overrides the `false` proactive default |
| Narration Audio | disabled — workflow default; no narration was requested |
| Created Date | 2026-09-10 |

- **Template Application**: Adopt the installed Creative Pitch Style wholesale as the deck's communication method and design discipline — its argument flow (audience truth → task → strategic thought → the idea → hero execution → range → identity → tone → environment → production reality → close), its one-moment-per-page message discipline, its Claim Discipline separating insight, idea, execution and production reality, its neutral-field colour behaviour, and its image direction. The Style supplies no structure, so every page is flat free design. Two Style defaults are consumed with a stated decision: the preferred `showcase` mode and `photo-editorial` visual style are kept; the preferred `editorial` image rendering is replaced by a custom rendering because `editorial` is a magazine-infographic treatment and this deck's images are night photography and printed poster artwork, not infographics.

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 72 px on all four sides; full-bleed imagery may cross them |
| Content Area | x 72–1208, y 72–648 (1136 × 576) |

## III. Visual Theme

### Theme Style

- **Mode**: showcase
- **Visual style**: photo-editorial
- **Theme**: The deck is a dark room with one light in it. The presentation's own field is night ink and stays neutral so the campaign's colours are seen accurately; the campaign supplies the only warmth. One mark recurs — a short horizontal rule with a crescent resting on it, the shelf and the night — drawn natively so it survives every scale, and it is the continuity object that carries from the idea page into the hero and from tone into environment. Creative pages carry no chrome, no page numbers and no footer; the two factual pages (production and close) switch to a paper field, which is the register shift itself.
- **Tone**: Quiet, unhurried, confident. The deck never explains a picture it has just shown.

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | `#0E0E10` | Night ink — the deck's neutral field for the whole creative arc |
| Secondary background | `#F4F1EA` | Paper — the field for the production and close pages, the visible register shift |
| Primary | `#E9C877` | Lamplight — the campaign's one light: the mark, the light source inside every image, the reading series in the chart |
| Accent | `#7FA69B` | Fern — the shop's own signature, used only on surfaces the shop owns (window, shelf talker, event) |
| Secondary accent | `#C4553F` | Ember — reserved for the thing being taken back: the screen, and the screen series in the chart |
| Body text | `#EDEAE3` | Paper-cream type on the night field |
| Secondary text | `#A29E97` | Captions, attribution, source lines, contextual annotation |
| Divider | `#2E2E33` | Hairlines and rules on the night field |
| Ink | `#141416` | Type on the paper field (production and close pages) |
| Scrim | `#08080A` | Gradient scrim stops beneath type sitting over imagery — never a whole-frame dim |
| Grid | `#3A3A40` | Chart hairlines and axis rules, lighter than dividers |

### AI Image Strategy

- **Image Rendering**: custom
- **Visual**: Photographic night interiors and streets at low key, lit by one practical warm light — a shaded lamp, a shop window, a bedside bulb — with true depth of field, real materials (paper, painted wood, glass, wet pavement, wool) and deep unlit space left genuinely dark. Inside those photographs, any surface that belongs to the campaign itself — a pasted street poster, a phone screen, a printed bookmark — is rendered as flat printed ink: two or three solid colours, stencil-cut shapes, visible halftone in the transitions, no gradient inside a printed shape. Nothing in any image contains text.
- **Mood**: The last hour before sleep, with one lamp on. The reference is the window of a bookshop seen from a cold pavement at seven in the evening, not a lifestyle catalogue.
- **Image Rendering Behavior**: Photograph the world at night and print the campaign onto it. Lines are photographic and absent except where printed artwork appears, where edges become stencil-cut and slightly misregistered. Texture is real material grain plus a halftone dot pattern confined to printed surfaces and a light film grain over the whole frame. Depth is true optical depth — a sharp foreground object, a falling-off middle ground, unlit background — while printed surfaces stay perfectly flat inside that depth. Material is paper, glass, wood and skin under a single warm source; the mood is quiet, contemplative and slightly cold outside the light.
- **Image Rendering References**: `corporate-photo` (photographic realism, optical depth of field and real material rendering), `warm-scene` (single-source golden lamplight, bloom and atmospheric falloff), `screen-print` (flat two-to-three-colour printed ink, stencil edges and halftone, applied only to campaign surfaces inside the frame)

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | Serif / bookish, high-contrast, the voice of the work itself | Georgia | — | serif |
| Body | Sans / quiet, small, the deck's own unobtrusive voice | Arial | — | sans-serif |
| Display | Sans / lining figures for numerals shown at statement scale | Arial | — | sans-serif |
| Cover title | Serif / the campaign's own voice at cover scale | Georgia | — | serif |
| Idea line | Serif / the campaign line at statement scale | Georgia | — | serif |

- **Title stack**: `Georgia, serif`
- **Body stack**: `Arial, sans-serif`
- **Display stack**: `Arial, sans-serif`
- **Cover title stack**: `Georgia, serif`
- **Idea line stack**: `Georgia, serif`
- **Role rationale**: the cover title and the campaign's idea line belong to the work's serif voice, so they take the Title family explicitly rather than inheriting the body sans. Georgia sets old-style figures whose digits sit at different heights, so every numeral shown at statement scale — the two audience-truth numbers, the chart labels, the table values — uses the Display/Arial stack instead of the Title family. Georgia titles are kept wordy for the same reason.

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 30 |
| Cover title | 84 |
| Idea line | 72 |
| Display (hero numeral) | 96 |
| Title | 48 |
| Subtitle | 38 |
| Lead | 36 |
| Annotation | 24 |
| Footnote | 18 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: One thing per page arrives first and everything else is subordinate to it. On creative pages the work arrives first and the line second; on the two factual pages the title arrives first and the grid second.
- **Composition tendency**: Alternate between full-frame work with a single line of type in a quiet corner, and sparse type-only pages with generous empty ink around a short statement. Keep the framing of the work consistent — the same caption position, the same attribution scale — while the pace varies between quiet and full.
- **Cross-page continuity**: The shelf-and-crescent mark recurs at the same small scale in the same relative position on the creative pages; caption position and attribution scale never move; the hero artwork recurs three times as derived backdrops so the deck feels like one body of work. The two paper-field pages deliberately break all of it.
- **Spacing posture**: Variable — extremely open through the creative arc, tighter and plainer on production and close.
- **Spacing anchors**: page margin 72 px; block gap 32 px; column gutter 40 px; corner radius 0 px (the phone-screen mockup's rounded corners are a property of the depicted device, not a deck radius); body leading 1.45.

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| `tabler-outline/printer` | Print and out-of-home channel class on the production page |
| `tabler-outline/device-mobile` | Social and owned-digital channel class |
| `tabler-outline/building-store` | In-store and shop-window channel class |
| `tabler-outline/calendar-event` | Event and programming channel class |
| `tabler-outline/bookmark` | Take-away print collateral class |
| `tabler-outline/book` | Product and catalogue class |
| `tabler-outline/bulb` | Light and evening-programme class |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P02 | chart | grouped_bar_chart | Compare average daily minutes spent reading against minutes spent watching television, by age band, so the gap and its shape are visible at once |
| P12 | table | record_table | Hold the production scope as flat records — one deliverable per row against stable format, quantity, lead-time, rights and owner fields |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| hero_night_shelf.jpg | 1920×1072 | 43:24 | The campaign's hero execution artwork — one lit shelf in a dark room | Illustration | Full-frame field on the hero page with a single line of type in the lower quiet zone; a tight vertical detail crop of the same file carries the cover | adaptive | ai | Generated | A single narrow bookshelf in an otherwise dark room, lit by one shaded lamp standing just out of frame at the left; six or seven books stand and one lies open; a window behind shows a cold blue night with fog; the right two-thirds of the frame fall away into unlit dark and must stay quiet enough to hold type. Warm light pools on the shelf edge and the open page; everything outside the pool is deep ink. | none | hero_page |
| poster_artwork.jpg | 1288×1920 | 53:79 | The campaign's street-poster artwork, shown inside a pasted poster and inside the shop window | Illustration | Sits inside a 2:3 poster crop on the range page and again, smaller and angled by context, in the window on the environment page | adaptive | ai | Generated | A printed street poster for a night reading campaign: flat two-colour ink on cream stock, a stencil-cut crescent resting on a horizontal rule occupying the upper half, a solid block of unbroken cream in the lower third left completely empty for type, visible halftone where the two inks meet, slight misregistration. No text anywhere. | none | local |
| social_artwork.jpg | 1920×1920 | 1:1 | The campaign's social post artwork, shown inside a phone screen | Illustration | Fills a rounded phone-screen crop on the range page; the empty lower band is where the native caption sits | adaptive | ai | Generated | A square social post for the same night reading campaign: the same flat two-colour printed ink language, a crescent and a shelf rule composed off-centre to the upper right, a wide empty cream band across the bottom third, halftone texture in the transition, slight misregistration. No text anywhere. | none | local |
| instore_scene.jpg | 1920×1072 | 43:24 | Environment and context — the shop window at night seen from the pavement at honest scale | Photo | Full-frame environmental field; the window occupies the right half at a realistic standing eye level, leaving the wet pavement at the left to carry type | adaptive | ai | Generated | A small independent bookshop window photographed at night from the pavement across a narrow street, at ordinary standing eye level and true scale — the window is roughly one and a half metres wide, warm light inside, books on a low display table, a blank cream poster pasted inside the glass at the right edge, wet pavement reflecting the light in the foreground, fog softening the street lamps behind the camera. Nothing in the frame contains readable text. | none | local |
| element_book.png | 600×464 | 674:521 | Campaign element — book | Illustration | Small element resting on the shelf rule in the identity system | no-crop | slice | Generated | Derived from `elements_sheet.png`; cell 1 | none | local |
| element_lamp.png | 399×627 | 7:11 | Campaign element — lamp | Illustration | The light in the identity system and in the take-away collateral | no-crop | slice | Generated | Derived from `elements_sheet.png`; cell 2 | none | local |
| element_moon.png | 483×538 | 483:538 | Campaign element — crescent | Illustration | The crescent that sits on the shelf rule wherever the element family is shown rather than drawn | no-crop | slice | Generated | Derived from `elements_sheet.png`; cell 3 | none | local |
| element_mug.png | 543×496 | 543:496 | Campaign element — mug | Illustration | Tone-and-craft page: the register of the finished work | no-crop | slice | Generated | Derived from `elements_sheet.png`; cell 4 | none | local |
| element_bookmark.png | 236×634 | 118:317 | Campaign element — printed bookmark | Illustration | The take-away carrier on the range page, shown at its own narrow ratio | no-crop | slice | Generated | Derived from `elements_sheet.png`; cell 5 | none | local |
| element_fern.png | 471×656 | 471:656 | Campaign element — fern frond, the shop's own signature | Illustration | Marks the surfaces the shop itself owns, on the identity and production pages | no-crop | slice | Generated | Derived from `elements_sheet.png`; cell 6 | none | local |
| hero_grey.jpg | 1920×1072 | 43:24 | Desaturated, dimmed backdrop for the strategic-thought page | Illustration | Recedes to a quiet field behind a single short statement | adaptive | ai | Generated | Derived from `hero_night_shelf.jpg`; treatment=grayscale + brightness reduction | none | local |
| hero_dim.jpg | 1920×1072 | 43:24 | Dimmed backdrop for the identity-exploration page | Illustration | Darkened but still recognisable, so the identity system is seen sitting on the work rather than on a swatch board | adaptive | ai | Generated | Derived from `hero_night_shelf.jpg`; treatment=brightness reduction | none | local |
| hero_blur.jpg | 1920×1072 | 43:24 | Blurred backdrop for the tone-and-craft page | Illustration | Out of focus behind foreground material, so the page reads as texture and register rather than as another execution | adaptive | ai | Generated | Derived from `hero_night_shelf.jpg`; treatment=blur | none | local |

## IX. Content Outline

### Part 1: The truth the work rests on

#### Slide 01 - Cover

- **Audience move**: Expects an agency deck → is already standing in the campaign's world, and knows within two seconds that this is an example pitch for a client that does not exist
- **Relationships**: none — the campaign name, the promise line, the client-and-season line and the fictional-example marker are four independent units of the same lockup
- **Composition**: A tight vertical detail crop of the hero artwork holds the left third; the rest is unbroken night ink carrying the campaign name at cover scale, the promise line beneath it, and one small footer line
- **Title**: The Night Shelf
- **Core message**: Fog & Fern Books can own the last hour of the day.
- **Content**: campaign name "The Night Shelf" · promise line "Give the night back to reading." · client and season "Fog & Fern Books — late autumn campaign" · marker "Example pitch. Fog & Fern Books, its figures and this campaign are fictional; all research cited is real."
- **Cover impact**: The hook is the lit shelf detail against a page of unbroken dark — one light in a dark room, before a single word of argument. The composition around it is a Reference.
- **Images**: `hero_night_shelf.jpg`, used as a narrow vertical detail crop only; the full frame is withheld until Slide 07
- **Motion suggestion**: The dark settles first, then the light arrives, then the name — the reverse of the order the audience will read them in
- **page_rhythm**: anchor

#### Slide 02 - There are sixteen minutes left

- **Audience move**: Believes their customers simply read less than they used to → sees that reading is not losing a preference contest, it is losing a time contest, and by how much
- **Relationships**: contrast between two measured daily behaviours (reading for personal interest, watching television) across an ordered set of age bands; the youngest band and the oldest band sit at opposite ends of the same contrast
- **Composition**: Two statement numerals share the upper band as a direct contrast; the chart occupies the lower two-thirds at statement scale with its meaning annotated on it rather than in a legend far away
- **Title**: There are sixteen minutes left
- **Core message**: The average day now holds sixteen minutes of reading and two hours thirty-seven of television — and the gap is widest among the youngest readers.
- **Content**: two contrasted numerals "16 min" reading / "2 h 37 m" television, both per day, average adult · one line naming the instrument and year · grouped bars, minutes per day, reading against television, six age bands · one annotation on the youngest band: ten minutes against one hour forty-six · source line
- **Visualization**: `daily-minutes-by-age` — grouped bars, six age-band categories, two series (reading for personal interest; watching television), values in minutes per day converted from published hours. Native-ready: `daily-minutes-by-age`=yes
- **Fact IDs**: F005, F006
- **page_rhythm**: dense

#### Slide 03 - The last hour is already taken

- **Audience move**: Assumes the missing time is spread across the whole day → understands that the only hour still available is the one before sleep, and that a screen is already in it
- **Relationships**: link from a prevalence fact (screens in bed are the normal case) to its measured cost (each additional hour of it), and a contrast with the alternative behaviour measured in a randomised trial
- **Composition**: One dark frame with three short evidence lines stacked at wide intervals down the left, each with its own small numeral; the crescent element sits alone in the upper right
- **Title**: The last hour is already taken
- **Core message**: Half of all adults are on a screen in bed every day, each extra hour of it costs twenty-four minutes of sleep, and a book in bed is the one thing measured to do the opposite.
- **Content**: half of adults use a screen in bed every day, a third more most days · each additional hour of screen time after getting into bed: 59% higher odds of insomnia, 24 minutes less sleep · in a randomised trial, 42% of people who read a book in bed reported better sleep against 28% who did not · each line carries its own source and sample
- **Images**: `element_moon.png`
- **Fact IDs**: F010, F011, F012
- **page_rhythm**: dense

#### Slide 04 - What the work has to do

- **Audience move**: Sees a general cultural problem → sees the shop's specific, constrained job for one season
- **Relationships**: parent task with three subordinate constraints that make it hard; the constraints are parallel to each other
- **Composition**: A short task statement at lead scale occupying the upper left, three constraints as widely spaced parallel lines beneath, everything else empty ink
- **Title**: What the work has to do
- **Core message**: Make one independent bookshop the place a reader thinks of at nine in the evening — with no media budget, one season, and five people.
- **Content**: the task in one sentence · constraint: no paid media beyond the shop's own street frontage and channels · constraint: one season, six weeks from first paste-up to the last event · constraint: five people, all of whom already work full shifts · marker line: shop scale, staffing and budget are illustrative and belong to this fictional client
- **Data class**: scenario — the six-week window, the five-person team and the no-paid-media constraint are invented for this example client
- **page_rhythm**: breathing

#### Slide 05 - Reading is not competing with the day

- **Audience move**: Thinks the shop must win attention back from everything → accepts that the whole campaign can aim at one hour, which makes it winnable
- **Relationships**: link — the audience truth on the two previous pages narrows to a single addressable moment, which is the bridge to the creative territory
- **Composition**: A desaturated, dimmed frame of the hero artwork behind one short statement set at idea scale slightly above centre; nothing else on the page
- **Title**: Reading is not competing with the day
- **Core message**: It is competing with the last hour — so stop arguing for reading and start owning bedtime.
- **Content**: one statement, three clauses, set for spoken rhythm with authored line breaks · one supporting half-line naming what that changes about where the work has to appear
- **Images**: `hero_grey.jpg` as a receded field
- **page_rhythm**: breathing

### Part 2: The idea and the work

#### Slide 06 - The idea

- **Audience move**: Has followed an argument → receives the idea in one line they can repeat exactly, with nothing else on the page to dilute it
- **Relationships**: none — one line stands alone
- **Composition**: The most restrained page in the deck. The shelf-and-crescent mark sits small and centred high; the line sits beneath it at idea scale with authored breaks; the rest of the page is empty night ink. No caption, no attribution, no number.
- **Title**: The Night Shelf
- **Core message**: The last hour belongs to a book.
- **Content**: the campaign line "The last hour belongs to a book." set on three lines for spoken rhythm · one half-line beneath, at annotation scale, naming what the shelf is: the books chosen for the hour before sleep, and a shop that stays open into it
- **Motion suggestion**: The mark arrives first and comes to rest; the line then appears one clause at a time in the order it is spoken; nothing else moves
- **page_rhythm**: anchor

#### Slide 07 - Hero execution

- **Audience move**: Has heard the idea → sees it made, at production quality, and stops needing it explained
- **Relationships**: none — one piece of work occupies the page
- **Composition**: Full frame, edge to edge, no chrome, no page furniture, no explanation. The campaign line sits inside the work in the dark right-hand zone over a soft gradient scrim; the mark sits small beneath it. Nothing else.
- **Title**: (none on the page — the work carries it)
- **Core message**: The campaign, made.
- **Content**: the campaign line placed inside the artwork as the work's own type · the mark at small scale beneath it
- **Images**: `hero_night_shelf.jpg` at full frame; this is the first time the whole artwork is shown
- **Motion suggestion**: The frame is already present; only the light and then the line resolve — the work must not appear to assemble itself
- **page_rhythm**: anchor

#### Slide 08 - It runs everywhere the hour is spent

- **Audience move**: Has seen one beautiful execution → believes the idea is a platform, because four genuinely different surfaces each carry it without repeating the same picture
- **Relationships**: membership — four executions belong to one campaign; they differ in surface, shape and moment rather than in colourway, and they are sequenced from public street to private hand
- **Composition**: Four carriers of visibly different shape and ratio across one field, sequenced left to right and public to private: a pasted street poster at 2:3, a phone screen with rounded corners, a horizontal shop-window lightbox band, and a narrow printed bookmark. Each is readable on its own; each carries its own one-line caption at annotation scale in the same position relative to its own frame.
- **Title**: It runs everywhere the hour is spent
- **Core message**: One idea, four surfaces, four different moments of the same evening — none of them a recolour of another.
- **Content**: street poster — the walk home, 2:3, pasted · phone — the moment the screen is already in hand, square post · shop window — the lightbox band the shop already owns, wide · bookmark — the object that leaves with the book · caption per carrier naming the moment, not the format · marker line: all four are mockups of proposed executions
- **Images**: `poster_artwork.jpg` inside the poster crop, `social_artwork.jpg` inside the phone crop, `hero_night_shelf.jpg` re-cropped into the wide lightbox band, `element_bookmark.png` as the printed bookmark. How they relate: the hero artwork travels from the previous page's full frame into the lightbox band here, so the same picture is seen first as art and then as media.
- **Motion suggestion**: The lightbox band is continuous from the previous page and does not re-enter; the other three carriers arrive in the public-to-private order they are read in
- **page_rhythm**: dense

#### Slide 09 - The identity, in use

- **Audience move**: Sees a campaign → sees a system the shop could keep using after the season ends
- **Relationships**: membership — one type voice, one palette in which each colour has a single job, and one mark, shown working together on real surfaces rather than as separate specimens
- **Composition**: A dimmed frame of the hero artwork behind; on it, three bands showing the system in use — the type voice set as it appears on the poster, the palette shown as the four jobs it does with each colour labelled by its job, and the mark shown at three real sizes down to the bookmark's
- **Title**: The identity, in use
- **Core message**: Four colours, each with one job, one type voice and one mark — enough to run the shop's own posters next year without us.
- **Content**: type voice — a bookish serif for everything the campaign says, a quiet sans for everything the shop has to add later · palette by job — night ink is the ground, lamplight is the only light and is never used for type, paper cream is everything a reader touches, fern is only ever the shop's own signature · the mark at poster, window and bookmark scale · one rule: ember appears only where a screen is being referred to
- **Images**: `hero_dim.jpg` as a receded field; `element_fern.png` and `element_lamp.png` shown at working scale
- **page_rhythm**: dense

#### Slide 10 - Tone and craft

- **Audience move**: Understands the system → knows how the finished work is meant to feel and how it will be made
- **Relationships**: parent register with three subordinate craft decisions, parallel to each other
- **Composition**: A blurred frame of the hero artwork behind foreground material shown sharp; one campaign word carried at display scale with a soft warm glow, the craft notes small beneath at annotation scale
- **Title**: Tone and craft
- **Core message**: Warm, unhurried and physically printed — the campaign should feel like something the shop made, not something it bought.
- **Content**: printed on uncoated cream stock, two inks, no laminate · photographed at night on location in the shop, not lit as a studio set · every line written to be read aloud in one breath · one campaign word carried at display scale as the tone sample
- **Images**: `hero_blur.jpg` as an out-of-focus field; `element_mug.png` sharp in the foreground
- **Motion suggestion**: The mark carries forward into the environment page rather than leaving with this one
- **page_rhythm**: breathing

#### Slide 11 - Where the audience meets it

- **Audience move**: Has seen the work on white → sees it at real size in a real street and can judge whether it actually reads at seven in the evening
- **Relationships**: none — one environment, shown honestly
- **Composition**: Full-frame environmental photograph at honest standing eye level with the poster in the window at true scale; a single caption at annotation scale in the wet-pavement quiet zone over a gradient scrim; a small honest-scale note
- **Title**: Where the audience meets it
- **Core message**: At real size, from the far pavement, the poster still reads — which is the only test that matters for a shop with no media budget.
- **Content**: one caption naming the moment and the distance · marker line: mockup, shown at the window's real dimensions and at ordinary eye level; no placement is implied that the shop does not already own
- **Images**: `instore_scene.jpg` full frame with `poster_artwork.jpg` composited into the window at its true relative size
- **page_rhythm**: anchor

### Part 3: Reality

#### Slide 12 - What it takes to make

- **Audience move**: Is persuaded → sees exactly what production, timing, rights and people the campaign actually needs, in a register that is plainly not a sales page
- **Relationships**: membership — seven deliverables belong to one production scope; each is a flat record described by the same stable fields, and their lead times are ordered against one six-week window
- **Composition**: Paper field, no imagery, no mark, plain rules. Title at page scale, the grid beneath it occupying most of the page, a channel-class icon row above it, and the illustrative-figures marker beneath it.
- **Title**: What it takes to make
- **Core message**: Six weeks, seven deliverables, two print suppliers and no paid media — this is buildable by five people.
- **Content**: deliverables as rows — street poster, window lightbox panel, social film and stills, printed bookmark, shelf talker, evening event series, local radio read · fields — format, quantity, lead time, rights window, owner · a marker beneath: all quantities, lead times and owners are illustrative for this fictional client; nothing here is a quotation
- **Visualization**: `production-scope` — a flat record grid, seven rows, five stable columns. Native-ready: `production-scope`=yes
- **Data class**: scenario — every quantity, lead time, rights window and owner on this page is invented for the example client
- **page_rhythm**: dense

#### Slide 13 - How you will know it worked

- **Audience move**: Is ready to decide → knows the single observable test of success, the decision being asked for, and where every number in the deck came from
- **Relationships**: link — one measurable outcome follows from the idea; the sources supporting the argument are listed beneath it as an ordered independent set
- **Composition**: Paper field. The measurement statement at title scale in the upper half with its one observable test; the source list beneath at footnote scale as a plain ordered column; the fictional-example statement last.
- **Title**: How you will know it worked
- **Core message**: If the shop is busier between eight and ten in the evening in week six than in week one, the idea worked — approve it for late autumn.
- **Content**: the one observable test, stated as a comparison the shop can make itself without any measurement it does not already have · the decision being asked for · sources, each as a live link — Pew Research Center on book reading; US Bureau of Labor Statistics American Time Use Survey; National Endowment for the Arts SPPA; UK National Literacy Trust; Frontiers in Psychiatry on screen use after going to bed; American Academy of Sleep Medicine; The People's Trial in Trials; American Booksellers Association · closing statement: Fog & Fern Books, its figures, its constraints and this campaign are fictional and exist only as an example; every research finding cited is real and linked above
- **Closing impact**: The binding takeaway is the single self-measurable test plus the approval ask; the composition is a Reference
- **Fact IDs**: F001, F005, F007, F008, F010, F011, F012, F013
- **page_rhythm**: anchor

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: One short spoken passage per page grounded in that page's final SVG — what the presenter says while the page is on screen, in the order the page is read. Every page whose content includes an external number restates its source aloud; every page carrying invented client, production or commercial figures says plainly that they are illustrative and that Fog & Fern Books is a fictional client. Notes carry the explanation the creative pages deliberately keep off the slide. No note invents a fact that is not on the page or in the imported facts file.
- **Total duration**: about 18–20 minutes for 13 pages, weighted toward the idea and range pages
- **Notes style**: conversational — a person talking in a shop, not a script being read
- **Presentation purpose**: Persuade the team to feel the idea and believe its audience truth, then align them on scope and obtain approval for late autumn

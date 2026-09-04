<!-- ppt-master-schema: design-spec/v1 -->
# Brutalism Field Guide - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | brutalism_field_guide |
| Canvas Format | ppt169, 1280 × 720 px |
| Page Count | 16 |
| Primary Language | en |
| Target Audience | English-reading adults with a general interest in architecture and cities — they recognise the concrete buildings but do not know where the style came from, what its architects believed, or why it was hated and then loved again |
| Communication Intent | Explain first — make the origin of the word, the material logic, and the ethic traceable; then inform completely about the figures, buildings and the demolition-versus-listing record; finally reframe the reader's judgement of the style without arguing them into liking it |
| Desired Audience Outcome | The reader can say where "new brutalism" came from, name the material logic behind béton brut, name three canonical buildings and their architects, explain both the backlash and the revival, and look at a concrete building with an informed rather than a reflexive reaction |
| Core Message / Ask / Action | Brutalism was an ethic before it was a look: show the structure, show the material as found — and that honesty is exactly what made it both hated and, fifty years on, worth saving |
| Delivery Context | Reader-led. A self-standing English briefing read on screen at desk distance; no live presenter. Secondary use as a leave-behind reference for an architecture reading group |
| Artifact Afterlife | Reference and reuse — kept, re-read, and shared; every claim traceable to the single cited source page |
| Reading Mode | text |
| Content Strategy | Balanced. Re-architect the encyclopedia article into a story arc — origin, ethic, buildings, reckoning, revival — while keeping every fact, name, date and quotation exactly as the source states them. Add no fact the source does not carry; where a figure is missing, say so on the page rather than estimating |
| Design Style | Brutalist editorial newspaper carrying a narrative arc — a field guide printed on newsprint: masthead numerals, irregular column widths, heavy rules, one inverted focal cell per spread, halftone documentary photography |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — workflow default (proactive Stage-2 value `true`) |
| Custom Animations | enabled — explicit user instruction: at least two Morph pairs plus entrance motion |
| Narration Audio | disabled — final Stage-2 proactive policy |
| Created Date | 2026-09-04 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | ppt169 |
| Dimensions | 1280 × 720 px |
| viewBox | `0 0 1280 720` |
| Margins | 48 px left/right, 40 px top, 44 px bottom |
| Content Area | x 48–1232, y 40–676 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Visual style**: custom
- **Mode References**: narrative
- **Mode Behavior**: Run one arc across five parts — a house in Uppsala gets a name (situation), the name hardens into an ethic (rising stake), the ethic becomes hundreds of public buildings (payoff), the public turns on them and the wrecking balls arrive (reversal), then the style is listed, reprinted and rebuilt (resolution). Titles read as beats that advance the story, never as topic labels. Each part opens on a visibly reset page and the two evidence tables land as the story's factual floor, not as an appendix.
- **Visual Style References**: brutalist
- **Visual Style Behavior**: Newsprint field guide. Irregular two-, three-, and four-column measures on one 12-column ruleset, mixed within a page; ink hairline column dividers and 6–10 px full-bleed rule bars slicing sections; a masthead numeral set at 120 px that crosses column rules and carries the page identity; one grid cell per page inverted to solid ink with paper-light type as the focal cell; a single rotated stamp box (2–4°) breaking the grid at one deliberate point on the anchor pages; `rx="0"` everywhere, no shadow, no gradient except a halftone `<pattern>` dot field used as printed texture. Photography enters only as high-contrast duotone or halftone, cropped hard into a ruled box. Colour is punctuation — the spot red appears at most twice per page, on a masthead rule or one key figure.
- **Theme**: A printed field guide to raw concrete: the page is built the way the buildings were — structure exposed, grid visible, nothing smoothed. Recurring motif: the **masthead numeral**, an oversized page number set in the display face, crossing the top rule; its continuity job is to number the field guide like plates in a printed manual, and it varies in position and scale by page rhythm.
- **Tone**: Reportorial, dry, unsentimental — a critic's field notes rather than an advocate's brochure.

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F2F0EA | Newsprint paper field, every page |
| Secondary background | #E2DFD5 | Grey stock for boxed columns, sidebars, table banding |
| Primary | #14110F | Ink — rules, masthead numerals, headline type, inverted focal cells |
| Accent | #C8331E | Spot red punctuation — one masthead rule, key figure, or stamp box per page |
| Secondary accent | #6E6A62 | Weathered concrete grey — halftone duotone shadow, secondary rules, quiet fills |
| Body text | #1C1A17 | Column body type on paper |
| Secondary text | #55514A | Captions, annotations, source lines, footnotes |
| Divider | #9A958B | Hairline column dividers, table rules lighter than the section bars |

Additional anchored neutral roles: `surface` #E2DFD5 (boxed column lift, identical to secondary background by design), `grid` #C9C5BA (halftone dot field and table hairlines), `scrim` #14110F at plan-level meaning "ink scrim under type over a photograph", `block-shade` #D8D4C8 (one step off the paper field for print-fill blocks).

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | Display sans, poster-black weight; the headline collision this style needs | Arial Black | — | Arial Black |
| Body | Transitional serif with lining figures; column body at small size, tight leading | Cambria | — | Cambria |
| Cover title | Poster-black at cover scale — the display word that opens the guide | Arial Black | — | Arial Black |
| Display numeral | The masthead numeral crossing the top rule on every page | Arial Black | — | Arial Black |
| Subtitle | Serif, not black — a quiet second line under a black headline | Cambria | — | Cambria |
| Lead | Serif at reading weight — the page's primary claim | Cambria | — | Cambria |
| Data | Monospace figures, table columns, years, heights, counts | Consolas | — | Consolas |
| Annotation | Monospace small — captions, credits, source lines | Consolas | — | Consolas |
| Table body | Monospace agate — the cell text of the two full-width record tables | Consolas | — | Consolas |
| Footnote | Monospace smallest — page numbers and licence lines | Consolas | — | Consolas |

- **Title stack**: Arial Black
- **Body stack**: Cambria
- **Cover title stack**: Arial Black
- **Display numeral stack**: Arial Black
- **Subtitle stack**: Cambria
- **Lead stack**: Cambria
- **Data stack**: Consolas
- **Annotation stack**: Consolas
- **Table body stack**: Consolas
- **Footnote stack**: Consolas
- **Role rationale**: `Cover title` and `Display numeral` separate the 80 px cover word and the 120 px masthead numeral from ordinary page titles so neither oversized carrier depends on the Executor display exception; `Subtitle` and `Lead` are pinned to the serif so a black headline is never followed by a second black line; `Data`, `Annotation`, and `Footnote` give the two native tables, every year, height and count, the photo credits and the page numbers a monospace column the serif body cannot supply; `Table body` is the agate cell size the two full-width record tables need to carry every named architect and building without dropping one, and it recurs on both table pages.

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 20 |
| Title | 36 |
| Subtitle | 26 |
| Annotation | 16 |
| Cover title | 80 |
| Lead | 24 |
| Display numeral | 120 |
| Data | 22 |
| Table body | 16 |
| Footnote | 12 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: Attention enters at the masthead numeral or the top rule bar, drops to the headline set flush left, then reads down the widest column; the inverted focal cell catches the eye once per page and holds the page's single hardest fact.
- **Composition tendency**: Irregular column measures over a 12-column ruleset — a page may run 5+7, 4+4+4, 3+6+3, or 8+4 — never the same split on adjacent pages. Full-bleed rule bars mark section changes. Photographs are cropped into ruled boxes that sit on column lines, never floated.
- **Cross-page continuity**: The masthead numeral recurs on every page and is the deck's continuity carrier; the top rule bar recurs at a stable weight; the inverted focal cell recurs once per page and moves. Part openers reset visibly by giving the numeral the full left column.
- **Spacing posture**: Dense by default with deliberate breathing at the two part-reset beats and the closing.
- **Spacing anchors**: page margin 48 px; block gap 24 px; column gutter 20 px; corner radius 0 px; body leading 30 px.

## VI. Icon Usage Specification

- **Primary bundled library**: chunk-filled

| Icon Path | Suitable Scenarios |
| --- | --- |
| chunk-filled/building | A named building, structure, or canonical work |
| chunk-filled/block-quote | A pull quote lifted from an architect or critic |
| chunk-filled/calendar | A dated event in the timeline of the style |
| chunk-filled/trash | Demolition and loss |
| chunk-filled/bookmark | Listing, protection, preservation |
| chunk-filled/globe | International spread of the style |
| chunk-filled/hammer | Material, construction, and fabric |
| chunk-filled/user | A named architect or critic |
| chunk-filled/book | A published book, essay, or citation |
| chunk-filled/link | An external source reference |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P09 | table | record_table | One row per country with its named brutalist architects and the works the source attributes to them |
| P13 | table | record_table | One row per building with its architect, year of loss or listing, and the source-stated outcome |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| src_beton_brut.jpg | 5358×3572 | 1.50 | Cover field — the raw concrete surface the whole guide is about | Source | not placed | adaptive | web | Sourced | Board-marked or shuttered raw concrete façade of a brutalist building, frontal or steeply angled, strong directional daylight raking the surface so the formwork grain reads; quiet upper-left region for the masthead; no people, no sky-dominant framing | none | — |
| cover_beton_brut_duo.png | 1000×667 | 1.50 | Cover — the concrete field, printed | image | Cropped hard into a ruled square box holding the right third of the cover while the display word runs across it; the photograph is the page's only tonal mass | adaptive | web | Sourced | Derived from src_beton_brut.jpg; treatment=contrast 1.35 then duotone #14110F/#F2F0EA then fit 1000x1000 | none | — |
| src_boston_city_hall.jpg | 4080×3060 | 1.33 | Evidence for the page on exposing a building's inner workings | Source | not placed | no-crop | web | Sourced | Boston City Hall, Boston, USA — exterior showing the projecting upper volumes over the recessed base, so the differently shaped projections that mark the special rooms behind them are legible; daylight, whole building in frame | none | — |
| boston_city_hall_half.png | 900×675 | 1.33 | The building whose outside announces its inside | image | Sits in a ruled box on the narrow column beside the argument, with the projecting volumes aligned to a column rule so the page grid and the building's grid rhyme | no-crop | web | Sourced | Derived from src_boston_city_hall.jpg; treatment=contrast 1.4 then duotone #14110F/#E2DFD5 then fit 900x900 | none | — |
| src_demolition.jpg | 6000×4000 | 1.50 | The reckoning — a brutalist block coming down | Source | not placed | adaptive | web | Sourced | A concrete tower block or slab mid-demolition or partly collapsed, dust and exposed floor plates visible; documentary, unromantic, wide enough to read the structure being destroyed | none | — |
| demolition_mono.png | 1000×667 | 1.50 | The page where the public verdict becomes physical | image | Full-width band across the lower half of the page, cropped to a letterbox so the falling structure runs against the horizontal rules; the inverted focal cell sits directly above it | adaptive | web | Sourced | Derived from src_demolition.jpg; treatment=contrast 1.5 then duotone #14110F/#C9C5BA then fit 1000x1000 | none | — |
| src_ningbo_museum.jpg | 5472×3648 | 1.50 | The revival — neobrutalism built | Source | not placed | no-crop | web | Sourced | Ningbo Museum, Ningbo, China, by Wang Shu — exterior wall showing the monumental mass and its textured recycled surface; daylight, whole façade section in frame | none | — |
| ningbo_museum_duo.png | 900×600 | 1.50 | Proof the ethic outlived the movement | image | Ruled box on the right column facing the neobrutalism argument, cropped to the wall itself so the surface texture, not the skyline, is what the reader sees | no-crop | web | Sourced | Derived from src_ningbo_museum.jpg; treatment=contrast 1.3 then duotone #14110F/#E2DFD5 then fit 900x900 | none | — |

## IX. Content Outline

### Part 1: The word

#### Slide 01 - Cover: concrete, honest, unforgiving

- **Audience move**: Sees concrete buildings as an ugly accident of the past → is told they were a deliberate ethic and wants to know whose
- **Relationships**: Title phrase, the style's active years, and the source claim that the buildings are known for showing bare material over decoration — the years and the claim both qualify the title; no order among them
- **Composition**: Masthead rule bar across the top with the guide title as a printed banner; the display word set at cover scale flush left across the left two-thirds, crossing into the duotone concrete box on the right; active-years line set in monospace under the display word
- **Cover impact**: The hook is the source's own definition — buildings known for showing the bare building materials and structural elements over decorative design — printed as a masthead claim, not a subtitle
- **Title**: Concrete, Honest, Unforgiving
- **Core message**: Brutalism is an architectural style that emerged in 1950s Britain and made a virtue of showing exactly what a building is made of
- **Content**:
  - Display word / cover phrase: CONCRETE · HONEST · UNFORGIVING
  - Full title line: Brutalist architecture — a field guide
  - Active years and reach, from the source infobox: 1950s – early 1980s; International
  - Masthead claim: minimalist construction showcasing the bare building materials and structural elements over decorative design
- **Images**: cover_beton_brut_duo.png
- **Motion suggestion**: The masthead rule bar and the page numeral are the objects that persist into slide 02; the cover word is the only element that should arrive on its own

#### Slide 02 - It started with a brick house in Uppsala

- **Audience move**: Assumes brutalism began with a concrete tower → learns it was named after a modest Swedish brick house
- **Relationships**: Villa Göth (the object) is the parent of the three "as found" features the source lists — visible I-beams over windows, exposed brick inside and out, poured concrete showing the board pattern of its forms; the naming event links Hans Asplund to the house; Edman and Holm link to it as its designers
- **Composition**: The year 1950 set as the masthead numeral filling the left column; the naming account in the wide centre column; the three "as found" features in a ruled three-cell strip along the bottom, one cell inverted
- **Title**: 1950: a name for a house in Kåbo
- **Core message**: The word arrived before the concrete — Swedish architect Hans Asplund coined *nybrutalism* for a brick house, not a monument
- **Content**:
  - The term *nybrutalism* (new brutalism) was coined by Swedish architect Hans Asplund to describe Villa Göth, a modern brick home in Uppsala
  - Villa Göth was designed in January 1950 by Bengt Edman and Lennart Holm, contemporaries of Asplund
  - The house shows the "as found" approach later at the core of brutalism: visible I-beams over windows · exposed brick inside and out · poured concrete in several rooms where the tongue-and-groove pattern of the form boards can still be seen
  - Villa Göth was listed as historically significant by the Uppsala county administrative board on 3 March 1995
- **Motion suggestion**: The masthead numeral is the continuity carrier from the cover into this page and out of it again — the year is what changes, the numeral is what stays

#### Slide 03 - The word spreads like wildfire

- **Audience move**: Has a Swedish origin story → sees how the term crossed to Britain and got attached to real buildings within five years
- **Relationships**: Four dated events in strict order — 1950 English architects hear the term in Sweden, 1953 first publication, 1954 Hunstanton completed, 1955 Sugden House completed and Banham's essay; each later event depends on the one before it
- **Composition**: A single spine of four dated entries running down the page in irregular column widths, each entry's year in the data face and hanging left of the column rule; the 1953 quotation set as a boxed pull-quote breaking the spine
- **Title**: Then it spread like wildfire
- **Core message**: In five years the term crossed from a Swedish house to the first building in the world its own architects called new brutalist
- **Content**:
  - Summer 1950 — visiting English architects including Michael Ventris, Oliver Cox and Graeme Shankland pick the term up in Sweden, where it "spread like wildfire, and [was] subsequently adopted by a certain faction of young British architects"
  - 1953 — first published use of "new brutalism": Alison Smithson describes the unbuilt Soho house in the November issue of *Architectural Design*, writing "It is our intention in this building to have the structure exposed entirely, without interior finishes wherever practicable"
  - 1954 — the Smithsons' Hunstanton School completed in Norfolk: the first completed building in the world to carry the title "new brutalist" by its architects, and described at the time as "the most truly modern building in England"
  - 1955 — the Smithsons' Sugden House completed in Watford; Hunstanton was likely inspired by Mies van der Rohe's 1946 Alumni Memorial Hall at the Illinois Institute of Technology, Chicago
- **Motion suggestion**: The four dated entries should arrive in their chronological order, not together — the sequence is the argument

#### Slide 04 - Béton brut: the critic names the material

- **Audience move**: Knows the term travelled → learns where the concrete association actually came from, and that it was a critic's doing
- **Relationships**: Banham's 1955 essay and his 1966 book are ordered; both link "new brutalism" to the French phrases *béton brut* and *art brut*; Le Corbusier's own description of his concrete work is the source Banham credits, making it the parent of the whole association
- **Composition**: The two French phrases set enormous across the upper half in the display face, translations in the data face beneath them; Banham's Le Corbusier sentence in an inverted focal cell spanning the lower right; publication details in a narrow left column
- **Title**: Raw concrete, raw art
- **Core message**: The concrete in brutalism came from a critic reaching for Le Corbusier's own words — *béton brut*, raw concrete
- **Content**:
  - Reyner Banham, British architectural historian, used "new brutalism" to identify both an ethic and an aesthetic style in his 1955 essay *The New Brutalism*, and named Hunstanton and the Soho house as "the reference by which The New Brutalism in architecture may be defined"
  - Banham associated the term with *art brut* ("raw art") and *béton brut* ("raw concrete")
  - In his 1966 book *The New Brutalism: Ethic or Aesthetic?* he wrote that "if there is one single verbal formula that has made the concept of Brutalism admissible in most of the world's Western languages, it is that Le Corbusier himself described that concrete work as 'béton-brut'"
  - Banham also said the words "The New Brutalism" were already circulating and "had acquired some depth of meaning through things said and done, over and above the widely recognised connection with *béton brut*"
- **Motion suggestion**: *béton brut* is the object that should carry from this page's display setting into the next page's argument; the focal cell arrives last

### Part 2: The ethic

#### Slide 05 - An ethic, not an aesthetic

- **Audience move**: Thinks brutalism is a look → learns its own architects insisted it was a moral position about materials, and can state Banham's three tests
- **Relationships**: The Smithsons' and Voelcker's statements are parallel claims for the same position; Banham's three numbered terms are an ordered membership set under his attempt to codify the movement, with the "image" criterion added alongside
- **Composition**: Two unequal columns — the quotations stacked left at column width, Banham's three numbered terms in a ruled three-row block on the right with the row numerals in the display face; the "an ethic, not an aesthetic" phrase inverted as the focal cell across the bottom rule
- **Title**: "An ethic, not an aesthetic"
- **Core message**: Brutalism's own architects defined it as honesty about material, and its critic turned that honesty into three testable conditions
- **Content**:
  - New brutalism is not only a style but a philosophical approach — a striving to create simple, honest, functional buildings that accommodate their purpose, inhabitants and location
  - Peter Smithson: brutalism's core was reverence for materials expressed honestly — "Brutalism is not concerned with the material as such but rather the quality of material", and "the seeing of materials for what they were: the woodness of the wood; the sandiness of sand"
  - Architect John Voelcker said the new brutalism "cannot be understood through stylistic analysis, although some day a comprehensible style might emerge", supporting the Smithsons' description of the movement as "an ethic, not an aesthetic"
  - Banham held the phrase existed as both an attitude to design and a label for the architecture, and that it "eludes precise description, while remaining a living force"; he insisted a brutalist structure must satisfy: 1, formal legibility of plan; 2, clear exhibition of structure; 3, valuation of materials for their inherent qualities "as found" — with the aesthetic "image", the coherence of the building as a visual entity, also important
  - Stylistically it was a strict, modernistic language, said to be a reaction to the retrospective nostalgia of much 1940s architecture

#### Slide 06 - What raw concrete actually is

- **Audience move**: Accepts the ethic in principle → understands the concrete physically: why it is rough, why it is cheap, and what "shuttering" means
- **Relationships**: Raw concrete is one member of the material list the source gives; the shuttering marks are caused by the casting forms; modular elements grouped into a unified whole is a separate structural claim that sits alongside the material claim
- **Composition**: The material list as a dense ruled strip of monospace labels across the top, concrete pulled out and enlarged; the shuttering explanation as the wide body column; a halftone dot field standing in for the board-marked surface along one full-height edge
- **Title**: The grain of the formwork stays in the wall
- **Core message**: Brutalist concrete is rough because nothing was done to it after the forms came off — the wood that shaped it is still legible in the surface
- **Content**:
  - Materials the source lists: concrete · brick · glass · steel · timber · rough-hewn stone · gabions
  - Raw concrete is often used because of its low cost, and left to reveal the basic nature of its construction — rough surfaces carrying the wood "shuttering" pattern produced when the forms were cast in situ
  - Buildings are usually constructed with recurring modular elements representing specific functional zones, distinctly articulated and grouped into a unified whole
  - There is often an emphasis on graphic expression in the external elevations and in the whole-site plan, in regard to the main functions and people-flows of the building
  - Examples are frequently massive in character even when not large, and challenge traditional notions of what a building should look like, with focus given to interior spaces as much as exterior
  - The style commonly uses exposed, unpainted concrete or brick, angular geometric shapes and a predominantly monochrome colour palette; steel, timber and glass also feature
- **Motion suggestion**: The halftone edge field is a page-local texture and should not move; the material strip may build left to right as a sequence

#### Slide 07 - The building tells you what is inside it

- **Audience move**: Understands the surface → understands the plan, and can read a brutalist façade as a diagram of its own functions
- **Relationships**: Boston City Hall and Hunstanton School are two parallel examples of one claim — that the inner workings are exposed on the exterior; within Boston City Hall, the projecting portions are the parent of the rooms they indicate; Hunstanton's water tank and its visible pipes and conduits are two members of the same exposure
- **Composition**: The claim as a single wide headline sentence across the top; the two examples in unequal columns beneath it, Boston taking the wider measure with the duotone photograph in a ruled box on the narrow column; the water-tank detail inverted as the focal cell
- **Title**: A façade that admits what it is doing
- **Core message**: Brutalism put a building's structure, services and human use on the outside, so the elevation reports the plan
- **Content**:
  - A common theme is the exposure of the building's inner workings — structure, services and human use — on the exterior
  - Boston City Hall, designed in 1962: the strikingly different projected portions indicate the special nature of the rooms behind those walls, such as the mayor's office or the city council chambers
  - Hunstanton School placed the facility's water tank — normally a hidden service feature — in a prominent, visible tower
  - Rather than being hidden in the walls, Hunstanton's water and electric utilities were delivered via readily visible pipes and conduits
- **Images**: boston_city_hall_half.png

#### Slide 08 - Streets in the sky

- **Audience move**: Sees an architectural argument → sees a political one, and understands why the style saturated Eastern Europe and British social housing
- **Relationships**: The socialist utopian ideology is the parent of the "streets in the sky" idea and of the style's position in communist-country architecture; British social housing and Eastern-bloc construction are parallel consequences; brick brutalism is a contrast — a sub-genre defined by rejecting the concrete
- **Composition**: A wide left column carrying the ideological argument; a ruled sidebar on the right listing the five named countries in the data face; the "concrete emphasized equality" line inverted as the focal cell low on the page; the brick brutalism note as a rotated stamp box breaking the lower grid
- **Title**: Concrete was the point, not the compromise
- **Core message**: Brutalism carried a politics — separation of traffic and people, cheap honest material, and a rejection of the styles the bourgeoisie had owned
- **Content**:
  - Brutalism as an architectural philosophy was often associated with a socialist utopian ideology, supported by its designers and especially by Alison and Peter Smithson near the height of the style; their work sought to emphasise functionality and connect architecture with what they saw as the realities of modern life
  - Among their early contributions were "streets in the sky", in which traffic and pedestrian circulation were rigorously separated — a theme popular in the 1960s
  - In the UK the style featured in utilitarian, low-cost social housing influenced by socialist principles, and spread from there to other regions
  - The style held a strong position in the architecture of European communist countries from the mid-1960s to the late 1980s: Bulgaria · Czechoslovakia · East Germany · USSR · Yugoslavia. In Czechoslovakia it was presented as an attempt at a "national" but also "modern socialist" style; such prefabricated socialist-era buildings are called *panelaky*
  - Its popularity in socialist and communist nations owed to traditional styles being associated with the bourgeoisie, whereas concrete emphasised equality
  - A sub-genre is "brick brutalism" or "brickalism", where brick rather than concrete dominates — from the Smithsons' Soho house (1952) to Colin St John Wilson's British Library (1982–1998)

### Part 3: The buildings

#### Slide 09 - Who built it, and where

- **Audience move**: Knows the ideas → can now name architects and works across seven countries and see that this was never only a British style
- **Relationships**: Each country groups its named architects, and each architect is the parent of the works the source attributes to them; countries are parallel members of one international set with no ranking
- **Composition**: The page is the table — a full-width ruled record grid with the country column in the display face hanging outside the left rule, architect and work columns in the data and body faces; the header band inverted to solid ink
- **Title**: Eight countries, one language of concrete
- **Core message**: Brutalism was international within two decades, and the source names its architects country by country
- **Content**:
  - United Kingdom — Alison and Peter Smithson (pioneered the style); Ernő Goldfinger; Basil Spence (some work); the London County Council / Greater London Council Architects Department; Owen Luder; John Bancroft; Norman Engleback (Hayward Gallery); Denys Lasdun, arguably (National Theatre); Leslie Martin; James Stirling and James Gowan (early works); Chamberlin, Powell and Bon (Barbican Centre)
  - United States — Evans Woollen III (credited with introducing brutalism and modernism to Indianapolis); Walter Netsch (brutalist academic buildings); Marcel Breuer ("soft" approach, curves rather than corners); Ted Levy (Plaza Towers and Park Place on Peachtree, Atlanta); Eero Saarinen (Milwaukee County War Memorial, 1957); on Louis Kahn, William Jordy wrote he was "[o]pposed to what he regarded as the muscular posturing of most Brutalism" yet some of his work "was surely informed by some of the same ideas"
  - Australia — Robin Gibson (Queensland Art Gallery); Ken Woolley (Fisher Library, University of Sydney); Christopher Kringas (High Court of Australia Building); John Andrews (government and institutional structures); Daryl Jackson and Kevin Borland (Harold Holt Memorial Swimming Centre, Malvern, 1967 — one of the first brutalist buildings in Melbourne)
  - Canada — Arthur Erickson (Simon Fraser University main campus building, MacMillan Bloedel Building, Museum of Anthropology at UBC, Vancouver Law Courts); Green Blankstein Russell (Winnipeg Civic Centre, 1962–1963); Waisman Ross Blankstein Coop Gillmor Hanna (University of Manitoba Students' Union Building, 1966–1969; Royal Manitoba Theatre Centre, 1969–1970)
  - Argentina — Clorindo Testa (Banco de Londres y América del Sur headquarters; National Library of Argentina); Federico Peralta Ramos (Entel building)
  - Serbia — Božidar Janković ("Belgrade School of residence"); Mihajlo Mitrović (Western City Gate / Genex Tower, 1977)
  - Vietnam — Garol Isakovich (Vietnam-Soviet Friendship Palace of Culture and Labour, 1985; awarded Hero of Labor in 1976); Ngô Viết Thụ (Independence Palace, 1966, said to include brutalist elements)
  - Bosnia and Herzegovina — Slobodan Jovandić (Hotel Internacional and the residential building Lamela, both in Zenica)
- **Visualization**: A record grid of country × named architects × attributed works. `architect-roster`. **Native-ready**: `architect-roster=yes`

#### Slide 10 - The concrete campus

- **Audience move**: Thinks of brutalism as council housing → learns universities were its largest and most deliberate patron, on two continents
- **Relationships**: The named campus buildings are parallel members of one claim — that universities gave brutalist architects their opportunities; within the UK group, Stirling's Red Trilogy is an ordered set of three; the UEA ziggurats' 2023 closure is a consequence attached to that building alone
- **Composition**: Four unequal columns, one per campus story, with the building name in the title face and the architect and year in the data face beneath a hairline; the Grade-listing status as a repeated monospace tag; the ziggurat closure note in the inverted focal cell
- **Title**: The universities built them first, and biggest
- **Core message**: When Britain and America built new universities, they built them in raw concrete — and some of those buildings are now the style's most protected examples
- **Content**:
  - Britain, early: the 'beehives' at St John's College, Oxford (Michael Powers of the Architects' Co-Partnership, 1958–1960); the 1959 architecture department extension at Cambridge under Leslie Martin, designed by Colin St John Wilson and Alex Hardy with student participation, which inspired the Grade II listed University Centre and Churchill College
  - James Stirling's *Red Trilogy*, in order: University of Leicester Engineering Building with James Gowan (1959–1963), sometimes regarded as the first postmodern building in Britain; the Grade II* listed History Faculty Building, Cambridge (1964–1967), listed as "a distinctive example of a new approach to education buildings, from a period when the universities were at the forefront of architectural patronage"; the Florey Building at Queen's College, Oxford (1966–1971)
  - University of Sussex — Basil Spence's Grade I listed Falmer House (1960–1962), a "meeting of Arts and Crafts with modernism", hand-made bricks and colonnades of bare board-marked concrete arches inspired by the Colosseum; named a "key brutalist building" by RIBA, popularly acclaimed while less liked by professional critics
  - University of East Anglia — Denys Lasdun's six linked halls in Norfolk Terrace and four in Suffolk Terrace, the 'ziggurats' (1968), with the library and teaching wall between them, considered one of the finest 1960s brutalist campuses; the ziggurats were closed in 2023 in the reinforced autoclaved aerated concrete crisis, with no refurbishment date set as of February 2025
  - Durham University — Ove Arup's Grade I listed Kingsgate Bridge (1963), one of only six post-1961 buildings listed Grade I by 2017, and the Grade II listed Dunelm House (1964–1966), "the foremost students' union building of the post-war era in England", saved from demolition in 2021 after a five-year Twentieth Century Society campaign; Pevsner called it "Brutal by tradition but not brutal to the landscape"
  - United States — Paul Rudolph's 1963 Art and Architecture Building at Yale, where as department chair he was both client and architect; his 1964 University of Massachusetts Dartmouth, a rare entire campus in the style and by his own account "the most complete realisation of his experiments with urbanism and monumentality"; Walter Netsch's unified University of Illinois-Chicago Circle Campus, plus the Joseph Regenstein Library and the Northwestern University Library; William Pereira's Geisel Library at UC San Diego (1969–70), said to "occup[y] a fascinating nexus between brutalism and futurism", originally intended in steel and glass until cost moved the structure outside in concrete
  - Elsewhere — Robarts Library, University of Toronto (Warner, Burns, Toan & Lunde, 1968–1973), "a crowning achievement of the brutalist movement" that opened in 1974 to be condemned as "a blunder on the grandest scale"; Middle East Technical University, Ankara (Behruz and Altuğ Çinici, 1960s); Rand Afrikaans University, Johannesburg, designed as an expression of Afrikaans identity

#### Slide 11 - One building, by the numbers

- **Audience move**: Has read about the style in the abstract → holds one building's exact dimensions and can feel the scale the movement worked at
- **Relationships**: The Genex Tower's measurements are members of one object; the two towers and the two-storey bridge are parts of its parent form; its rank in Belgrade is a contrast against Ušće Tower, whose own height the source does not give
- **Composition**: Three hero figures set in the display face across the page, each with its monospace unit line and a hairline beneath; the form description in a narrow column; the missing comparison stated plainly in a ruled box rather than filled with an estimate
- **Title**: 117 metres of Belgrade
- **Core message**: The Western City Gate is the movement at full scale — two towers, a bridge, a revolving restaurant, and a critical reputation to match
- **Content**:
  - Mihajlo Mitrović designed the Western City Gate, also known as the Genex Tower, in Belgrade in 1977
  - 36 storeys · 117 m (384 ft) tall, or 135–140 m (443–459 ft) with the restaurant
  - Formed by two towers connected with a two-storey bridge, with a revolving restaurant at the top
  - Designed in the brutalist style with elements of structuralism and constructivism; the treatment of form and detail associates it slightly with postmodernism, and it is today one of the rare surviving representatives of this style's early period in Serbia
  - Considered a prime representative of brutalist architecture in Serbia and one of the best of its style built in the 1960s and 1970s in the world; its artistic expression marked an entire era in Serbian architecture
  - It is the second-tallest high-rise in Belgrade, after Ušće Tower — the source gives no height for Ušće Tower, so the gap is printed as NO DATA rather than estimated
- **Visualization**: Three hero figures with unit annotations plus one explicit no-data cell; this is typographic, not a value-driven chart, and carries no chart key

### Part 4: The reckoning

#### Slide 12 - Few styles have been so widely hated

- **Audience move**: Has been shown the case for brutalism → is given the case against it in the public's own words, without the guide defending it
- **Relationships**: The public verdict, the climate argument and the aesthetic-political objections are three parallel strands of the same backlash; the weathering mechanism is the cause of the staining that feeds the "urban decay" association
- **Composition**: The Jenkins quotation set as the largest thing on the page, inverted in a solid ink cell that crosses the column rules; the 2005 vote result as a hero figure in the accent colour; the climate mechanism in a dense lower column beside the letterboxed demolition photograph
- **Title**: "So many pleas from its users to see it destroyed"
- **Core message**: The backlash was popular, not academic — people voted for demolition, and the concrete itself was making the argument against it
- **Content**:
  - A 2014 article in *The Economist* noted the style's unpopularity, observing that a campaign to demolish a building will usually be directed against a brutalist one
  - Simon Jenkins: "Few styles in history can have been met with so many pleas from its users to see it destroyed."
  - In 2005 the British TV programme *Demolition* ran a public vote to select twelve buildings that ought to be demolished — eight of the twelve were brutalist
  - One argument is that the criticism exists partly because concrete façades do not age well in damp, cloudy maritime climates such as northwestern Europe and New England: the concrete becomes streaked with water stains, sometimes moss and lichen, and rust stains from the steel reinforcing bars
  - Critics find it unappealing for its "cold" appearance, projecting an atmosphere of totalitarianism, and for the association with urban decay from poor weathering and surfaces prone to graffiti
  - The Queen Elizabeth Square flats in Glasgow (1962) were demolished in 1993
- **Images**: demolition_mono.png
- **Motion suggestion**: The inverted quotation cell is the page's arrival; the demolition band beneath it should settle after the quotation, not with it

#### Slide 13 - Lost, and saved

- **Audience move**: Knows the style was attacked → sees the actual score sheet, and that the losses and the rescues run on the same clock
- **Relationships**: Each row pairs a building with its architect, a year, and an outcome; the rows divide into two contrasting membership groups — demolished and saved — that overlap in time rather than following one another
- **Composition**: One full-width ruled record grid, the outcome column carrying the only colour on the page; demolished and saved rows separated by a heavy rule rather than by a second table; the totals line set in the data face beneath
- **Title**: The score sheet
- **Core message**: Britain lost the Tricorn, Robin Hood Gardens and Birmingham Central Library — and in the same decades saved Preston, Dunelm House and the Southbank
- **Content**:
  - Demolished — Tricorn Centre, Owen Luder and Rodney Gordon, 2004; Third Church of Christ, Scientist, Washington D.C., Araldo Cossutta, 2014; Birmingham Central Library, John Madin, 2016; Robin Hood Gardens, East London, Alison and Peter Smithson, 2017; Welbeck Street car park, London, 2019 — the source names no architect for Welbeck Street, printed as NO DATA; American Press Institute Building, Reston, Virginia, Marcel Breuer — the source gives no demolition year, printed as NO DATA
  - Saved or listed — Preston bus station garage, Lancashire (1969), Grade II listed September 2013 after two unsuccessful demolition proposals; Dunelm House, Durham, saved from demolition in 2021 after a five-year campaign; London's Southbank Centre, including the Queen Elizabeth Hall and the Hayward Gallery, Grade II listed in 2026 after a 35-year Twentieth Century Society campaign; Villa Göth, listed by the Uppsala county administrative board on 3 March 1995; the Pirelli Tire Building, New Haven's Long Wharf, recognised in the United States
  - The Twentieth Century Society campaigned unsuccessfully against the Tricorn Centre and the Trinity Square multi-storey car park — made famous by its role in the film *Get Carter* — and successfully for Preston and the Southbank
  - On the Southbank listing, Society director Catherine Croft said "The battle has been won and brutalism has finally come of age"; Simon Heffer responded by calling for the centre's demolition
  - Gillespie, Kidd & Coia's St. Peter's Seminary, named Scotland's greatest post-war building in *Prospect* magazine's survey of architects, has been the subject of conservation campaigns
- **Visualization**: A record grid of building × architect × year × outcome, split by a heavy rule into demolished and saved groups. `loss-and-rescue`. **Native-ready**: `loss-and-rescue=yes`

#### Slide 14 - The style comes back in print, then in concrete

- **Audience move**: Expects the story to end in rubble → learns it ends in guidebooks, listings, Pritzker citations and new buildings
- **Relationships**: The 2015-onward publications are an ordered set that precedes and enables the revival; neobrutalism is the child of that revival; the named neobrutalist buildings are parallel examples, and the softening of the style's defining aspects contrasts with the buildings that still use board-marked concrete
- **Composition**: The publication run as a dense monospace column of titles and years down the left edge; the neobrutalist buildings as a wide right block with the Ningbo photograph in a ruled box; the "commissioned by the private sector" reversal inverted as the focal cell
- **Title**: Printed back into fashion
- **Core message**: The movement was over by the early 1980s, and since 2015 books, listings and Pritzker citations have brought it back — softened, privately funded, and still exposing its materials
- **Content**:
  - The original movement was largely over by the late 1970s and early 1980s, having given way to structural expressionism and deconstructivism
  - Interest resurged from 2015 with guides and books: *Brutal London* (Zupagrafika, 2015) · *Brutalist London Map* (2015) · *This Brutal World* (2016) · *SOS Brutalism: A Global Survey* (2017) · *Atlas of Brutalist Architecture* (2018)
  - New construction in the style followed, termed *neobrutalism*
  - Wang Shu's Ningbo Museum (2008) shows traces of the bamboo framework on its monumental concrete and was called "an urban icon" in his 2012 Pritzker Prize citation
  - Neobrutalist buildings tend to be commissioned by the private sector — such as the campus of the private University of Engineering and Technology (UTEC) in Peru by Yvonne Farrell and Shelley McNamara, referenced in their 2020 Pritzker Prize citation
  - They may use more ecologically friendly materials — recycled bricks, timber — rather than concrete, while keeping the fundamental concept of exposing materials and structural elements, as at the Colegio Reggio in Madrid
  - Many defining aspects have been softened: façades sandblasted to a stone-like surface, covered in stucco, or composed of patterned precast elements, as in the redevelopment of Sheffield's Park Hill
  - Board-marked concrete in the brutalist tradition is still used, as at the neobrutalist Silberrad Student Centre and library extension at the University of Essex (2015), designed to be sympathetic to the existing 1960s brutalist campus and taking "the opportunity to use in-situ brutalist concrete as a sensitive contextual material"
- **Images**: ningbo_museum_duo.png
- **Motion suggestion**: The masthead numeral and the top rule bar are the objects that carry into the closing page; the publication column may build downward in year order

### Part 5: Close

#### Slide 15 - Honest to the end

- **Audience move**: Has the whole story → leaves with one transferable test to apply to any building, brutalist or not
- **Relationships**: Banham's three conditions return as the closing frame; the takeaway links the ethic stated at the start to the buildings now being listed
- **Closing impact**: The binding takeaway is that brutalism asked to be judged by whether a building shows its plan, its structure and its materials as found — the same test that first made it hated and now makes it worth keeping. Composition Reference: the takeaway set at cover scale over a near-empty page, the three conditions returning as a single ruled line beneath it, the masthead numeral finally at rest in the corner
- **Title**: Judge it the way it asked to be judged
- **Core message**: The test brutalism set for itself — legible plan, exhibited structure, materials valued as found — is the test worth carrying out of this guide
- **Content**:
  - Banham's three conditions, restated as a closing line: formal legibility of plan · clear exhibition of structure · valuation of materials for their inherent qualities "as found"
  - "An ethic, not an aesthetic" — the Smithsons' own description of the movement
  - The style has been polarising throughout its history, and there are often public-led campaigns to demolish brutalist buildings; some people are favourable to it, and in the United Kingdom some buildings have been preserved
  - Active years: 1950s – early 1980s. Location: international
- **Motion suggestion**: A breathing page — one element arrives, everything else is already in place from the previous page

#### Slide 16 - Source

- **Audience move**: Has finished the guide → knows exactly which single page every fact came from and under what licence it may be reused
- **Relationships**: One source document is the parent of every claim in the deck; the licence statement links to that source
- **Composition**: A near-empty page in the masthead's own newspaper-colophon manner — a heavy rule bar, the source line set in the data face at readable size as a live link, the licence line beneath it, the guide's title returning small at the foot
- **Title**: Source
- **Core message**: Every fact, name, date and quotation in this guide comes from one Wikipedia article, reused under CC BY-SA
- **Content**:
  - Source: "Brutalist architecture", Wikipedia, the free encyclopedia. Retrieved 4 September 2026.
  - Link: https://en.wikipedia.org/wiki/Brutalist_architecture
  - Text from that article is reused under the Creative Commons Attribution-ShareAlike licence (CC BY-SA); this deck is a derivative work and carries the same licence.
  - Photographs are individually credited on the pages where they appear.
  - No claim in this deck comes from outside that article; where the article states no figure, the page prints NO DATA.
- **Links**: The text "en.wikipedia.org/wiki/Brutalist_architecture" links to https://en.wikipedia.org/wiki/Brutalist_architecture ; the text "CC BY-SA 4.0" links to https://creativecommons.org/licenses/by-sa/4.0/

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: Conversational narration grounded in the final SVG of each page — bridge from the previous beat, name what the reader is looking at, add the connective reasoning the dense columns cannot carry, and never introduce a fact absent from the page or the source article. Quotations stay verbatim; the two NO DATA gaps are named as gaps.
- **Total duration**: approximately 16–20 minutes at a reading pace of about 70–80 seconds per page
- **Notes style**: conversational
- **Presentation purpose**: Explain the origin, material logic and ethic of brutalism, inform completely about its architects, buildings and the demolition-versus-listing record, and leave the reader able to judge a concrete building on the terms the style set for itself

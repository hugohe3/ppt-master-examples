<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: en-US
- audience: The owner and four-person team of Fog & Fern Books, a fictional independent bookstore, judging the work by whether it sounds like their shop
- objective: Make the team feel one idea and believe its audience truth, then align them on scope so they approve the late-autumn campaign — success is that they can repeat the campaign line exactly and agree to go into production
- core_message: The last hour of the day is the only reading time still available and a screen already owns it; The Night Shelf takes it back
- consumption_mode: presentation

## mode
- mode: showcase

## visual_style
- visual_style: photo-editorial

## colors
- background: #0E0E10
- secondary_bg: #F4F1EA
- primary: #E9C877
- accent: #7FA69B
- secondary_accent: #C4553F
- body_text: #EDEAE3
- secondary_text: #A29E97
- divider: #2E2E33
- ink: #141416
- scrim: #08080A
- grid: #3A3A40
- image_rendering: custom
- image_rendering_references: corporate-photo, warm-scene, screen-print
- image_rendering_behavior: Photograph the world at night and print the campaign onto it. Edges are photographic except on campaign surfaces, where they become stencil-cut and slightly misregistered; texture is real material grain plus halftone confined to printed surfaces and a light overall film grain; depth is true optical depth with a sharp foreground, a falling-off middle ground and genuinely unlit background, while printed surfaces stay perfectly flat inside it; material is paper, glass, wood and skin under one warm practical light; mood is quiet and contemplative, cold outside the light. No text appears inside any generated image.

## typography
- font_family: Arial, sans-serif
- title_family: Georgia, serif
- body_family: Arial, sans-serif
- display_family: Arial, sans-serif
- cover_title_family: Georgia, serif
- idea_line_family: Georgia, serif
- body: 30
- title: 48
- subtitle: 38
- cover_title: 84
- idea_line: 72
- display: 96
- lead: 36
- annotation: 24
- footnote: 18

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/printer, tabler-outline/device-mobile, tabler-outline/building-store, tabler-outline/calendar-event, tabler-outline/bookmark, tabler-outline/book, tabler-outline/bulb

## images
- p01: images/hero_night_shelf.jpg | source=ai | crop=adaptive
- p03: images/element_moon.png | source=slice | crop=no-crop
- p05: images/hero_grey.jpg | source=ai | crop=adaptive
- p08a: images/poster_artwork.jpg | source=ai | crop=adaptive
- p08b: images/social_artwork.jpg | source=ai | crop=adaptive
- p08c: images/element_bookmark.png | source=slice | crop=no-crop
- p09a: images/hero_dim.jpg | source=ai | crop=adaptive
- p09b: images/element_fern.png | source=slice | crop=no-crop
- p09c: images/element_lamp.png | source=slice | crop=no-crop
- p10a: images/hero_blur.jpg | source=ai | crop=adaptive
- p10b: images/element_mug.png | source=slice | crop=no-crop
- p11: images/instore_scene.jpg | source=ai | crop=adaptive
- p12: images/element_book.png | source=slice | crop=no-crop

## page_visualizations
- P02: chart/grouped_bar_chart
- P12: table/record_table

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: breathing
- P05: breathing
- P06: anchor
- P07: anchor
- P08: dense
- P09: dense
- P10: breathing
- P11: anchor
- P12: dense
- P13: anchor

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- every title is solid-colour type with clear contrast against its ground (user)
- a text picture fill, if used at all, goes on one short decorative word with a near-uniform texture and never on the cover or a page title (user)
- Never use a real bookstore's or publisher's name or branding. (user)
- No text inside generated images — all copy is editable native text placed over the artwork. (user)

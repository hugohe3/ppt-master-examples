<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: ru-RU
- audience: Аналитики, журналисты данных, преподаватели и руководители программ, знакомые с темой убыли населения, но не держащие в памяти конкретные значения и коды индикаторов
- objective: Дать полный нейтральный срез по десяти индикаторам Всемирного банка и объяснить механику динамики численности так, чтобы слушатель мог назвать масштаб убыли, объяснить «русский крест» и найти любую цифру по коду индикатора и году
- core_message: Численность населения России в 2024 году на 4,7 млн ниже уровня 1991 года; естественная убыль почти непрерывна с 1992 года, и только миграционный прирост удерживал численность в 2009–2019 годах
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: pyramid, briefing
- mode_behavior: Страницы данных идут по pyramid — заголовок несёт вывод, под ним строка-итог, затем график или таблица как доказательство и строка источника; справочные страницы идут по briefing — тематический заголовок, равный вес строк, полнота вместо отбора. Порядок: общая численность, затем её компоненты, затем внешнее сопоставление и вывод.

## visual_style
- visual_style: custom
- visual_style_references: data-journalism, swiss-minimal
- visual_style_behavior: График или таблица — хребет страницы, текст верстается вокруг него, а не в карточке; тонкие линейки вместо рамок, врезка с одной ключевой величиной, постоянная служебная строка источника внизу страниц данных, числа окрашены по смыслу. Каркас жёсткий: модульная сетка на 12 колонок, прямые углы, одна крупная плоскость на страницах-якорях, широкие поля, без орнамента.

## colors
- background: #FBFAF7
- secondary_bg: #F0EDE6
- primary: #1B2B3A
- accent: #B3121B
- secondary_accent: #2E6F8E
- body_text: #232A31
- secondary_text: #5B6670
- divider: #D5CFC4
- surface: #FFFFFF
- grid: #E6E1D7
- positive: #2E7D32
- negative: #B3121B
- warning: #F57C00
- image_rendering: custom
- image_rendering_references: editorial, minimalist-swiss
- image_rendering_behavior: Абстрактная редакционная композиция на модульной сетке — плоские заливки без градиентов, тонкие точные линейки единой толщины, одна доминирующая область и широкое спокойное поле, бумажная зернистость около 8 %; плотность форм убывает к зоне текста; без текста и цифр в изображении.

## typography
- font_family: Arial, sans-serif
- title_family: Times New Roman, serif
- body_family: Arial, sans-serif
- display_family: Times New Roman, serif
- data_family: Consolas, monospace
- annotation_family: Arial, sans-serif
- footnote_family: Arial, sans-serif
- body: 24
- title: 40
- subtitle: 32
- annotation: 18
- cover_title: 76
- display: 64
- lead: 28
- data: 22
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/users, tabler-outline/chart-line, tabler-outline/baby-carriage, tabler-outline/grave, tabler-outline/hourglass, tabler-outline/building-skyscraper, tabler-outline/arrows-exchange, tabler-outline/database, tabler-outline/world, tabler-outline/flag, tabler-outline/man, tabler-outline/woman, tabler-outline/arrow-up-right, tabler-outline/arrow-down-right

## images
- p01: images/01_cover_field.jpg | source=ai | crop=adaptive
- p15: images/15_closing_band.jpg | source=ai | crop=adaptive

## page_visualizations
- P02: table/record_table
- P03: chart/line_chart
- P04: chart/line_chart
- P05: chart/line_chart
- P06: chart/column_chart
- P07: chart/line_chart
- P08: chart/line_chart
- P10: chart/column_chart
- P12: chart/column_chart
- P13: table/metric_table
- P14: chart/grouped_bar_chart

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: breathing
- P08: dense
- P09: breathing
- P10: dense
- P11: breathing
- P12: dense
- P13: dense
- P14: dense
- P15: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- Все данные — только из приложенных CSV Всемирного банка (папка _sources_ru_demography), ничего не выдумывай, у каждой цифры укажи код индикатора и год (user)

<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 全省市、县级自然资源主管部门及勘查、设计、施工、监理等参建单位的项目管理人员
- objective: 逐页解读《吉林省地质灾害治理工程项目管理办法》的背景、依据、框架、规范内容与特点，使听众理解入库、实施、验收、管护的流程与时限并找到本单位职责
- core_message: 《办法》把地质灾害治理工程项目管理规范为从入库、实施、验收到运行管护、全过程监督的一整套运行规程
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: briefing
- mode_behavior: 以 briefing 为唯一基底：逐页中立、完整、可查找；源稿20页一一对应、顺序与文字逐字不变，页标题沿用源稿章节式主题标题，同级条款同形同权，只在源稿已标注的关键词、时限与禁止事项上加强强调，不制造结论句。

## visual_style
- visual_style: custom
- visual_style_behavior: 政务条文手册：白色纸面；页眉为左侧深色主题标题、蓝色章节标签、右上角圆形厅徽，页眉下细分隔线的左段为蓝色山形折线母题；条款抬头用满宽蓝色条带（白字、黄色高亮关键词）；并列条款用同尺寸浅蓝底面板或编号行，编号为大号蓝色数字或圆形编号牌；流程与时限用带连接线的编号轨道；6px小圆角，仅截图卡片有轻微投影；强调两级：蓝色加粗标关键词，红色加粗标时限、禁止与关键结论；截图以白边卡片呈现，剪贴画保留原貌加细框。

## colors
- background: #FFFFFF
- secondary_bg: #EEF4FB
- primary: #0070C0
- accent: #D7141A
- secondary_accent: #E07A1F
- body_text: #1F2328
- secondary_text: #5A6472
- divider: #C9D6E5
- title_text: #0B2A5B
- highlight: #FFC000
- panel_edge: #5B9BD5

## typography
- font_family: "Microsoft YaHei", Arial, sans-serif
- title_family: "Microsoft YaHei", Arial, sans-serif
- body_family: "Microsoft YaHei", Arial, sans-serif
- numeral_family: Arial, "Microsoft YaHei", sans-serif
- body: 24
- title: 36
- subtitle: 28
- annotation: 18
- cover_title: 56
- lead: 26
- numeral: 32
- footnote: 14

## icons
- library: tabler-filled
- inventory: tabler-filled/book, tabler-filled/database, tabler-filled/building-bridge-2, tabler-filled/clipboard-check, tabler-filled/shield-check, tabler-filled/eye, tabler-filled/file-text, tabler-filled/scale, tabler-filled/zoom-check, tabler-filled/calendar, tabler-filled/clock, tabler-filled/archive, tabler-filled/list-check, tabler-filled/writing-sign, tabler-filled/map-pin, tabler-filled/circle-check, tabler-filled/mountain, tabler-filled/rosette, tabler-filled/flag, tabler-filled/alert-triangle, tabler-filled/briefcase

## images
- logo: images/1.jpeg | source=user | crop=adaptive
- p03_notice: images/2.png | source=user | crop=no-crop
- p04_gov: images/3.png | source=user | crop=adaptive
- p04_mnr: images/4.png | source=user | crop=no-crop
- p04_flk: images/5.png | source=user | crop=no-crop
- p07_procure: images/6.jpeg | source=user | crop=no-crop
- p07_lifelong: images/7.jpeg | source=user | crop=no-crop
- p12_subcontract: images/8.jpeg | source=user | crop=no-crop

## page_rhythm
- P01: anchor
- P02: anchor
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: dense
- P11: dense
- P12: breathing
- P13: dense
- P14: dense
- P15: dense
- P16: dense
- P17: dense
- P18: breathing
- P19: dense
- P20: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 内容一个字都不要动，页数页序也不变 (user)

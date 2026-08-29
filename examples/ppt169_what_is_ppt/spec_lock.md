<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- audience: 会用 PowerPoint 但把 PPT 只当"做几页幻灯片"的知识工作者、学生与职场人
- objective: 系统讲清 PPT 同时是沟通媒介、可编辑文档、传递载体与原生文件结构，使受众能区分其多重含义、看懂原生对象模型、判断任务是否适合演示文稿，并在动手前问对关键问题
- core_message: PPT 不是一叠静态页面，而是有顺序、模块化、可编辑并需要持续流转的沟通产物——先想清受众要完成什么任务，工具才服务沟通
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional, pyramid
- mode_behavior: 三幕。第一幕"解构"拆解"PPT"被混用的多重含义、制造认知张力；第二幕"重构"用 instructional 的概念分解逐页只讲一个概念、平行展开可比，关键页用 pyramid 结论先行、标题即断言；第三幕"方法"落到"每次做 PPT 该问的问题"，把认知收成可执行的闭环。

## visual_style
- visual_style: custom
- visual_style_references: editorial, blueprint
- visual_style_behavior: editorial 杂志栅格与眉题→标题→引言→正文的强纵向层级为底，非对称分栏与竖向规则线；讲结构/对象模型的页面叠加 blueprint 示意线稿——细单色线框、等距投影、尺寸标注线、引线箭头、坐标/代号标签、极低透明度网格底。正文区清晰留白，结构区线稿在浅场上呼吸；遵循工程图"单一高亮色"惯例，用 colors.accent 作唯一强调。

## colors
- background: #FFFFFF
- secondary_bg: #F4F1EA
- primary: #1A2B4A
- accent: #C8102E
- secondary_accent: #5E7089
- body_text: #22262B
- image_rendering: custom
- image_rendering_references: blueprint, editorial
- image_rendering_behavior: blueprint 示意线稿+网格+标注为骨架，叠 editorial 信息图的实色区块与层级；crisp 单一线宽（约1.5px 观感）、直角与精确曲线，元素简化为框/连接线/锚点/代号标记，可选 5-8% 透明度网格衬底；无照片、无渐变噪点、无材质阴影。图像色彩全部继承演示色：primary 作线稿主色、accent 作单一高亮、白/secondary_bg 作场、secondary_accent 作次级线。

## typography
- font_family: "Microsoft YaHei", Consolas, monospace
- title_family: "Microsoft YaHei", Arial, sans-serif
- body_family: "Microsoft YaHei", Consolas, monospace
- title: 42
- subtitle: 32
- body: 24
- annotation: 18
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/app-window, tabler-outline/presentation, tabler-outline/stack-2, tabler-outline/player-play, tabler-outline/file-zip, tabler-outline/transform, tabler-outline/target, tabler-outline/info-circle, tabler-outline/bulb, tabler-outline/speakerphone, tabler-outline/checkbox, tabler-outline/users-group, tabler-outline/school, tabler-outline/report, tabler-outline/flag, tabler-outline/archive, tabler-outline/list-numbers, tabler-outline/layout-grid, tabler-outline/photo, tabler-outline/microphone, tabler-outline/book, tabler-outline/edit, tabler-outline/transfer, tabler-outline/file-text, tabler-outline/table, tabler-outline/layout-board, tabler-outline/movie, tabler-outline/browser, tabler-outline/arrows-shuffle, tabler-outline/palette, tabler-outline/template, tabler-outline/layout, tabler-outline/rectangle, tabler-outline/square, tabler-outline/notes, tabler-outline/link, tabler-outline/checklist, tabler-outline/message-2, tabler-outline/route, tabler-outline/brain, tabler-outline/eye, tabler-outline/settings, tabler-outline/help-circle, tabler-outline/users, tabler-outline/refresh

## images
- cover_identities: images/cover_identities.jpg | source=ai | pattern=#73 Full-bleed poster image + side title stack | crop=adaptive
- five_meanings: images/five_meanings.jpg | source=ai | pattern=#3 Right-third image + left text body | crop=adaptive
- object_model: images/object_model.jpg | source=ai | pattern=#41 Background image + measurement lines and module tags | crop=adaptive
- quality_layers: images/quality_layers.jpg | source=ai | pattern=#3 Right-third image + left text body | crop=adaptive
- ppt_is_not: images/ppt_is_not.jpg | source=ai | pattern=#2 Left-third image + right text body | crop=adaptive

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: breathing
- P05: dense
- P06: dense
- P07: dense
- P08: breathing
- P09: dense
- P10: breathing
- P11: dense
- P12: dense
- P13: breathing
- P14: dense
- P15: dense
- P16: dense
- P17: breathing

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters

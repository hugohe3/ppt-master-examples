<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1024 768
- format: PPT 4:3

## communication
- primary_language: zh-CN
- audience: 有高中数学基础的大学新生与做信号/图像/通信的工程师
- objective: 用一节 45 分钟公开课把时域到频域讲通,使听众能读懂并复述一条变换对与卷积定理、解释 FFT 为什么快,并指认一个自己领域的傅里叶应用
- core_message: 傅里叶变换是一本可逆的字典,把"随时间怎么变"翻译成"由哪些频率组成"
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional, briefing
- mode_behavior: 教学阶梯为主干,每页一个可验证的理解台阶,页标题写成陈述句,上一页结论是下一页前提;instructional 负责概念分解与推导顺序,briefing 负责变换对表与应用页的中性均权陈列;每小节先一句直觉,再公式,再一句能做什么。

## visual_style
- visual_style: custom
- visual_style_references: swiss-minimal, editorial, data-journalism
- visual_style_behavior: 教科书跨页语言——swiss-minimal 定 12 栅格、硬边直角与大留白,editorial 提供细规则线、边注栏、小节序号与衬线/黑体互文层级,data-journalism 只负责公式与图表下的来源行与刻度注记;公式独占浅底带状区并以左侧 3px 主色竖条起头,右侧留边注栏写读法;装饰只有细线、带状区与刻度,无卡片阴影、无圆角、无渐变。

## colors
- background: #FFFFFF
- secondary_bg: #F2F4F7
- primary: #123B63
- accent: #C2452D
- secondary_accent: #2E7D7B
- body_text: #1B2027
- secondary_text: #5A6472
- divider: #D6DBE1
- image_rendering: custom
- image_rendering_references: blueprint, editorial
- image_rendering_behavior: 讲义插图而非海报——blueprint 给等宽刻度、细网格底与描线感的技术图语言,editorial 给杂志信息图的干净留白与清晰层级;线条均匀细实,无渐变、无发光、无立体投影;只用主色、时域青碧与频域朱红三色,底为纸白。

## typography
- font_family: Microsoft YaHei, Cambria, sans-serif
- title_family: SimSun, Cambria, serif
- body_family: Microsoft YaHei, Cambria, sans-serif
- formula_family: Cambria Math, serif
- annotation_family: Microsoft YaHei, Cambria, sans-serif
- footnote_family: Microsoft YaHei, Cambria, sans-serif
- display_family: SimSun, Cambria, serif
- body: 24
- title: 42
- subtitle: 32
- formula: 28
- annotation: 18
- footnote: 16
- display: 60

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/wave-sine, tabler-outline/math-function, tabler-outline/chart-histogram, tabler-outline/photo, tabler-outline/wifi, tabler-outline/activity-heartbeat, tabler-outline/music, tabler-outline/clock, tabler-outline/repeat, tabler-outline/book, tabler-outline/bulb, tabler-outline/arrows-right-left

## images
- p01: images/cover_wave_band.jpg | source=ai | crop=adaptive

## page_visualizations
- P05: chart/column_chart
- P08: table/record_table
- P13: chart/line_chart

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: dense
- P05: dense
- P06: breathing
- P07: dense
- P08: dense
- P09: dense
- P10: dense
- P11: dense
- P12: dense
- P13: dense
- P14: dense
- P15: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 公式要多而且要是 PowerPoint 里可编辑的原生公式,不要贴图 (user)

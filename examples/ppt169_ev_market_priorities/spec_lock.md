<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 整车企业高管团队与海外业务/战略负责人
- objective: 让管理层接受"美国停滞、欧洲分化、新兴市场加速"三个判断,并批准三级市场优先级与 PHEV 先行的产品节奏
- core_message: 增量重心已从欧美转向新兴市场,2026–2028 应分级投入并以 PHEV 打开低渗透市场
- consumption_mode: text

## mode
- mode: pyramid

## visual_style
- visual_style: custom
- visual_style_references: swiss-minimal
- visual_style_behavior: 白底咨询决策文档(文档密度,非演示密度):每页一个两行以内的行动标题顶在页首,标题下一行灰色单位/副题行,再一条深色细横线;右上角小字追踪器与「讨论稿」贴纸、右下角页码、页脚编号脚注加来源行;正文区左 2/3 并置两到三个证据面板(各带加粗小标题与单位行),右 1/3 为「关键信息」编号要点栏,图上用编号圆点 callout 对应要点;纯平面,只用 1px 发丝线和留白分隔,无卡片、圆角、阴影、渐变;藏青为主系列与标题,电蓝只标当页唯一强调,灰承担其余,深色满版仅封面与章节页;表格为细横线表,数字右对齐用 Arial。

## colors
- background: #FFFFFF
- secondary_bg: #F2F2F2
- primary: #051C2C
- accent: #2251FF
- secondary_accent: #8FB8FF
- body_text: #333333
- secondary_text: #7F7F7F
- divider: #B7B7B7
- grid: #E3E3E3
- surface: #F7F7F7
- negative: #B3261E

## typography
- font_family: Microsoft YaHei
- title_family: Microsoft YaHei
- body_family: Microsoft YaHei
- data_family: Arial
- display_family: Arial
- body: 14
- title: 24
- subtitle: 14
- lead: 16
- annotation: 12
- footnote: 10
- display: 40
- data: 12

## icons
- library: none
- inventory: none

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: dense
- P11: breathing
- P12: dense
- P13: breathing
- P14: anchor

## page_visualizations
- P03: chart/dual_axis_line_chart
- P04: chart/stacked_bar_chart
- P05: chart/line_chart
- P06: chart/horizontal_bar_chart
- P07: chart/grouped_bar_chart
- P08: chart/stacked_area_chart
- P09: chart/waterfall_chart
- P10: table/comparison_matrix
- P12: table/record_table
- P14: table/metric_table

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters

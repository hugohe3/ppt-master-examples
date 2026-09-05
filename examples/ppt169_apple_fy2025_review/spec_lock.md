<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 苹果管理层与机构投资者,已熟悉业务与分部口径
- objective: 先落定 FY2025 的整体结论再逐项解释每一处重大变化的来源,使受众能说出增长与毛利向服务集中的事实、识别净利润增速中的基数效应、定位大中华区与可穿戴两处收缩,并对三个未决问题各自形成判断
- core_message: FY2025 总量健康、质量提升,但增长与毛利同时向服务集中,风险集中在大中华区与可穿戴两处;净利润 +19.50% 中含 FY24 一次性税项造成的基数效应,可比口径为 +7.72%
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: briefing, pyramid
- mode_behavior: 以简报方式直接给出本期结果,不复述受众已有背景;随后对每一处重大变化用金字塔收口——偏差、解释其大部分的原因、证据、以及尚未定论的部分。深度跟随重要性而非版面对称,平稳指标一行带过,移动了的指标给完整链条;页面形状跨页与跨期保持稳定以便直接比较。

## visual_style
- visual_style: custom
- visual_style_references: data-journalism, swiss-minimal
- visual_style_behavior: 账页式栅格——纸白场上用发丝细线而非卡片与阴影划分区域,分栏与基线严格对齐;每页固定顶部断言句带、中部数字/图表主体、底部来源与口径行三个区域,位置跨页不变。零装饰:无渐变、无发光、无圆角 KPI 卡与仪表盘外壳;状态由色加形状或符号双重编码,灰度可读。数字走等宽字族并右对齐,靠对齐而非容器分组;留白用于分开结果与解释,不用于稀释密度。

## colors
- background: #FFFFFF
- secondary_bg: #F4F6F8
- primary: #1E293B
- accent: #2B6CB0
- secondary_accent: #2E7D5B
- body_text: #1E293B
- secondary_text: #64748B
- divider: #D8DEE6
- surface: #F4F6F8
- grid: #E8EDF2
- positive: #2E7D5B
- warning: #8A5A12
- negative: #B4342C
- series_alt: #7BA7D4

## typography
- font_family: Microsoft YaHei
- title_family: Microsoft YaHei
- body_family: Microsoft YaHei
- data_family: Consolas
- kpi_hero_family: Consolas
- body: 24
- title: 44
- subtitle: 30
- annotation: 18
- cover_title: 72
- lead: 28
- kpi_hero: 64
- data: 24
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/trending-up, tabler-outline/trending-down, tabler-outline/chart-bar, tabler-outline/world, tabler-outline/device-mobile, tabler-outline/cloud, tabler-outline/coin, tabler-outline/alert-triangle, tabler-outline/target, tabler-outline/file-text, tabler-outline/link, tabler-outline/calendar-stats, simple-icons/apple

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: breathing
- P09: dense
- P10: breathing
- P11: dense
- P12: breathing
- P13: anchor
- P14: anchor

## page_visualizations
- P02: table/metric_table
- P03: chart/waterfall_chart
- P04: chart/column_chart
- P05: chart/column_chart, chart/line_chart, chart/stacked_bar_chart
- P06: chart/grouped_bar_chart
- P07: chart/stacked_bar_chart
- P08: chart/line_chart
- P09: table/comparison_matrix
- P11: chart/line_chart

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 不做任何 AI 生图、不搜网图 (user)
- 不为"原生可编辑"降级视觉 (user)
- 不配音效、不做路径动画 (user)
- 不引入这两个文件之外的事实 (user)

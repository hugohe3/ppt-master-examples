<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 科普展厅循环播放区的公众观众(含中小学生与家长),日常使用手机地图但不了解卫星导航原理与北斗建设历程,停留时间短且可能中途加入
- objective: 用可核验的事实讲清北斗的三步走、三轨混合与短报文独创,使观众离开时能自述"三步、三轨、短报文"并知道自己手机里就有北斗
- core_message: 北斗不是"中国版GPS",而是按自己的路线走出来的时空基础设施——三步走完、三轨混合、导航与通信合一
- consumption_mode: presentation

## mode
- mode: custom
- mode_references: instructional, narrative
- mode_behavior: 骨架用 instructional 的概念分解与分步推进,每一场景只推进一个理解台阶,前一台阶的结论是下一台阶的前提;三步走那一段按 narrative 的张力走(起点"只有一颗试验星、用户还得自己发信号",转折"从有源到无源",收束"提前半年、18箭30星")。讲"怎么回事"的页用分解,讲"怎么走过来"的页用故事推进;标题一律写成陈述句,让中途加入的观众读标题即拿到该页主张。

## visual_style
- visual_style: custom
- visual_style_references: dark-tech, blueprint, data-journalism
- visual_style_behavior: 近黑深蓝的连续天场作底,其上用示意线语言——细实线、细虚线、刻度、引出线与标注,几何一律用原生形状画,不用卡片网格承载概念;面板只在需要把读数与天场分开时出现,直角无圆角,靠 1px 分隔线而非阴影抬起。每个外部事实数字下方有一条极小的来源行(来源名+年份),来源行是全片的视觉签名。装饰密度低,除轨道弧线、刻度与那条贯穿页面的仪器横梁外不加纯装饰元素;大面积留白留给天场。标题用钝头黑体对住天场,数字用等宽体排成仪表读数,二者对比是本片的字体戏剧。

## colors
- background: #060B1A
- secondary_bg: #0E1730
- primary: #4EA8FF
- accent: #FFC24B
- secondary_accent: #35D0A5
- body_text: #D8E0F0
- secondary_text: #8FA0C0
- divider: #1E2B4A
- surface: #111C38
- grid: #1A2747
- scrim: #060B1A
- image_rendering: custom
- image_rendering_references: corporate-photo
- image_rendering_behavior: 以真实摄影的线与质地为唯一基底,自然镜头虚化、克制的暗部噪点、冷蓝到近黑的连续影调过渡;材质靠光而不靠描边,深度来自景深与大气透视;低照度纪录片式的克制,不加风格化滤镜、渐变叠加或发光特效。

## typography
- font_family: Microsoft YaHei, Arial, sans-serif
- title_family: SimHei, Arial, sans-serif
- body_family: Microsoft YaHei, Arial, sans-serif
- display_family: SimHei, Arial, sans-serif
- data_family: Consolas, Microsoft YaHei, monospace
- hero_number_family: Consolas, Microsoft YaHei, monospace
- footnote_family: Consolas, Microsoft YaHei, monospace
- year_family: Consolas, Microsoft YaHei, monospace
- display: 96
- hero_number: 88
- title: 52
- subtitle: 40
- year: 40
- lead: 36
- body: 30
- annotation: 22
- data: 22
- footnote: 18

## icons
- library: tabler-outline
- stroke_width: 3
- inventory: tabler-outline/satellite, tabler-outline/world, tabler-outline/clock, tabler-outline/broadcast, tabler-outline/map-pin, tabler-outline/message, tabler-outline/ship, tabler-outline/plane, tabler-outline/tractor, tabler-outline/bolt, tabler-outline/device-mobile, tabler-outline/route, tabler-outline/rocket, tabler-outline/target, tabler-outline/lifebuoy, tabler-outline/link, tabler-outline/antenna, tabler-outline/radar, tabler-outline/mountain, tabler-outline/map

## images
- p01: images/cover_orbit_earth_fit.jpg | source=ai | crop=adaptive
- p11: images/scene_night_sea_fit.jpg | source=ai | crop=adaptive
- p13: images/app_scene_muted.jpg | source=ai | crop=adaptive

## page_visualizations
- P05: table/comparison_matrix
- P08: chart/donut_chart
- P12: chart/horizontal_bar_chart

## page_rhythm
- P01: anchor
- P02: dense
- P03: anchor
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: breathing
- P09: dense
- P10: dense
- P11: dense
- P12: breathing
- P13: dense
- P14: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 展示文字绝不用场景图或渐变填充;所有标题用单色实心字 (user)
- 找不到可追溯出处的数字不用 (user)
- Morph 只配相邻页,不配原生图表 (user)

<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 新上岗的消防控制室值班员,已受过设备按键层面的基础培训,但尚未把散落在国家标准、法规与统计中的值班规则串成一条判断轴
- objective: 教会值班员在接到报警后先判定自己处于四级判断轴的哪一级、再执行该级唯一正确的动作,并能把规则回溯到它依赖的机制页与记录义务
- core_message: 值班不是盯屏幕,是把每一个报警信号推进到一个明确的级别,并在该级别上执行唯一正确的动作
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional, pyramid
- mode_behavior: 每节以一句可判断的结论开场,再按拆开—展开—应用三拍讲机制;全 deck 只保留一条纵向判断轴,任何一页都能回答现在在第几级、第几步;标题写成判断句而非名词短语。

## visual_style
- visual_style: custom
- visual_style_references: swiss-minimal, blueprint, dark-tech
- visual_style_behavior: 深底之上的严格网格手册;swiss-minimal 负责基线栏、硬左对齐与大留白,blueprint 负责细线网格、引出线注解与剖面式图解,dark-tech 负责深底上的高对比强调与几何精度;容器一律零圆角细线方框,无投影无辉光;左缘固定分节进度指示条,当前节点亮强调色,离轴内容整条转警示色。

## colors
- background: #0E1B2E
- secondary_bg: #1A2C46
- primary: #4A9FD8
- accent: #D8F04A
- secondary_accent: #E85D2B
- body_text: #DCE6F0
- secondary_text: #8FA3BC
- divider: #2A3F5C
- surface: #16273D
- grid: #1C2E49
- scrim: #0A1422
- image_rendering: custom
- image_rendering_references: blueprint, vector-illustration, digital-dashboard
- image_rendering_behavior: 两个共享同一深底与同一组强调色的登记册——白色等线宽技术线图(无填充、正交连线、端点圆点、引出线注解)与冷光深色实景画面;图内一律无文字,无渐变、无阴影、无景深;实景硬边直角嵌入,压字处用定向 scrim 而非整幅压暗。

## typography
- font_family: 'Microsoft YaHei', Arial, sans-serif
- title_family: 'Microsoft YaHei', Arial, sans-serif
- body_family: 'Microsoft YaHei', Arial, sans-serif
- display_family: 'Arial Black', 'Microsoft YaHei', sans-serif
- data_family: Arial, 'Microsoft YaHei', sans-serif
- annotation_family: 'Microsoft YaHei', Arial, sans-serif
- footnote_family: 'Microsoft YaHei', Arial, sans-serif
- body: 24
- title: 40
- subtitle: 30
- lead: 28
- display: 96
- data: 22
- annotation: 18
- footnote: 16

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/bell, tabler-outline/alert-triangle, tabler-outline/phone, tabler-outline/clipboard-check, tabler-outline/users, tabler-outline/clock, tabler-outline/flame, tabler-outline/device-desktop, tabler-outline/toggle-right, tabler-outline/door-exit, tabler-outline/certificate, tabler-outline/file-text, tabler-outline/link, tabler-outline/ban, tabler-outline/droplet, tabler-outline/wind, tabler-outline/eye, tabler-outline/checklist

## images
- p01: images/cover_control_room_night_fit.jpg | source=ai | crop=adaptive
- p04: images/divider_alarm_panel_fit.jpg | source=ai | crop=adaptive
- p06: images/diagram_signal_chain_fit.png | source=ai | crop=no-crop
- p12: images/divider_duty_log_fit.jpg | source=ai | crop=adaptive
- p15: images/counter_auto_manual_switch_fit.jpg | source=ai | crop=adaptive

## page_visualizations
- P03: chart/grouped_bar_chart
- P13: table/record_table
- P14: table/record_table

## page_rhythm
- P01: anchor
- P02: anchor
- P03: dense
- P04: breathing
- P05: dense
- P06: dense
- P07: anchor
- P08: dense
- P09: dense
- P10: dense
- P11: breathing
- P12: breathing
- P13: dense
- P14: dense
- P15: dense
- P16: dense

## pptx_structure
- mode: flat
- template_reuse_scope: style

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 展示文字绝不用场景图或渐变填充 (user)
- 图内无文字 (user)
- 量级差异过大的项拆到单独数字块并标倍数,不硬塞一轴 (user)

<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 对太空史有兴趣但不是专业读者的中文观众，知道"阿波罗登月"这个名字，记得一两张照片，但说不清这四年里到底发生了几件事
- objective: 用满版照片建立在场感、用少量精确的数字把 1968–1972 串成一条时间线，成功标志是观众能复述四个关键时刻、说出每张照片的拍摄者与时刻，并意识到最后一次离开月面已过去半个多世纪
- core_message: 从 1968 年 12 月 21 日到 1972 年 12 月 19 日，1,459 天，人类九次抵达月球、六次落上去、十二个人走过月面，然后再没有回去
- consumption_mode: presentation

## mode
- mode: custom
- mode_references: narrative
- mode_behavior: 以 situation → tension → resolution 走四年——1968 设赌注、1969 兑现、1970 崩塌、1971–72 收束；页标题写成推进故事的句子而非标签；张力页与呼吸页按情节需要交替，不做机械轮转；人物、时刻、器材是抓手，抽象的"人类壮举"不作为论据。

## visual_style
- visual_style: custom
- visual_style_references: photo-editorial
- visual_style_behavior: 满版出血照片是页面脊椎，文字只做指认、计数与图注；装饰只有发丝细线、编号章标与小字图注，任何卡片、图标、装饰阴影都不与照片争注意力。构图在四种之间轮换——L 形文字区、标题跨压照片明暗交界、破边的浮动图注卡、无照片时退回 editorial 多栏文字页；相邻两页不重复同一种。留白给文字、出血给照片；文字侧永远是安静的中性暗色，锈橙只落在编号、细线与一两个关键词上。整卷平面，唯一允许的渐变是压字用的方向性 scrim。

## colors
- background: #0B0E11
- secondary_bg: #161A20
- primary: #E9E4D9
- accent: #D2622B
- secondary_accent: #6E7B8A
- body_text: #DAD5CA
- secondary_text: #98A0A9
- divider: #39414A
- scrim: #06080B
- surface: #1E242B

## typography
- font_family: Arial, Microsoft YaHei
- title_family: Times New Roman, SimSun
- body_family: Arial, Microsoft YaHei
- display_family: Times New Roman, SimSun
- body: 30
- title: 54
- subtitle: 40
- display: 78
- annotation: 22
- footnote: 18

## icons
- library: none
- inventory: none

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: breathing
- P05: breathing
- P06: dense
- P07: breathing
- P08: dense
- P09: breathing
- P10: breathing
- P11: dense
- P12: anchor
- P13: anchor

## pptx_structure
- mode: flat

## page_visualizations
- P11: table/record_table

## images
- p01: images/01_launch.jpg | source=web | crop=adaptive
- p02: images/02_earthrise.jpg | source=web | crop=adaptive
- p04: images/03_ladder.jpg | source=web | crop=adaptive
- p05: images/04_visor.jpg | source=web | crop=adaptive
- p06: images/05_bootprint.jpg | source=web | crop=adaptive
- p07: images/06_apollo13_sm_mono.jpg | source=web | crop=adaptive
- p09: images/07_irwin_rover.jpg | source=web | crop=adaptive
- p10: images/08_schmitt_boulder.jpg | source=web | crop=adaptive
- p12: images/09_blue_marble.jpg | source=web | crop=adaptive
- p13: images/10_apollo11_liftoff.jpg | source=web | crop=adaptive

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 不生成 AI 图冒充照片 (user)
- 不要把多种处理叠在同一张上 (user)
- 不为原生降级 (user)

<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-CN
- audience: 公司新入职员工（非安全专业岗），已签保密协议但尚未接触内部安全制度
- objective: 让新员工承认个人日常操作即企业风险敞口，按账号、数据设备、合规红线、应急上报的顺序学会可执行动作，并当堂说出三条与自己相关的法律红线、指出仿冒邮件的破绽、说出发现异常后 4 小时内报给谁
- core_message: 攻击者的首选入口是员工而不是系统，法律罚到个人、还能禁业；而及时上报是免责条款，不是追责起点
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional, pyramid
- mode_behavior: 以 instructional 的概念分解与固定教学顺序作为全卷骨架，同级概念用同样的深度与结构并列，最后用随堂自测检验；每章内部借 pyramid 的结论先行，标题写判断句而不是话题标签，证据与法条随后展开，每章末页用一句可执行的"你要做的"收束。

## visual_style
- visual_style: custom
- visual_style_references: editorial, swiss-minimal, data-journalism
- visual_style_behavior: swiss-minimal 负责严格基线网格、非对称栏宽、大留白与方角单一线重；editorial 负责眉标、细规则线、边注栏、引块与超大编号的排版层级；data-journalism 负责证据页的密度组织——图表作为页面脊柱、全幅 hero 数字、每页底部一条来源行。层级靠规则线粗细与实色块拉开，不用阴影与发光；章节页整版反转为深墨实底承接超大编号。

## colors
- background: #F7F4EE
- secondary_bg: #EBE6DC
- primary: #1F2A37
- accent: #C0392B
- secondary_accent: #1D6A73
- body_text: #232A31
- secondary_text: #5A6068
- divider: #D5CEC2
- surface: #FFFFFF
- grid: #E4DED3
- block_shade: #E0D9CC
- warning: #B26A00

## typography
- font_family: Microsoft YaHei, Arial, sans-serif
- title_family: SimSun, Cambria, serif
- body_family: Microsoft YaHei, Arial, sans-serif
- body: 24
- title: 44
- subtitle: 32
- annotation: 18
- cover_title: 88
- chapter_title: 56
- chapter_numeral: 160
- lead: 28
- data: 64
- footnote: 16

## icons
- library: chunk-filled
- inventory: chunk-filled/envelope, chunk-filled/fish, chunk-filled/triangle-exclamation, chunk-filled/shield-check, chunk-filled/key, chunk-filled/keyhole, chunk-filled/user, chunk-filled/users, chunk-filled/building, chunk-filled/eye, chunk-filled/clock, chunk-filled/hourglass-half-top, chunk-filled/phone, chunk-filled/comment, chunk-filled/magnifying-glass, chunk-filled/laptop, chunk-filled/wifi, chunk-filled/mobile, chunk-filled/floppy-disk, chunk-filled/arrow-up-from-bracket, chunk-filled/database, chunk-filled/book, chunk-filled/bug, chunk-filled/link, chunk-filled/circle-x, chunk-filled/circle-checkmark, chunk-filled/megaphone, chunk-filled/clipboard, chunk-filled/trash

## page_rhythm
- P01: anchor
- P02: anchor
- P03: anchor
- P04: dense
- P05: dense
- P06: dense
- P07: breathing
- P08: anchor
- P09: dense
- P10: dense
- P11: dense
- P12: dense
- P13: breathing
- P14: anchor
- P15: dense
- P16: breathing
- P17: dense
- P18: breathing
- P19: anchor
- P20: dense
- P21: dense
- P22: dense
- P23: dense
- P24: anchor
- P25: dense
- P26: dense
- P27: breathing
- P28: anchor

## page_visualizations
- P04: chart/pie_chart
- P05: chart/column_chart
- P06: table/record_table
- P09: table/comparison_matrix
- P12: chart/horizontal_bar_chart
- P16: chart/donut_chart
- P20: table/record_table
- P22: table/metric_table
- P26: table/record_table

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 法规和标准只引用公开的正式文本（网络安全法、数据安全法、个人信息保护法、GB/T 22239 等级保护 2.0 等）并标出条款号和年份 (user)
- 案例只用监管部门或 CERT 公开通报过的事件并标来源与年份 (user)

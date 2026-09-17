<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1242 1660
- format: 小红书

## communication
- primary_language: zh-CN
- audience: 中国大陆普通家庭的小红书读者(非医护),多为家里有孩子或老人、想把急救包一次性配齐的人
- objective: 让读者照着四类骨架把急救包配齐、把红药水紫药水与过期药清出去、定下固定位置与 3 个月检查节点,并在割伤或烫伤时按流程处置
- core_message: 急救包不是囤药,是"止血包扎 + 消毒 + 常用药 + 工具"四类齐全、位置固定、每 3 个月一查
- consumption_mode: text

## mode
- mode: custom
- mode_references: instructional
- mode_behavior: 按"先给骨架、再逐类展开、再纠错、再落地、最后两条现场流程与一张总表"的学习顺序推进;页标题写这一页教什么而不写论断;四个同级类别用同一形状与同一深度并列展开;每条处置先给动作、再给参数、再给禁忌注记,注记始终挂在它解释的那一步旁边。

## visual_style
- visual_style: custom
- visual_style_references: sketch-notes, editorial
- visual_style_behavior: sketch-notes 提供质地——暖米纸底、带轻微手抖的黑墨轮廓、略微溢出边线的柔和色块、稀疏手绘装饰与波浪箭头、全平面无投影;editorial 提供竖版层级——眉题、发丝分隔线、贯穿全页的纵向标尺、超大序号或数字作为锚点、非均分的不对称分区。形状与质地归手绘,秩序与层级归编辑排版。

## colors
- background: #FBF6EC
- secondary_bg: #F2E8D5
- primary: #1F6F5C
- accent: #D94F3D
- secondary_accent: #E8A33D
- body_text: #2B2A26
- secondary_text: #6B6558
- divider: #D9CDB8
- surface: #FFFDF7
- block_shade: #EFE3CC
- positive: #3F8F5B
- warning: #E8A33D
- negative: #C0392B
- image_rendering: custom
- image_rendering_references: sketch-notes
- image_rendering_behavior: 手绘教学笔记风格——黑墨轮廓带轻微手抖,色块从墨绿、暖橙、急救红三个角色派生为低饱和柔和平涂并略微溢出轮廓,纸面带 8–12% 纸纹;完全平面,不加投影与渐变;极少量手绘小装饰。九张图共用同一线宽与同一上色错位量。

## typography
- font_family: Microsoft YaHei, Arial, sans-serif
- title_family: SimHei, Arial Black, sans-serif
- body_family: Microsoft YaHei, Arial, sans-serif
- display_family: SimHei, Arial Black, sans-serif
- hero_number_family: SimHei, Arial Black, sans-serif
- annotation_family: Microsoft YaHei, Arial, sans-serif
- footnote_family: Microsoft YaHei, Arial, sans-serif
- body: 44
- title: 80
- subtitle: 56
- annotation: 32
- display: 128
- hero_number: 96
- lead: 52
- kicker: 36
- step_number: 48
- table_cell: 36
- footnote: 26

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/first-aid-kit, tabler-outline/bandage, tabler-outline/vaccine-bottle, tabler-outline/pills, tabler-outline/thermometer, tabler-outline/scissors, tabler-outline/droplet, tabler-outline/flame, tabler-outline/alert-triangle, tabler-outline/trash, tabler-outline/calendar-repeat, tabler-outline/clock-hour-3, tabler-outline/phone-call, tabler-outline/ban, tabler-outline/hand-stop, tabler-outline/mask, tabler-outline/shield-check, tabler-outline/cut, tabler-outline/tools, tabler-outline/bottle, tabler-outline/stethoscope, tabler-outline/medical-cross, tabler-outline/snowflake, tabler-outline/bath, tabler-outline/clipboard-list, tabler-outline/home, tabler-outline/bulb, tabler-outline/emergency-bed, tabler-outline/circle-number-1, tabler-outline/circle-number-2, tabler-outline/circle-number-3, tabler-outline/circle-number-4, tabler-outline/circle-number-5, tabler-outline/arrow-narrow-right

## images
- p01: images/cover_kit.jpg | source=ai | crop=adaptive
- p02_bandage: images/kit_bandage.jpg | source=slice | crop=no-crop
- p02_antiseptic: images/kit_antiseptic.jpg | source=slice | crop=no-crop
- p02_medicine: images/kit_medicine.jpg | source=slice | crop=no-crop
- p02_tools: images/kit_tools.jpg | source=slice | crop=no-crop
- p05_old_drugs: images/no_old_drugs.jpg | source=slice | crop=no-crop
- p06_storage: images/kit_storage.jpg | source=slice | crop=no-crop
- p07_press: images/cut_press.jpg | source=slice | crop=no-crop
- p08_water: images/burn_water.jpg | source=slice | crop=no-crop

## page_rhythm
- P01: anchor
- P02: anchor
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: anchor

## page_visualizations
- P09: table/record_table

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
- 插图要手绘感的 AI 插画,别用实拍照片 (user)

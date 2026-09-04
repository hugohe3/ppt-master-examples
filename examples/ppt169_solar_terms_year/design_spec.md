<!-- ppt-master-schema: design-spec/v1 -->
# 二十四节气·全年手账 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | 二十四节气·全年手账（solar_terms_year） |
| Canvas Format | ppt169 · 1280×720 |
| Page Count | 31 |
| Primary Language | zh-CN |
| Target Audience | 对二十四节气有兴趣的普通读者、家长与中小学教师：叫得出节气名，但记不住日期、说不清三候出处，也不确定“今天该做点什么” |
| Communication Intent | 先给一张全年的时间地图，再逐个节气交付可查的事实（交节时刻／三候原文／一条习俗），最后交出全部来源；教在前、记录归档在后 |
| Desired Audience Outcome | 读者能在一年中的任意一天翻到当天所属的节气页，说出交节时刻、复述三候、挑出一条当天可做的事，并能顺着来源页核对每条事实 |
| Core Message / Ask / Action | 二十四节气是一套精确到分钟的时间系统，也是一本可以照着过的一年生活手账 |
| Delivery Context | 读者主导自读为主（手账式长卷，逐页可单独查阅或打印）；无现场讲者；全年随时翻阅，无时间约束 |
| Artifact Afterlife | 归档与复用：逐页可单独打印夹进本子，来源页支撑事实复核 |
| Reading Mode | balanced |
| Content Strategy | 未提出材料取舍约束，取均衡默认：以研究对中的事实为准重新架构成手账体例，事实一律沿用来源，不外扩 |
| Design Style | 圆角手账（instructional × soft-rounded）：圆角卡片＋柔和抬升＋pill 标签＋大色块出血，四季四个语义色，其余系统整卷不变 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | disabled — final Stage-2 proactive policy: 读者主导的可打印手账，无讲者通道，全部必要含义留在页面上 |
| Custom Animations | enabled — explicit user instruction (object-level motion required: ≥4 pairs of Morph plus entrance choreography) |
| Narration Audio | disabled — final Stage-2 proactive policy |
| Created Date | 2026-09-04 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | ppt169 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 64 px 四边 |
| Content Area | x 64–1216, y 64–656（页脚带 y 656–700 为页码与季标） |

## III. Visual Theme

### Theme Style

- **Mode**: instructional
- **Visual style**: soft-rounded
- **Theme**: 一本可以翻一年的纸质手账——暖白纸底上浮着一叠圆角卡片，四季各占一个语义色，年轮环是贯穿整卷的连续母题（连续职责：让任意一页都能被定位回全年的哪一格；复用方式：封面与总览为完整环，四季分隔页为该季 1/4 弧，节气页缩为右上角的小环＋指针）
- **Tone**: 温和、笃定、有生活气；讲事实时精确到分钟，讲怎么过时说人话

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FBF8F3 | 暖白纸底，整卷唯一页面底色 |
| Secondary background | #FFFFFF | 圆角卡片面，靠柔和抬升与底色拉开 |
| Primary | #7A5C3E | 手账皮革棕：页眉页脚、环线、标题前缀、结构性线条 |
| Accent | #7A5470 | 梅紫：当前指针、超链接、跨页强调；与四季色都不同族，永不与季色抢义 |
| Secondary accent | #9C8B7A | 暖灰褐：刻度、pill 描边、次级分隔 |
| Body text | #3A332C | 正文与三候原文 |
| Secondary text | #8A8078 | 注释、来源标注、页脚 |
| Divider | #E3DACB | 卡片边界与分组细线 |
| Surface | #FFFFFF | 卡片抬升面（soft-rounded 的层次锚） |
| Grid | #EFE8DC | 比 divider 更淡的网格／年轮细刻度 |
| Scrim | #2E2A26 | 大色块出血或图上压字时的低透压暗层 |
| Season · Spring | #6FA46B | 春季语义色（P03 与 P04–P09） |
| Season · Summer | #CC5B4C | 夏季语义色（P10 与 P11–P16） |
| Season · Autumn | #D99A2B | 秋季语义色（P17 与 P18–P23） |
| Season · Winter | #5C7FA3 | 冬季语义色（P24 与 P25–P30） |

### AI Image Strategy

- **Image Rendering**: flat
- **Visual**: 减法造型的扁平矢量：圆润轮廓、无描边或极粗的同色描边、2–3 个平涂色域＋一层更浅的同色块做体积，无渐变、无投影、无透视；物象只保留最能被认出的两三个特征
- **Mood**: 像一套纸质节气日历上的小图标，或无印良品季节手账内页的插图——安静、可爱但不幼稚

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 中文黑体／中性无衬线，字面开阔、笔画等粗，让圆角卡片自己说圆 | Microsoft YaHei | Trebuchet MS | sans-serif |
| Body | 同族无衬线，正文与三候原文同一质地 | Microsoft YaHei | Trebuchet MS | sans-serif |
| Data | 人文无衬线，等高数字（lining figures），专用于日期与交节时刻 | Trebuchet MS | Trebuchet MS | sans-serif |

- **Title stack**: `Microsoft YaHei, sans-serif`
- **Body stack**: `Microsoft YaHei, sans-serif`
- **Data stack**: `Trebuchet MS, sans-serif`
- **Role rationale**: Data 单列一族，因为交节时刻是整卷 24 页都出现的重复角色，必须用等高数字；Microsoft YaHei 的西文数字在小字号下与中文混排重心不稳。Title 与 Body 同族是刻意的 concord：整卷的性格由 24 张 AI 题字（display 层）和圆角几何承担，原生标题保持中性、可搜索、可编辑。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 44 |
| Subtitle | 32 |
| Annotation | 18 |
| Display | 96 |
| Chapter title | 56 |
| Lead | 30 |
| Data | 40 |
| Quote | 26 |
| Footnote | 16 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 节气页从左上的题字＋原生标题起手，向右下依次交出“什么时候（时刻）→ 古人看见什么（三候）→ 今人做什么（时令＋怎么过）”；总览与分隔页反过来，先给整体图形再落到文字
- **Composition tendency**: 圆角卡片叠在暖白纸底上，靠柔和抬升而非描边分层；半径家族整卷统一为 12／24／40 三档（pill 与小标签 12，内容卡 24，出血大板 40），任何页不引入第四档；每季六页在“左图右文／上题下三栏／大板出血／环形定位／对角错落／满幅卡阵”之间轮换，四季轮换顺序一致，使同季第 n 页与另一季第 n 页构图呼应
- **Cross-page continuity**: 页眉左侧季名＋节气序号、右上角年轮小环＋指针、页脚右侧页码与来源提示，24 个节气页完全一致；变化的只有季语义色、题字、主视觉与内容
- **Spacing posture**: variable by page rhythm——分隔页与封面 breathing，节气页 dense，总览与来源页 anchor
- **Spacing anchors**: page margin 64；block gap 28；column gutter 32；corner radius 24；body leading 38

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-filled

| Icon Path | Suitable Scenarios |
| --- | --- |
| tabler-filled/clock | 交节时刻的时间标记 |
| tabler-filled/calendar | 公历日期标记 |
| tabler-filled/sun | 昼长、日照、太阳高度相关标记 |
| tabler-filled/moon | 夜长与冬季页的对照标记 |
| tabler-filled/leaf | 春季与草木物候标记 |
| tabler-filled/flame | 夏季与暑热标记 |
| tabler-filled/droplet | 降水、露、雨相关物候标记 |
| tabler-filled/cloud | 冬季与霜雪、云气标记 |
| tabler-filled/feather | 候鸟类物候标记 |
| tabler-filled/bug | 虫类物候标记 |
| tabler-filled/soup | 时令饮食标记 |
| tabler-filled/bowl | 时令饮食的第二种载体 |
| tabler-filled/book | 出处与文献标记 |
| tabler-filled/link | 来源页的外链标记 |
| tabler-filled/star | 三候序号与要点标记 |
| tabler-filled/map-pin | 年轮上的当前定位标记 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P02 | chart | line_chart | 用 12 个中气日的太阳上中天仰角画出一年的太阳高度曲线，给全年总览一条可读的量化脊梁 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| elem_lichun.png | 310x308 | 1:1 | 立春页主视觉：解冻的东风与初芽 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_spring_elements.png; treatment=slice; | none | local |
| elem_yushui.png | 326x282 | 1.16:1 | 雨水页主视觉：獭与初萌的草木 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_spring_elements.png; treatment=slice; | none | local |
| elem_jingzhe.png | 309x310 | 1:1 | 惊蛰页主视觉：桃花与惊醒的虫 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_spring_elements.png; treatment=slice; | none | local |
| elem_chunfen.png | 251x305 | 0.82:1 | 春分页主视觉：竖起的蛋与燕子 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_spring_elements.png; treatment=slice; | none | local |
| elem_qingming.png | 308x308 | 1:1 | 清明页主视觉：青团与柳枝 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_spring_elements.png; treatment=slice; | none | local |
| elem_guyu.png | 309x294 | 1.05:1 | 谷雨页主视觉：新茶与香椿 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_spring_elements.png; treatment=slice; | none | local |
| elem_lixia.png | 314x312 | 1:1 | 立夏页主视觉：称与立夏蛋 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_summer_elements.png; treatment=slice; | none | local |
| elem_xiaoman.png | 260x296 | 0.88:1 | 小满页主视觉：将满的麦穗与苦菜 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_summer_elements.png; treatment=slice; | none | local |
| elem_mangzhong.png | 312x317 | 0.98:1 | 芒种页主视觉：青梅与带芒的麦 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_summer_elements.png; treatment=slice; | none | local |
| elem_xiazhi.png | 287x309 | 0.93:1 | 夏至页主视觉：过水面与最短的影 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_summer_elements.png; treatment=slice; | none | local |
| elem_xiaoshu.png | 319x311 | 1.03:1 | 小暑页主视觉：新米碗与蟋蟀 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_summer_elements.png; treatment=slice; | none | local |
| elem_dashu.png | 286x323 | 0.89:1 | 大暑页主视觉：仙草碗与萤火 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_summer_elements.png; treatment=slice; | none | local |
| elem_liqiu.png | 337x315 | 1.07:1 | 立秋页主视觉：西瓜与凉风 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_autumn_elements.png; treatment=slice; | none | local |
| elem_chushu.png | 360x310 | 1.16:1 | 处暑页主视觉：鸭与河灯 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_autumn_elements.png; treatment=slice; | none | local |
| elem_bailu.png | 338x316 | 1.07:1 | 白露页主视觉：草叶露珠与茶壶 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_autumn_elements.png; treatment=slice; | none | local |
| elem_qiufen.png | 337x333 | 1:1 | 秋分页主视觉：秋汤与月 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_autumn_elements.png; treatment=slice; | none | local |
| elem_hanlu.png | 324x248 | 1.31:1 | 寒露页主视觉：菊与芝麻 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_autumn_elements.png; treatment=slice; | none | local |
| elem_shuangjiang.png | 334x322 | 1.04:1 | 霜降页主视觉：柿子与霜 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_autumn_elements.png; treatment=slice; | none | local |
| elem_lidong.png | 336x274 | 1.23:1 | 立冬页主视觉：饺子与初冰 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_winter_elements.png; treatment=slice; | none | local |
| elem_xiaoxue.png | 334x272 | 1.23:1 | 小雪页主视觉：咸菜坛与鱼干 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_winter_elements.png; treatment=slice; | none | local |
| elem_daxue.png | 317x295 | 1.07:1 | 大雪页主视觉：腌肉与雪 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_winter_elements.png; treatment=slice; | none | local |
| elem_dongzhi.png | 311x288 | 1.08:1 | 冬至页主视觉：饺子汤圆与回头的太阳 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_winter_elements.png; treatment=slice; | none | local |
| elem_xiaohan.png | 345x306 | 1.13:1 | 小寒页主视觉：菜饭锅与喜鹊 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_winter_elements.png; treatment=slice; | none | local |
| elem_dahan.png | 314x309 | 1.02:1 | 大寒页主视觉：扫帚与厚冰 | Illustration | 作为该页唯一的具象锚点，与题字构成左上／右侧的一组，不与文字重叠 | no-crop | slice | Generated | Derived from sheet_winter_elements.png; treatment=slice; | none | local |
| word_lichun.png | 381x189 | 2.02:1 | 立春 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_a.png; treatment=slice; | embedded | local |
| word_yushui.png | 379x186 | 2.04:1 | 雨水 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_a.png; treatment=slice; | embedded | local |
| word_chunfen.png | 384x188 | 2.04:1 | 春分 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_a.png; treatment=slice; | embedded | local |
| word_qingming.png | 377x192 | 1.96:1 | 清明 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_a.png; treatment=slice; | embedded | local |
| word_guyu.png | 380x182 | 2.09:1 | 谷雨 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_a.png; treatment=slice; | embedded | local |
| word_lixia.png | 662x300 | 2.21:1 | 立夏 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_a.png; treatment=slice; | embedded | local |
| word_xiaoman.png | 379x190 | 1.99:1 | 小满 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_a.png; treatment=slice; | embedded | local |
| word_mangzhong.png | 377x194 | 1.94:1 | 芒种 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_b.png; treatment=slice; | embedded | local |
| word_xiazhi.png | 371x200 | 1.85:1 | 夏至 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_b.png; treatment=slice; | embedded | local |
| word_xiaoshu.png | 380x202 | 1.88:1 | 小暑 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_b.png; treatment=slice; | embedded | local |
| word_dashu.png | 380x201 | 1.89:1 | 大暑 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_b.png; treatment=slice; | embedded | local |
| word_liqiu.png | 384x192 | 2.00:1 | 立秋 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_b.png; treatment=slice; | embedded | local |
| word_chushu.png | 380x202 | 1.88:1 | 处暑 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_b.png; treatment=slice; | embedded | local |
| word_bailu.png | 365x202 | 1.81:1 | 白露 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_b.png; treatment=slice; | embedded | local |
| word_qiufen.png | 385x194 | 1.98:1 | 秋分 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_b.png; treatment=slice; | embedded | local |
| word_hanlu.png | 390x209 | 1.87:1 | 寒露 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_c.png; treatment=slice; | embedded | local |
| word_shuangjiang.png | 396x204 | 1.94:1 | 霜降 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_c.png; treatment=slice; | embedded | local |
| word_lidong.png | 394x204 | 1.93:1 | 立冬 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_c.png; treatment=slice; | embedded | local |
| word_xiaoxue.png | 394x200 | 1.97:1 | 小雪 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_c.png; treatment=slice; | embedded | local |
| word_daxue.png | 390x200 | 1.95:1 | 大雪 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_c.png; treatment=slice; | embedded | local |
| word_dongzhi.png | 393x206 | 1.91:1 | 冬至 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_c.png; treatment=slice; | embedded | local |
| word_xiaohan.png | 394x206 | 1.91:1 | 小寒 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_c.png; treatment=slice; | embedded | local |
| word_dahan.png | 389x207 | 1.88:1 | 大寒 的手写题字（display 层） | Lettering | 置于原生标题之上或之左，作 display 层；原生标题与副标题独立存在，保证可搜索可编辑 | no-crop | slice | Generated | Derived from sheet_lettering_c.png; treatment=slice; | embedded | local |
| orn_ring.png | 400x400 | 1:1 | 装饰母题：年轮圆环 | Illustration | 整卷复用的装饰件，只做陪衬，永不承载信息 | no-crop | slice | Generated | Derived from sheet_ornament.png; treatment=slice; | none | local |
| orn_corner.png | 251x148 | 1.70:1 | 装饰母题：角落云纹 | Illustration | 整卷复用的装饰件，只做陪衬，永不承载信息 | no-crop | slice | Generated | Derived from sheet_ornament.png; treatment=slice; | none | local |
| orn_sunmoon.png | 256x206 | 1.24:1 | 装饰母题：日月合符 | Illustration | 整卷复用的装饰件，只做陪衬，永不承载信息 | no-crop | slice | Generated | Derived from sheet_ornament.png; treatment=slice; | none | local |
| orn_divider.png | 258x72 | 3.58:1 | 装饰母题：小分隔花饰 | Illustration | 整卷复用的装饰件，只做陪衬，永不承载信息 | no-crop | slice | Generated | Derived from sheet_ornament.png; treatment=slice; | none | local |

## IX. Content Outline

### Part 1: 开卷

#### Slide 01 - 封面

- **Audience move**: 只知道“节气是个传统说法” → 意识到这是一套精确到分钟、可以照着过一年的系统
- **Relationships**: 主题名与副标题为 parent；“24 格 / 72 候 / 一年”三个数字彼此 membership 于同一个系统；none 之外无其他关系
- **Cover impact**: 钩子（binding）= 精确到分钟这件事本身——用 2026 年立春的“4:02”作为封面上唯一的具体数字，让读者第一眼就知道这不是模糊的老话。Composition（Reference）= 暖白纸面居中偏左的主题字，右侧或下方浮一枚完整年轮环，环上 24 个刻度按四季着色，其中一格被指针点亮
- **Composition**: 大面积留白＋一个视觉主体（原生 display 主题字）＋一个结构主体（年轮环）；不要卡片阵
- **Title**: 二十四节气·全年手账
- **Core message**: 二十四节气是一套精确到分钟的时间系统，也是一本可以照着过的一年生活手账
- **Content**: · 原生完整标题「二十四节气·全年手账」与副标题「2026 年公历日期 · 交节时刻 · 三候 · 时令」· 一行钩子：2026 年的春天始于 2 月 4 日 4:02 · 三个小数字：24 格 / 72 候 / 1 年
- **Images**: orn_ring.png 作年轮环的装饰底；orn_sunmoon.png 作角落陪衬（封面主题字为原生 display 号字，不做题字素材——三张题字母表按锁定计划只承载 24 个节气名）
- **Motion suggestion**: 主题字先落定，年轮环随后从 0 度扫出一整圈并停在立春刻度上；这一圈是全卷的“开卷”动作
- **Fact IDs**: F003, F025
- **page_rhythm**: anchor

#### Slide 02 - 全年总览：一年是一个环

- **Audience move**: 记不住 24 个节气的顺序与分布 → 能在一个环上指出任意节气所在的位置与季节
- **Relationships**: 24 个节气之间为 order（首尾相接的循环）；每 6 个节气 membership 于一个季；四个季彼此 contrast（各占 1/4 弧、各有语义色）；太阳高度序列与 12 个中气 link（每个中气日对应一个仰角值）
- **Composition**: 左侧一枚大年轮环占据主视觉，24 格按四季着色并标名；右侧一栏放太阳高度曲线与三行读法说明；环与曲线共享同一条“一年”的时间轴
- **Title**: 一年是一个环
- **Core message**: 二十四节气不是 24 个孤立的日子，而是黄道上近乎均匀的 24 个位置，一圈正好一年
- **Content**: · 年轮环：24 格按立春起顺时针排列，标节气名与月份，四季四色 · 一句定义：节气是太阳在黄道上到达 24 个既定位置的时刻，含 12 个“中气”与 12 个“节气”，相间排列 · 太阳高度曲线：12 个中气日的太阳上中天仰角（香港），从冬至 44° 升到夏至 89° 再落回 · 一行读法：曲线最高处是夏至，最低处是冬至，两次穿过 68° 的地方是春分与秋分 · 一行背景：2016 年 11 月 30 日列入联合国教科文组织人类非物质文化遗产代表作名录
- **Visualization**: year-sun-altitude = 12 个中气日的太阳上中天仰角折线；年轮环为定性构图，不计入 Chart
- **Native-ready**: year-sun-altitude=yes
- **Images**: 本页年轮环为原生几何（便于作动画端点），不再另置装饰底纹；orn_ring.png 只在封面用一次
- **Motion suggestion**: 年轮环从封面延续（同一个环），随后四季弧依次点亮；曲线由左向右画出
- **Fact IDs**: F074, F075
- **page_rhythm**: anchor

### Part 2: 春 · 立春到谷雨

#### Slide 03 - 春季·Spring

- **Audience move**: 刚读完上一季（或封面总览） → 知道接下来六格属于春季、各自叫什么、这一季的整体走向
- **Relationships**: 六个节气之间为 order；六者 membership 于春季；本季与相邻季 contrast（语义色与物候方向相反）
- **Composition**: 该季语义色的大板从一侧出血占据大半页，季名与起讫日期压在板上；另一侧一排六枚圆角小卡作本季导航，每卡一个节气名＋日期＋主视觉小图；年轮环缩为该季的 1/4 弧
- **Title**: 春 · Spring
- **Core message**: 春天从 2 月 4 日 4:02 开始，六格里草木先动、雷起、雨落
- **Content**: · 季名与英文 · 本季起讫：立春 2月4日 04:02 → 谷雨 4月20日 09:39 · 六格小导航：立春、雨水、惊蛰、春分、清明、谷雨（各带日期与主视觉小图）· 一句本季走向：春天从 2 月 4 日 4:02 开始，六格里草木先动、雷起、雨落
- **Images**: elem_lichun.png 等本季六张主视觉小图并置作导航；orn_corner.png 作角落陪衬
- **Motion suggestion**: 季节色盘（该季语义色的大板）与年轮 1/4 弧是本页与下一页共有的承接物——它们在下一页保留身份、改变位置与大小
- **Fact IDs**: F001, F006
- **page_rhythm**: breathing

#### Slide 04 - 立春

- **Audience move**: 只认得“立春”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 左图右文：题字与主视觉占左三分之一，右侧两栏放三候与时令
- **Title**: 立春 · Start of Spring
- **Core message**: 春天不是暖起来才开始的，是从这一分钟起算的。
- **Content**: · 交节：2026 年 2月4日 04:02（北京时间）· 三候：一候东风解冻／二候蛰虫始振／三候鱼陟负冰（《月令七十二候集解》）· 时令：咬春——吃春饼、赠春盘、品尝春菜；另有鞭土牛的“打春”礼 · 怎么过：买张春饼，把第一口春天咬进嘴里。 · 页眉：春季第 1 格，全年第 1 格
- **Images**: elem_lichun.png 作主视觉；word_lichun.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 承接上一页的季节色盘与年轮 1/4 弧——两者保留身份，色盘收缩为本页的色带或标签底，弧退回右上角的小环并把指针落到本格；随后题字与主视觉进场，三候按一候→二候→三候的顺序依次出现
- **Fact IDs**: F001, F026, F050
- **page_rhythm**: dense

#### Slide 05 - 雨水

- **Audience move**: 只认得“雨水”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 上题下三栏：题字与时刻横贯上方，下方三张等宽圆角卡分别放三候、时令、怎么过
- **Title**: 雨水 · Rain Water
- **Core message**: 降水接替降雪，草木在看不见的地方先动了。
- **Content**: · 交节：2026 年 2月18日 23:52（北京时间）· 三候：一候獭祭鱼／二候候雁北／三候草木萌动（《月令七十二候集解》）· 时令：川西“雨水节，回娘家”，出嫁女儿带礼物回娘家拜望父母 · 怎么过：给爸妈打个电话，或者干脆回一趟家。 · 页眉：春季第 2 格，全年第 2 格
- **Images**: elem_yushui.png 作主视觉；word_yushui.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F002, F027, F051
- **page_rhythm**: dense

#### Slide 06 - 惊蛰

- **Audience move**: 只认得“惊蛰”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 大板出血：该季语义色的大圆角板从右侧出血，主视觉压在板上，文字在左侧纸底上
- **Title**: 惊蛰 · Awakening of Insects
- **Core message**: 雷声是发令枪，蛰伏一冬的都被叫醒。
- **Content**: · 交节：2026 年 3月5日 21:59（北京时间）· 三候：一候桃始华／二候仓庚鸣／三候鹰化为鸠（《月令七十二候集解》）· 时令：惊蛰吃梨，滋阴清肺；“梨”谐“离”，取远离害虫灾病之意 · 怎么过：吃个梨，顺手把冬天积下的灰扫干净。 · 页眉：春季第 3 格，全年第 3 格
- **Images**: elem_jingzhe.png 作主视觉；本页无题字素材——「蛰」字经五次生成仍写成「塾」，该题字资源已取消，标题改由原生 Display 号字承担（整卷唯一一页如此，其余 23 页题字照常）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F003, F028, F052
- **page_rhythm**: dense

#### Slide 07 - 春分

- **Audience move**: 只认得“春分”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 环形定位：右上角年轮小环放大为页面的次主体，三候沿弧线排布
- **Title**: 春分 · Spring Equinox
- **Core message**: 昼夜均分，春天走到正中间。
- **Content**: · 交节：2026 年 3月20日 22:46（北京时间）· 三候：一候玄鸟至／二候雷乃发声／三候始电（《月令七十二候集解》）· 时令：“春分到，蛋儿俏”竖蛋；踏青、放风筝、吃春菜 · 怎么过：找颗新鲜鸡蛋立在桌上，成不成都算春天开场。 · 页眉：春季第 4 格，全年第 4 格
- **Images**: elem_chunfen.png 作主视觉；word_chunfen.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F004, F029, F053
- **page_rhythm**: dense

#### Slide 08 - 清明

- **Audience move**: 只认得“清明”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 对角错落：题字在左上、主视觉在右下，三候与时令沿对角线错落的两张卡
- **Title**: 清明 · Clear and Bright
- **Core message**: 唯一既是节气又是节日的一天：既向后看，也往前走。
- **Content**: · 交节：2026 年 4月5日 02:40（北京时间）· 三候：一候桐始华／二候田鼠化为鴽／三候虹始见（《月令七十二候集解》）· 时令：扫墓祭祖之外有踏青、荡秋千、蹴鞠、插柳；食青团、清明花饼 · 怎么过：出门走一段有树的路，回来蒸一屉青团。 · 页眉：春季第 5 格，全年第 5 格
- **Images**: elem_qingming.png 作主视觉；word_qingming.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F005, F030, F054
- **page_rhythm**: dense

#### Slide 09 - 谷雨

- **Audience move**: 只认得“谷雨”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 满幅卡阵：一张宽卡横贯中部放三候，上下两条窄 pill 放时刻与时令
- **Title**: 谷雨 · Grain Rain
- **Core message**: 雨生百谷，春天把最后一份力气交给土地。
- **Content**: · 交节：2026 年 4月20日 09:39（北京时间）· 三候：一候萍始生／二候鸣鸠拂其羽／三候戴胜降于桑（《月令七十二候集解》）· 时令：南方喝谷雨茶，北方食香椿（亦称“吃春”）；赏牡丹、走谷雨 · 怎么过：泡一杯今年的新茶，或者炒一盘香椿鸡蛋。 · 页眉：春季第 6 格，全年第 6 格
- **Images**: elem_guyu.png 作主视觉；word_guyu.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F006, F031, F055
- **page_rhythm**: dense

### Part 3: 夏 · 立夏到大暑

#### Slide 10 - 夏季·Summer

- **Audience move**: 刚读完上一季（或封面总览） → 知道接下来六格属于夏季、各自叫什么、这一季的整体走向
- **Relationships**: 六个节气之间为 order；六者 membership 于夏季；本季与相邻季 contrast（语义色与物候方向相反）
- **Composition**: 该季语义色的大板从一侧出血占据大半页，季名与起讫日期压在板上；另一侧一排六枚圆角小卡作本季导航，每卡一个节气名＋日期＋主视觉小图；年轮环缩为该季的 1/4 弧
- **Title**: 夏 · Summer
- **Core message**: 夏天从 5 月 5 日 19:49 开始，六格里从将满走到最热
- **Content**: · 季名与英文 · 本季起讫：立夏 5月5日 19:49 → 大暑 7月23日 03:13 · 六格小导航：立夏、小满、芒种、夏至、小暑、大暑（各带日期与主视觉小图）· 一句本季走向：夏天从 5 月 5 日 19:49 开始，六格里从将满走到最热
- **Images**: elem_lixia.png 等本季六张主视觉小图并置作导航；orn_corner.png 作角落陪衬
- **Motion suggestion**: 季节色盘（该季语义色的大板）与年轮 1/4 弧是本页与下一页共有的承接物——它们在下一页保留身份、改变位置与大小
- **Fact IDs**: F007, F012
- **page_rhythm**: breathing

#### Slide 11 - 立夏

- **Audience move**: 只认得“立夏”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 左图右文：题字与主视觉占左三分之一，右侧两栏放三候与时令
- **Title**: 立夏 · Start of Summer
- **Core message**: 夏天开门，万物开始比谁长得快。
- **Content**: · 交节：2026 年 5月5日 19:49（北京时间）· 三候：一候蝼蝈鸣／二候蚯蚓出／三候王瓜生（《月令七十二候集解》）· 时令：立夏称人，祈健康长寿；孩童挂立夏蛋、斗蛋 · 怎么过：上称记一次体重，秋天再称一回。 · 页眉：夏季第 1 格，全年第 7 格
- **Images**: elem_lixia.png 作主视觉；word_lixia.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 承接上一页的季节色盘与年轮 1/4 弧——两者保留身份，色盘收缩为本页的色带或标签底，弧退回右上角的小环并把指针落到本格；随后题字与主视觉进场，三候按一候→二候→三候的顺序依次出现
- **Fact IDs**: F007, F032, F056
- **page_rhythm**: dense

#### Slide 12 - 小满

- **Audience move**: 只认得“小满”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 上题下三栏：题字与时刻横贯上方，下方三张等宽圆角卡分别放三候、时令、怎么过
- **Title**: 小满 · Grain Buds
- **Core message**: 籽粒将满未满——二十四节气里唯一不求圆满的一格。
- **Content**: · 交节：2026 年 5月21日 08:37（北京时间）· 三候：一候苦菜秀／二候靡草死／三候麦秋至（《月令七十二候集解》）· 时令：江南“小满动三车”（水车、榨油车、缫丝车）；吃苦菜 · 怎么过：吃一盘略带苦味的菜，给太满的日子留个余地。 · 页眉：夏季第 2 格，全年第 8 格
- **Images**: elem_xiaoman.png 作主视觉；word_xiaoman.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F008, F033, F057
- **page_rhythm**: dense

#### Slide 13 - 芒种

- **Audience move**: 只认得“芒种”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 大板出血：该季语义色的大圆角板从右侧出血，主视觉压在板上，文字在左侧纸底上
- **Title**: 芒种 · Grain in Ear
- **Core message**: 有芒的麦子要收，有芒的稻子要种，一年最忙的一格。
- **Content**: · 交节：2026 年 6月5日 23:48（北京时间）· 三候：一候螳螂生／二候鵙始鸣／三候反舌无声（《月令七十二候集解》）· 时令：祭花神、饯送花神归位；南方“煮梅” · 怎么过：煮一小锅青梅，把夏天的酸先存起来。 · 页眉：夏季第 3 格，全年第 9 格
- **Images**: elem_mangzhong.png 作主视觉；word_mangzhong.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F009, F034, F058
- **page_rhythm**: dense

#### Slide 14 - 夏至

- **Audience move**: 只认得“夏至”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 环形定位：右上角年轮小环放大为页面的次主体，三候沿弧线排布
- **Title**: 夏至 · Summer Solstice
- **Core message**: 白昼最长的一天，也是白昼开始变短的一天。
- **Content**: · 交节：2026 年 6月21日 16:25（北京时间）· 三候：一候鹿角解／二候蜩始鸣／三候半夏生（《月令七十二候集解》）· 时令：北方“冬至饺子夏至面”，麦收后吃面尝新；女子互赠折扇脂粉 · 怎么过：中午吃碗过水面，量一量自己影子最短的时候。 · 页眉：夏季第 4 格，全年第 10 格
- **Images**: elem_xiazhi.png 作主视觉；word_xiazhi.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F010, F035, F059
- **page_rhythm**: dense

#### Slide 15 - 小暑

- **Audience move**: 只认得“小暑”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 对角错落：题字在左上、主视觉在右下，三候与时令沿对角线错落的两张卡
- **Title**: 小暑 · Minor Heat
- **Core message**: 风里已经没有凉气了，暑天正式开场。
- **Content**: · 交节：2026 年 7月7日 09:57（北京时间）· 三候：一候温风至／二候蟋蟀居壁／三候鹰始击（《月令七十二候集解》）· 时令：“食新”尝新米、祭五谷大神；北方“头伏饺子” · 怎么过：尝一口新米，把伏天的第一顿吃踏实。 · 页眉：夏季第 5 格，全年第 11 格
- **Images**: elem_xiaoshu.png 作主视觉；word_xiaoshu.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F011, F036, F060
- **page_rhythm**: dense

#### Slide 16 - 大暑

- **Audience move**: 只认得“大暑”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 满幅卡阵：一张宽卡横贯中部放三候，上下两条窄 pill 放时刻与时令
- **Title**: 大暑 · Major Heat
- **Core message**: 一年最热的一格，也是萤火虫最多的一格。
- **Content**: · 交节：2026 年 7月23日 03:13（北京时间）· 三候：一候腐草为萤／二候土润溽暑／三候大雨时行（《月令七十二候集解》）· 时令：广东食仙草消暑；陕西安康以酸菜面配油泼辣子开胃 · 怎么过：熬一碗仙草或酸汤，别跟暑气硬扛。 · 页眉：夏季第 6 格，全年第 12 格
- **Images**: elem_dashu.png 作主视觉；word_dashu.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F012, F037, F061
- **page_rhythm**: dense

### Part 4: 秋 · 立秋到霜降

#### Slide 17 - 秋季·Autumn

- **Audience move**: 刚读完上一季（或封面总览） → 知道接下来六格属于秋季、各自叫什么、这一季的整体走向
- **Relationships**: 六个节气之间为 order；六者 membership 于秋季；本季与相邻季 contrast（语义色与物候方向相反）
- **Composition**: 该季语义色的大板从一侧出血占据大半页，季名与起讫日期压在板上；另一侧一排六枚圆角小卡作本季导航，每卡一个节气名＋日期＋主视觉小图；年轮环缩为该季的 1/4 弧
- **Title**: 秋 · Autumn
- **Core message**: 秋天从 8 月 7 日 19:43 开始，六格里暑气退场、露水成霜
- **Content**: · 季名与英文 · 本季起讫：立秋 8月7日 19:43 → 霜降 10月23日 17:38 · 六格小导航：立秋、处暑、白露、秋分、寒露、霜降（各带日期与主视觉小图）· 一句本季走向：秋天从 8 月 7 日 19:43 开始，六格里暑气退场、露水成霜
- **Images**: elem_liqiu.png 等本季六张主视觉小图并置作导航；orn_corner.png 作角落陪衬
- **Motion suggestion**: 季节色盘（该季语义色的大板）与年轮 1/4 弧是本页与下一页共有的承接物——它们在下一页保留身份、改变位置与大小
- **Fact IDs**: F013, F018
- **page_rhythm**: breathing

#### Slide 18 - 立秋

- **Audience move**: 只认得“立秋”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 左图右文：题字与主视觉占左三分之一，右侧两栏放三候与时令
- **Title**: 立秋 · Start of Autumn
- **Core message**: 秋天先在名字里到，暑气还要再赖一阵。
- **Content**: · 交节：2026 年 8月7日 19:43（北京时间）· 三候：一候凉风至／二候白露降／三候寒蝉鸣（《月令七十二候集解》）· 时令：贴秋膘：吃炖肉烤肉以肉贴膘；啃秋：吃西瓜香瓜“咬住秋天” · 怎么过：吃块西瓜把夏天咬住，晚饭可以稍微丰盛一点。 · 页眉：秋季第 1 格，全年第 13 格
- **Images**: elem_liqiu.png 作主视觉；word_liqiu.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 承接上一页的季节色盘与年轮 1/4 弧——两者保留身份，色盘收缩为本页的色带或标签底，弧退回右上角的小环并把指针落到本格；随后题字与主视觉进场，三候按一候→二候→三候的顺序依次出现
- **Fact IDs**: F013, F038, F062
- **page_rhythm**: dense

#### Slide 19 - 处暑

- **Audience move**: 只认得“处暑”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 上题下三栏：题字与时刻横贯上方，下方三张等宽圆角卡分别放三候、时令、怎么过
- **Title**: 处暑 · End of Heat
- **Core message**: “处”是终止：暑气到此打住。
- **Content**: · 交节：2026 年 8月23日 10:19（北京时间）· 三候：一候鹰乃祭鸟／二候天地始肃／三候禾乃登（《月令七十二候集解》）· 时令：吃鸭子补阴益血；庆赞中元、放河灯 · 怎么过：河灯不必真放，给过去的一段事情道个别。 · 页眉：秋季第 2 格，全年第 14 格
- **Images**: elem_chushu.png 作主视觉；word_chushu.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F014, F039, F063
- **page_rhythm**: dense

#### Slide 20 - 白露

- **Audience move**: 只认得“白露”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 大板出血：该季语义色的大圆角板从右侧出血，主视觉压在板上，文字在左侧纸底上
- **Title**: 白露 · White Dew
- **Core message**: 昼夜温差把水汽逼成露珠，秋天开始有实体。
- **Content**: · 交节：2026 年 9月7日 22:41（北京时间）· 三候：一候鸿雁来／二候玄鸟归／三候群鸟养羞（《月令七十二候集解》）· 时令：收清露；饮白露茶——民间有“要喝茶，秋白露”的说法 · 怎么过：早起看一次草叶上的露水，再泡一壶白露茶。 · 页眉：秋季第 3 格，全年第 15 格
- **Images**: elem_bailu.png 作主视觉；word_bailu.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F015, F040, F064
- **page_rhythm**: dense

#### Slide 21 - 秋分

- **Audience move**: 只认得“秋分”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 环形定位：右上角年轮小环放大为页面的次主体，三候沿弧线排布
- **Title**: 秋分 · Autumn Equinox
- **Core message**: 又一次昼夜均分，此后夜比昼长。
- **Content**: · 交节：2026 年 9月23日 08:05（北京时间）· 三候：一候雷始收声／二候蛰虫坏户／三候水始涸（《月令七十二候集解》）· 时令：秋祭月、送秋牛、放风筝；采秋菜与鱼片滚汤，名曰“秋汤” · 怎么过：采点时令青菜滚个汤，白天和黑夜一样长的这天早点睡。 · 页眉：秋季第 4 格，全年第 16 格
- **Images**: elem_qiufen.png 作主视觉；word_qiufen.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F016, F041, F065
- **page_rhythm**: dense

#### Slide 22 - 寒露

- **Audience move**: 只认得“寒露”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 对角错落：题字在左上、主视觉在右下，三候与时令沿对角线错落的两张卡
- **Title**: 寒露 · Cold Dew
- **Core message**: 同样是露，白露还温着，寒露已经凉透。
- **Content**: · 交节：2026 年 10月8日 14:29（北京时间）· 三候：一候鸿雁来宾／二候雀入大水为蛤／三候菊有黄华（《月令七十二候集解》）· 时令：“寒露吃芝麻”养阴防燥；近重阳而登高、赏菊、吃蟹 · 怎么过：找个高处走走，回来吃一勺芝麻。 · 页眉：秋季第 5 格，全年第 17 格
- **Images**: elem_hanlu.png 作主视觉；word_hanlu.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F017, F042, F066
- **page_rhythm**: dense

#### Slide 23 - 霜降

- **Audience move**: 只认得“霜降”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 满幅卡阵：一张宽卡横贯中部放三候，上下两条窄 pill 放时刻与时令
- **Title**: 霜降 · Frost Descent
- **Core message**: 秋天最后一格，草木把颜色一次交还。
- **Content**: · 交节：2026 年 10月23日 17:38（北京时间）· 三候：一候豺祭兽／二候草木黄落／三候蛰虫咸俯（《月令七十二候集解》）· 时令：“霜降摘柿子，立冬打软枣”；民谚“霜降羊肉赛金丹” · 怎么过：买两个软柿子，秋天最后的甜。 · 页眉：秋季第 6 格，全年第 18 格
- **Images**: elem_shuangjiang.png 作主视觉；word_shuangjiang.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F018, F043, F067
- **page_rhythm**: dense

### Part 5: 冬 · 立冬到大寒

#### Slide 24 - 冬季·Winter

- **Audience move**: 刚读完上一季（或封面总览） → 知道接下来六格属于冬季、各自叫什么、这一季的整体走向
- **Relationships**: 六个节气之间为 order；六者 membership 于冬季；本季与相邻季 contrast（语义色与物候方向相反）
- **Composition**: 该季语义色的大板从一侧出血占据大半页，季名与起讫日期压在板上；另一侧一排六枚圆角小卡作本季导航，每卡一个节气名＋日期＋主视觉小图；年轮环缩为该季的 1/4 弧
- **Title**: 冬 · Winter
- **Core message**: 冬天从 11 月 7 日 17:52 开始，六格里天地闭塞又见回头的太阳
- **Content**: · 季名与英文 · 本季起讫：立冬 11月7日 17:52 → 大寒 1月20日 09:45 · 六格小导航：立冬、小雪、大雪、冬至、小寒、大寒（各带日期与主视觉小图）· 一句本季走向：冬天从 11 月 7 日 17:52 开始，六格里天地闭塞又见回头的太阳
- **Images**: elem_lidong.png 等本季六张主视觉小图并置作导航；orn_corner.png 作角落陪衬
- **Motion suggestion**: 季节色盘（该季语义色的大板）与年轮 1/4 弧是本页与下一页共有的承接物——它们在下一页保留身份、改变位置与大小
- **Fact IDs**: F019, F024
- **page_rhythm**: breathing

#### Slide 25 - 立冬

- **Audience move**: 只认得“立冬”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 左图右文：题字与主视觉占左三分之一，右侧两栏放三候与时令
- **Title**: 立冬 · Start of Winter
- **Core message**: 冬是“终”，一年的收藏从今天开始。
- **Content**: · 交节：2026 年 11月7日 17:52（北京时间）· 三候：一候水始冰／二候地始冻／三候雉入大水为蜃（《月令七十二候集解》）· 时令：“立冬补冬，补嘴空”；北方“立冬不端饺子碗，冻掉耳朵没人管” · 怎么过：包一顿饺子，把冬天的门关严。 · 页眉：冬季第 1 格，全年第 19 格
- **Images**: elem_lidong.png 作主视觉；word_lidong.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 承接上一页的季节色盘与年轮 1/4 弧——两者保留身份，色盘收缩为本页的色带或标签底，弧退回右上角的小环并把指针落到本格；随后题字与主视觉进场，三候按一候→二候→三候的顺序依次出现
- **Fact IDs**: F019, F044, F068
- **page_rhythm**: dense

#### Slide 26 - 小雪

- **Audience move**: 只认得“小雪”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 上题下三栏：题字与时刻横贯上方，下方三张等宽圆角卡分别放三候、时令、怎么过
- **Title**: 小雪 · Minor Snow
- **Core message**: 不是一定下雪，是天地开始闭塞。
- **Content**: · 交节：2026 年 11月22日 15:23（北京时间）· 三候：一候虹藏不见／二候天气上升地气下降／三候闭塞而成冬（《月令七十二候集解》）· 时令：“小雪腌菜”：腌咸菜、品糍粑、晒鱼干、吃刨汤、酿小雪酒 · 怎么过：腌一小罐咸菜或晒点鱼干，等它慢慢入味。 · 页眉：冬季第 2 格，全年第 20 格
- **Images**: elem_xiaoxue.png 作主视觉；word_xiaoxue.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F020, F045, F069
- **page_rhythm**: dense

#### Slide 27 - 大雪

- **Audience move**: 只认得“大雪”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 大板出血：该季语义色的大圆角板从右侧出血，主视觉压在板上，文字在左侧纸底上
- **Title**: 大雪 · Major Snow
- **Core message**: 雪不一定更大，但冷是真的更深了。
- **Content**: · 交节：2026 年 12月7日 10:53（北京时间）· 三候：一候鹖鴠不鸣／二候虎始交／三候荔挺出（《月令七十二候集解》）· 时令：“小雪腌菜，大雪腌肉”；打雪仗、赏雪景、进补 · 怎么过：腌块肉挂起来，或者约一顿火锅。 · 页眉：冬季第 3 格，全年第 21 格
- **Images**: elem_daxue.png 作主视觉；word_daxue.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F021, F046, F070
- **page_rhythm**: dense

#### Slide 28 - 冬至

- **Audience move**: 只认得“冬至”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 环形定位：右上角年轮小环放大为页面的次主体，三候沿弧线排布
- **Title**: 冬至 · Winter Solstice
- **Core message**: 黑夜最长的一天，也是阳气回头的那一天。
- **Content**: · 交节：2026 年 12月22日 04:50（北京时间）· 三候：一候蚯蚓结／二候麋角解／三候水泉动（《月令七十二候集解》）· 时令：北方吃饺子——“冬至不端饺子碗，冻掉耳朵没人管”；南方吃汤圆取团圆意 · 怎么过：北方饺子南方汤圆，今天开始白天变长。 · 页眉：冬季第 4 格，全年第 22 格
- **Images**: elem_dongzhi.png 作主视觉；word_dongzhi.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F022, F047, F071
- **page_rhythm**: dense

#### Slide 29 - 小寒

- **Audience move**: 只认得“小寒”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 对角错落：题字在左上、主视觉在右下，三候与时令沿对角线错落的两张卡
- **Title**: 小寒 · Minor Cold
- **Core message**: 名字叫小，实际常常是一年最冷的开头。
- **Content**: · 交节：2026 年 1月5日 16:23（北京时间）· 三候：一候雁北乡／二候鹊始巢／三候雉雊（《月令七十二候集解》）· 时令：福建沿海晒鱼干；北京腊八粥、南京菜饭、东北冰戏 · 怎么过：煮一锅菜饭，把腊味和青菜一起焖上。 · 页眉：冬季第 5 格，全年第 23 格
- **Images**: elem_xiaohan.png 作主视觉；word_xiaohan.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F023, F048, F072
- **page_rhythm**: dense

#### Slide 30 - 大寒

- **Audience move**: 只认得“大寒”这两个字 → 说得出它 2026 年具体哪天几点交节、古人在这十五天里看见了什么、今天自己可以做哪一件事
- **Relationships**: 三候之间为 order（一候→二候→三候，各约五日）；交节时刻、三候、时令三块 membership 于本节气；本页与同季相邻两页 order
- **Composition**: 满幅卡阵：一张宽卡横贯中部放三候，上下两条窄 pill 放时刻与时令
- **Title**: 大寒 · Major Cold
- **Core message**: 最后一格，也是下一轮立春的前一格。
- **Content**: · 交节：2026 年 1月20日 09:45（北京时间）· 三候：一候鸡乳／二候征鸟厉疾／三候水泽腹坚（《月令七十二候集解》）· 时令：扎帚扫屋、洗涤杂物，预备过年；北方吃消寒糕，南方煨鸡汤 · 怎么过：扫一次屋子，把这一年的最后一格填满。 · 页眉：冬季第 6 格，全年第 24 格
- **Images**: elem_dahan.png 作主视觉；word_dahan.png 作题字 display 层（原生标题独立保留）
- **Motion suggestion**: 三候按一候→二候→三候的语义顺序依次出现；主视觉带意图进场，页眉页脚与年轮小环不动
- **Fact IDs**: F024, F049, F073
- **page_rhythm**: dense

### Part 6: 收卷

#### Slide 31 - 来源

- **Audience move**: 读完 24 格，想知道“这些时刻和原文靠不靠谱” → 能逐条点开原始出处自行核对
- **Relationships**: 四类事实（交节时刻／三候原文／习俗时令／背景）与其来源为 link；四类之间 membership 于同一份研究对；两个天文来源之间为 overlap（12 个中气时刻互相印证）
- **Closing impact**: 收束（binding）= “每一条都能点开”——把可核对本身作为这本手账的最后一个卖点，而不是致谢或联系方式。Composition（Reference）= 四张圆角卡按事实类别排列，每卡一行来源名＋一条可点击链接，卡底留一行说明这条来源覆盖了哪些页
- **Composition**: 四卡两列，页底一行整卷统一的口径说明
- **Title**: 每一条都能点开
- **Core message**: 这本手账里的每个时刻、每句三候、每条习俗都有出处，可以逐条核对
- **Content**: · 交节时刻：中国科学院紫金山天文台发布（经荔枝新闻整理），12 个中气时刻另经《香港天文台年曆2026》独立印证，立春时刻另经新华社印证 · 三候原文：《月令七十二候集解》（维基文库）· 习俗与时令：中国气象网“二十四节气”专题，逐节气一页 · 背景：联合国教科文组织人类非物质文化遗产代表作名录 · 一行口径：紫金山天文台为北京时间、香港天文台为香港时间，同属 UTC+8，12 个中气时刻实测完全一致 · 一行用字说明：三候依通行本作“玄鸟”，维基文库本作“元鸟”，字面语义相同
- **Content (links)**: 紫金山天文台交节时刻 → https://finance.sina.com.cn/jjxw/2026-01-05/doc-inhffsfn9506531.shtml ；香港天文台年曆2026 二十四節氣 → https://www.hko.gov.hk/en/gts/astron2026/files/2026SolarTerms24.pdf ；新华社立春时刻 → https://finance.sina.com.cn/jjxw/2026-02-03/doc-inhkpvfi7233217.shtml ；月令七十二候集解 → https://zh.wikisource.org/wiki/%E6%9C%88%E4%BB%A4%E4%B8%83%E5%8D%81%E4%BA%8C%E5%80%99%E9%9B%86%E8%A7%A3 ；中国气象网 二十四节气专题（以立春页为代表） → https://www.cma.gov.cn/ztbd/2025zt/24jq/lichun/index.html ；UNESCO 名录 → https://www.unesco.org/zh/articles/ershisijieqiruxuanrenleifeiwuzhiwenhuayichandaibiaominglu
- **Images**: orn_divider.png 作卡间分隔陪衬
- **Motion suggestion**: 四张卡依次落定，年轮环在角落走完最后一格回到立春，呼应封面
- **Fact IDs**: F001, F026, F050, F074, F075
- **page_rhythm**: anchor

## X. Speaker Notes Requirements

- **Generation**: disabled

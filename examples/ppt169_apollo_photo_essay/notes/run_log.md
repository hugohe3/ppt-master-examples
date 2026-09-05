# 运行日志 — apollo_photo_essay

工程根：`/root/ppt-master/projects/apollo_photo_essay_ppt169_20260904`
路线：Generate PPTX → Default（`workflows/generate-pptx.md` Step 1–7）
确认门：**显式委托**分支（`confirm-surface.md` §1 第一行）——Stage 1 / Stage 2 由执行代理决策并在此记录完整摘要；不启动 `confirm_ui/server.py`，不启动 `svg_editor/server.py`，不伪造任何 UI 回执。

## 时间线

| 时间 | 事件 |
|---|---|
| 13:54 | 读 SKILL.md → attribution_guard 通过（exit 0）→ routing.md → 选定 Generate PPTX / Default |
| 13:54 | Step 1 起：题目型输入，派出一名隔离 topic-research worker（stage 文档 § Execution Context 允许） |
| 13:54–14:05 | 等待期间读完 Step 4 规划核心与 Step 6 执行核心的全部模块（见下「模块阅读」） |
| 14:05 | Step 1 完成：`apollo_photo_essay_research.md` + `.facts.json`，100 条外部事实（F001–F100），11/11 缺口覆盖，契约校验通过（`## Research Brief` 在、无 URL、schema 正确、ID 连续唯一） |
| 14:06 | Step 2 完成：`project_manager.py init apollo_photo_essay --format ppt169` → 工程根；`import-sources` 导入 research pair |
| 14:07 | Step 3 完成：委托分支，候选边界留在上下文，不写 `template_options.json`，不读任何模板 |

## Step 1 — topic-research

- 执行方式：隔离 worker（保证原始网页内容不进主上下文）。
- 产出：11 项缺口全覆盖，0 未决；100 条外部事实，41 个唯一 `source_url`（NASA 任务页 / NASA History / JSC 照片数据库 / NASA Science / LPI 样品图集 / 英文维基 / 中文维基译名）。
- **worker 报回 8 处材料冲突，本卷的裁决全部记录在下方「冲突裁决」。**

## 冲突裁决（执行代理决定，来源：research 的「材料冲突清单」）

| # | 冲突 | 本卷取值 | 理由 |
|---|---|---|---|
| 1 | 阿波罗13号距离纪录是否仍然成立 | 写「保持了半个多世纪」，并在同页写出 2026-04-06 被 Artemis II 打破 | F038 明确时效；写「至今无人更远」会是错的 |
| 2 | Aldrin 下梯照片编号 | **AS11-40-5868**（任务书给的 AS11-40-5875 不是这一张） | F088 为 NASA 官方图文收录 |
| 3 | Tracy's Rock 照片编号 | **AS17-140-21496**（任务书给的 AS17-134-20463 在 JSC 库中无说明，无法证实） | F089 / F090 |
| 4 | 阿波罗17号月球车行驶距离 | **30.5 公里**（NASA 任务页穿越里程口径），页面上标注「NASA 口径」 | 单一权威来源优先；不与 35.7 并列 |
| 5 | 阿波罗17号样品质量 | **110.4 公斤**（NASA 任务页） | 同上 |
| 6 | Cernan 离开月面的日期 | **1972年12月14日 5:40:56 UTC**，页面写明 UTC | 采 NASA 记录并注时区，避免与 12月13日（休斯敦时间）打架 |
| 7 | 阿波罗11号电视观众 | 写区间「约 6 亿–6.5 亿」 | 两个估算并存，写区间不选边 |
| 8 | 阿波罗8号平安夜听众 | 「全球约四分之一的人」（F005） | 与「约十亿」同量级，择一，不并列不相加 |
| 9 | "Houston, we have a problem" | 页面用飞行原话 `Okay, Houston, we've had a problem here`，并在同页注明通行说法出自电影 | F035 |
| 10 | 中文人名异写 | 全卷统一：洛弗尔(Lovell)、大卫·斯科特(Scott)、詹姆斯·艾尔文(Irwin)、阿尔弗莱德·沃尔登(Worden)、尤金·塞尔南(Cernan)、哈里森·施密特(Schmitt) | research 提醒同一人物在不同条目里异写 |
| 11 | 「1,459 天」 | 由 F001 与 F076 推算，**不挂 fact_id**，页面上标「本卷推算」 | executor-base §3「自建框架须说明」 |

## 模块阅读（Step 6 前置 sweep 的实际范围）

规划集：`strategist.md` / `plan-core.md` / `canvas-formats.md` / `strategist-image.md` / `modes/_index.md` + `modes/narrative.md` / `visual-styles/_index.md` + `visual-styles/photo-editorial.md` / `image-renderings/_index.md` / `templates/icons/README.md` / `chart-vocabulary.md` / `table-vocabulary.md` / `confirm-surface.md` / `design_spec_reference.md` / `spec_lock_reference.md`

执行集：`executor-base.md` / `shared-standards-core.md` / `semantic-svg.md` / `preset-shape-vocabulary.md` / `svg-effects.md` / `native-shape-authoring.md` / `executor-image.md` + `image-layout-spec.md` + `image-layout-patterns.md` + `svg-image-embedding.md` + `executor-web-image.md`（Any image 触发）/ `native-data-interface.md` + `executor-table.md` + `executor-visualization.md`（原生表格触发）/ `native-hyperlinks.md`（来源页触发）/ `animations.md` + `customize-animations.md`（Custom Animations 启用）/ `executor-notes.md`（Speaker Notes 启用）/ `image-base.md` + `image-searcher.md`（Step 5）

不触发：`executor-structured.md`（flat）、`executor-chart.md`（无 value-driven 几何）、`native-formula.md`（无数学）、`image-generator.md`（不用 AI 图）、`video-design.md`（非录播/自走）、`pptx-structure-interface.md`（flat）

---

## Step 4 — Stage 1 / Stage 2 决策摘要（显式委托分支，无 UI 回执）

**未启动 `confirm_ui/server.py`，未写 `confirm_ui/` 下任何文件，未生成 `result.json` / `template_selection.json`。** 下面是本应由用户确认、现由执行代理按委托作出的完整决策。

### Stage 1 — 沟通契约 + 模板/自由设计选择

| 字段 | 取值 |
|---|---|
| primary_language | `zh-CN` |
| canvas | `ppt169`（1280×720，来自任务书显式指定，故 init 带 `--format`） |
| audience | 对太空史有兴趣但不是专业读者的中文观众；知道"阿波罗登月"这个名字，记得一两张照片，但说不清这四年里到底发生了几件事 |
| communication_intent | 先让照片建立在场感，再用少量精确的数字把四年串成一条能复述的时间线；"看见"在前、"记住"在后，技术科普不在范围内 |
| audience_outcome | 能说出四个关键时刻（1968 绕月 / 1969 落月 / 1970 事故 / 1972 收尾），知道每张照片是谁在什么时候拍的，并意识到最后一次离开月面已过去半个多世纪 |
| core_message | 1968-12-21 到 1972-12-19，1,459 天，人类九次抵达月球、六次落上去、十二个人走过月面，然后再没有回去 |
| delivery_context | 主要为有主讲人的图片随笔式放映（约十分钟）；次要为会后独立翻阅 |
| artifact_afterlife | 作为 photo-editorial 示例卷入库，可再次放映、引用与拆用 |
| content_divergence | 题目型输入，结构自建；每个数字与日期必须挂得上 fact_id；口径冲突二选一并注明，不并列不相加；自行推算的数字标「本卷推算」 |
| **模板选择** | **`free_design`** —— 任务书显式要求"用 free_design，不套模板"。因此 Step 3 只在上下文里保留候选边界，未读任何 `*_index.json`、未读任何模板 spec/prototype，未运行 `apply-template-workspace`，未调用 `--complete-template-selection` |

### Stage 2 — 完整方案 + 生产机制

| 字段 | 取值 | 说明 |
|---|---|---|
| delivery_purpose（阅读模式） | `presentation` | 图片随笔 + 主讲；文字克制到每页不超过两段短句 |
| mode | `custom`（references: `narrative`） | 见 `spec_lock.md mode_behavior` |
| visual_style | `custom`（references: `photo-editorial`） | 见 `spec_lock.md visual_style_behavior` |
| page_count | **13**（任务书区间 11–13） | 8 页单张满版出血 + 2 页裁形 + 1 页同源放大 + 3 页无照片文字/表格页 |
| color | 深空暗底 + 骨白文字 + 单一锈橙强调 | `#0B0E11 / #161A20 / #E9E4D9 / #D2622B / #6E7B8A / #DAD5CA`，另锚定 `scrim` 与 `surface` 两级中性（photo-editorial 在 plan-core §6.1 表中的规定动作） |
| icons | **D — 无基础图标库** | photo-editorial 的装饰只有细线、编号与图注；图标会与照片争注意力。`library: none`, `inventory: none` |
| typography | 标题 `Times New Roman, SimSun`（衬线）× 正文 `Arial, Microsoft YaHei`（无衬线） | 任务书要求"衬线中文标题 × 无衬线正文（字体单名，能导出）"。每栈只含一个 Latin 面与一个 CJK 面，符合 `plan-core.md` §6.2；无通用族尾巴 |
| body_size | 30 | `presentation` 在 ppt169 的建议带是 28–32；取 30 给中文长行留余量 |
| image_usage | `["web"]` | **不含 `ai`** |
| image_ai_path | 不适用 | 无 AI 图 → §III 不写 AI Image Strategy，Step 5 不加载 `image-generator.md` |
| generation_mode | `continuous` | 单会话连画，跨页一致性是本卷主轴 |
| refine_spec | `false` | |
| design_spec_depth | `brief` | 同一代理写规划也画页 |
| proactive_speaker_notes | `true` | 工作流默认 |
| proactive_custom_animations | `true` | **用户显式要求**，覆盖默认 `false` |
| proactive_narration_audio | `false` | 工作流默认 |

### 三个方向与被选中的那个（`design_directions.selected` 的等价记录）

Stage-2 契约要求三个"在设计上就明显不同"的完整方案。任务书已把 `visual_style = photo-editorial`、`mode = narrative`、`image_usage = web`、画布与语言全部钉死，按 `strategist.md` §d "Where authoritative truth fixes components, the open ones carry the difference"，差异只能由**开放分量**承载：色彩、字体、以及照片处理层的分配策略。

- **方向 0「档案室」**：冷灰蓝底 + 白字 + 无强调色；标题与正文同族无衬线；所有照片一律去饱和成近单色，靠统一的灰调把十张不同年代的照片拉到一个平面上。*未选*——去饱和会杀掉《地出》和《蓝色弹珠》唯一的说服力（那两张的全部重量就在颜色上），且与任务书"照片质量先行"直接冲突。
- **方向 1「深空画报」（选中）**：深空暗底 + 骨白衬线标题 × 无衬线正文 + 单一锈橙强调；照片全部保留原色满版出血，处理层按页面职能分配（scrim 压字 6 页、几何裁形 2 页、同源放大 1 页、单色派生 1 页），单色只留给事故页做情绪断层。*选中*——它让照片自己说话，处理层每次出现都有一个具体的页面任务，且"单色"因为只用一次而变成了叙事标点而不是滤镜。
- **方向 2「白纸画册」**：纸白底 + 黑字 + 细黑框；照片一律加纸框与细线派生，不出血，像贴在画册上；标题用大号衬线居中。*未选*——纸框会让每张照片缩到画幅的六成，与"少而满版、照片本身要能撑住整页"相反；而且十三页里有八页要出血，白底会让暗部照片和页面之间出现硬边。

**image_strategy（三个候选各一份，按 `strategist-image.md` §2 无论是否选 `ai` 都要写）**：三个方向的 rendering 候选分别是「档案灰阶纪实」「原色纪实、处理层按职能分配」「画册纸面纪实」，均为 `custom`。因为最终 `image_usage` 不含 `ai`，这三个候选只作为推荐留在此处，不进 `spec_lock.md`，也不写 §III `AI Image Strategy`。

### Gate 1 / Gate 2

- **Gate 1（Design Spec 对齐上面这份最终状态）**：逐字段比对通过。13 页 = §I Page Count = §IX 条目数；`presentation` / `free_design` / `web` / `continuous` / `brief` / notes-on / animations-on / narration-off 全部落到 §I；photo-editorial 要求的 `scrim` 中性层落到 §III；`icons: none` 落到 §VI 且 §VI 表为空；无 `ai` 行故 §III 不写 AI Image Strategy、§VIII 无 `text_policy` / `page_role` 值。
- **Gate 2（lock 对齐 Design Spec）**：`project_manager.py validate` → `[OK] Project structure is valid, with warnings`（唯一 warning 是 `svg_output` 为空，属预期）。

---

## Step 5 — 图片获取

- 10 个 `web` 行 + 1 个派生行。**无 AI 图**（`image_usage: ["web"]`），故未加载 `image-generator.md`。
- 一次 `--batch --save-candidates`（`--concurrency 2`，全部 `provider: wikimedia`）→ 10 行 `Needs-Selection`；本代理有视觉能力，按 `web-image-review.md` 的门序本地评审 10 张 review sheet，未另派 reviewer。
- **搜索调用统计**：批量搜索 2 次（首轮 10 行 / 二轮 3 行）+ 单行搜索 2 次（`01_launch` 第 2 页、`01_launch` 换 query 重开池）= 共 4 次检索调用；**采用 10 张**（候选池累计约 130 张缩略图，采用率 8%）。
- **两行走了替换阶梯**：
  - `01_launch`：page 1 全是塔架／围观／VIP 照，无升空瞬间 → page 2（池尽）仍无 → 换 query 重开池，得到的全是竖幅。**决定改用阿波罗17号夜间发射（GPN-2000-001150，3000×2252 横幅）作封面**，把阿波罗11号升空移到 P13 来源页做圆形裁切。封面因此是"最后一次离开"，正文从第一次开始——图注写明了这个安排。
  - `08_schmitt_boulder`：`AS17-140-21496` 单帧在 Wikimedia 上不存在，只有 2025 年的双帧拼接全景。改用 NASA 官方单帧 **S73-22871**，并同步修了 §VIII / §IX / P13 编号清单。
- 派生：`image_treat.py … --desaturate 1 --contrast 1.18` → `06_apollo13_sm_mono.jpg`；母本 `06_apollo13_sm.jpg` 标 `Type: Source`，不上页。
- `image_sources.json` 11 条记录齐全，`license_tier` 全部 `no-attribution`（NASA / Public Domain）。**署名不是强制的，但任务书要求页面上小字署名，13 页全部照做。**

## Step 6 — 执行

- **未启动 `svg_editor/server.py`**（任务书显式禁止）。Design Parameter Confirmation 里如实声明了这一点，没有静默跳过。
- P01 前跑 `text_measure.py calibrate --outline`；据其输出把 `display` 锚点从 96 下调到 78（96 在 L 形文字栏里放不下两行中文标题），并补 `display_family: Times New Roman, SimSun`（原先 `display` 会继承 Body 栈变成无衬线，与 §IV 的意图不符）。两处改动同步回 `design_spec.md §IV`。
- **早期门（P05 后）**：2 blocking + 5 advisory。两条 blocking 同源同向 → 判定为**方法级**，见 `friction.md` 第 1 条；全卷改用 ×1.25 的 Latin/DIGITS 修正后继续。
  - `gate-signal: method=Times New Roman/SimSun 栈 Latin+DIGITS 行宽低估约 18% | page-local=1 | not-exercised=原生表格、原生超链接、preset 几何、同源放大裁切、单色派生页`
- **终检轮次**：共 3 轮。
  1. 1 blocking（`p10-lens` ↔ `p10-body` bounds 重叠）+ 9 advisory
  2. 1 blocking（放宽 `p11-days` bounds 后与 `mission-ledger` 重叠 2px）+ 4 advisory
  3. **0 error**，3 advisory（全部是同一条 image 文件体积提示，见 friction 第 3 条）
- 每轮 checker 调用都跟在一个门点或一次合并修复之后，没有逐条修完就跑。

## 载体收据复核（终检 `[CARRIERS]`，非配额）

```
Pages 13 | text 122 | images 11 | icons 0
Geometry: SVG elements 57 | native presets 1 | page-frame elements 25 | marker uses 1
Effects: inline emphasis 15 (pages 9) | gradients 6 (pages 6) | filters 0 | text effects 0
Native objects: charts 0 | tables 1 | formulas 0
Presets: arc x1
Largest image-frame share on image pages: 15.7%–100.0%
```

**Absence needs a reason** —— 逐条给出替代载体与理由：

| 收据事实 | 由什么承担 | 为什么这样对读者更好 |
|---|---|---|
| `filters 0` | 6 道方向性 scrim + 3 块实色卡片／色带 | photo-editorial §4 是明写的："Flat — no decorative shadows"，唯一例外就是压字用的 scrim。阴影或发光会成为页面上第一个与照片争注意力的东西；而滤镜本来要解决的"可读性"这件事，这里由压在文字底下的 scrim 和卡片直接解决，更准也更轻 |
| `text effects 0` | 15 处 inline emphasis（9 页）+ 单一锈橙强调色 | 本卷的文字侧被定义为"安静的一侧"（§III Tone）。描边、渐变或图片填充的标题会让字去和照片抢，而这正是任务书点名要避免的失败模式 |
| Presets 家族 **carrier and field = 0** | 照片本身 + 发丝线／实色卡片构成的编辑式版面场 | 风格禁止在内容外面套容器（"nothing competes with the image"）。plaque / frame / snipRect 一类承载轮廓会把卡片语言带回来。唯一真正需要轮廓的地方（P04 的异形照片裁切）做成了图片自身的多边形 clip —— 那是图片几何，不是画出来的容器 |
| **direction and sequence = 0** | 页序 + 整卷复用并逐页改写的任务章标（Morph 承接物）+ P08 的 `arc` preset 与 1 个 marker 箭头 | 顺序已经由页序和章标说清楚了，再画箭头是重复陈述。全卷唯一真正是"空间方向"的关系是阿波罗13号的去—绕—回，它就是被画出来的那一个 |
| **grouping and ownership = 0** | P03 的分栏竖发丝线、P11 的表头规则线 | 这两页的分组密度用规则线正好，bracket / brace / plaque 在这个信息量下比内容还重 |
| **emphasis and annotation = 0** | P10 的圆形同源放大镜（含引线与标记环）+ 3 张浮动图注卡 | 注释这件事已经由放大镜和图注卡完成。callout preset 会在一张月面纪实照片上加一个对话气泡尾巴 |
| 11 页的 `Relationships` 写了 order / contrast / link / membership，但只有 1 页画了 preset | 邻接、章标连续性、把文字绑到图上的 scrim | 照片页上的关系是"照片"与"指着它的那句话"之间的关系，靠位置与连续性承担就够了。两处**真正是空间关系**的（P08 的往返轨迹、P10 的尺度对比）恰好就是拿到几何的那两页 |
| `Largest image-frame share 15.7%` | P13 来源页的圆形照片 | 来源页的主角是可点的链接清单，照片在那里是视觉句号，不是证据 |

无与既定决策矛盾之处，未因此重跑 checker。

## Step 7 — 导出

严格串行，每条命令单独一次调用：

1. `total_md_split.py` → `notes/` 下 13 个分页讲稿，覆盖全部 13 页 ✓
2. `finalize_svg.py` → `svg_final/` 13 份自包含预览（8.8 MB，11 张图内嵌）✓
3. `svg_to_pptx.py <project> --native-charts-and-tables` —— 附加 `--native-charts-and-tables` 是因为任务书显式要求"任务一览做原生表格"；`animations.json` 由导出器自动读取。
   `[POSTFLIGHT] status=passed-with-warnings quality_gate=passed slides=13 warning_categories=1`，3 条 warning 即终检那 3 条图片体积 advisory。

**成品回读校验**（解包 PPTX 核对）：13 张幻灯片全部带 `p:timing`（371 个动画节点）；5 张带 morph 过渡（slide 3/5/6/10/12）；13 处 `!!` 选择窗格命名（`!!era-mark` 9 处、`!!page-title` 4 处）；`a:tbl` 原生表格在场；4 个 `hlinkClick` 超链接；11 张图片，`ppt/media` 共 11 MB（11 张原图合计约 28 MB，导出器按 2560 上限重编码过）。

## 事实抽查 10/10

逐条把页面上的数字回对 `sources/apollo_photo_essay_research.facts.json`：

| # | 页 | 页面上的值 | fact | 结果 |
|---|---|---|---|---|
| 1 | P02 | AS08-14-2383 / 1968.12.24 16:39:39.3 UTC / William Anders | F008 | ✓ |
| 2 | P03 | 绕月 10 圈 · 约 20 小时 | F003 | ✓ |
| 3 | P04 | 着陆 1969.07.20 20:17:40 UTC | F015 | ✓ |
| 4 | P04 | 第一步 1969.07.21 02:56:15 UTC | F017 | ✓ |
| 5 | P05 | 舱外活动 2 小时 31 分 40 秒 | F019 | ✓ |
| 6 | P06 / P11 | 带回样品 21.5 公斤 | F020 | ✓ |
| 7 | P07 | 经过 55:54:53 → 1970.04.14 03:08 UTC | F033 | ✓ |
| 8 | P08 | 400,171 公里；2026.04.06 被 Artemis II 以 252,756 英里打破 | F037 / F038 | ✓ |
| 9 | P09 | 27.9 公里 · 空车 210 公斤 · 设计最高时速 10 公里 | F049 / F051 / F052 | ✓ |
| 10 | P10 | 三次月面行走 22 小时 4 分 · 月球车穿越 30.5 公里（NASA 口径） | F065 / F066 | ✓ |
| + | P11 | 24 人到过月球 / 12 人踩上月面 / 382 公斤 / 254 亿美元（1973 年美元） | F078 / F079 / F080 | ✓ |
| + | P12 | AS17-148-22727 1972.12.07 10:39 UTC / 约 29,400 公里 / 1972.12.14 5:40:56 UTC | F072 / F074 | ✓ |

**10/10 通过**（实际核了 13 条）。所有口径冲突处页面取值与本文档开头「冲突裁决」表一致；`1,459 天` 在 P01 与 P11 都标了「本卷推算」，未挂 fact_id。

## 总用时

13:54 起（读 SKILL.md）→ 15:06 导出完成，**约 72 分钟**，13 页，平均 5.5 分钟/页。其中 Step 1 的隔离 research worker 占 11 分钟（等待期间并行读完了全部规划集与执行集模块，未空等）。

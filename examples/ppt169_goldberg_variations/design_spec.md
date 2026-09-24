<!-- ppt-master-schema: design-spec/v1 -->
# goldberg_variations_ppt169_20260923 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | goldberg_variations_ppt169_20260923 |
| Canvas Format | ppt169 (1280×720) |
| Page Count | 12 |
| Primary Language | zh-CN |
| Target Audience | 公司古典音乐爱好者小组成员:喜欢听古典音乐,多数没学过乐理,听过或听说过古尔德的录音 |
| Communication Intent | 导赏:先让零乐理的听众看懂全曲结构(咏叹调首尾、30 个变奏、每三首一首卡农、卡农音程逐级上升、背后的低音线),再对比古尔德 1955 与 1981 两次录音,最后给出带着地图去听的方法 |
| Desired Audience Outcome | 听完后能说出"咏叹调 + 30 变奏 + 咏叹调"的框架,找到卡农的位置并知道它的音程一路升高,理解所有变奏共用同一条低音线,并能说出古尔德两版的主要差别 |
| Core Message / Ask / Action | 《哥德堡变奏曲》是一座以低音线为地基、以卡农为梁柱的对称建筑;看懂这张结构图,就能听出它的秩序与自由 |
| Delivery Context | 主讲人现场分享(兴趣小组活动,约 30–40 分钟,可穿插播放片段);次要用途为会后在小组内传阅 |
| Artifact Afterlife | 小组内部留存,作为之后自己聆听时的"结构地图" |
| Reading Mode | balanced |
| Content Strategy | balanced(用户未指定;以导赏叙事重组调研事实,不增加来源之外的事实) |
| Design Style | 「铜版纸上的建筑」— mode custom(instructional 为基底、narrative 收束古尔德段落)+ visual style custom(editorial + ink-notes);奶油纸底、墨色线条、暗红批注,五线谱线与拱形为贯穿母题 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — final Stage-2 proactive policy(委托决定,默认开启) |
| Custom Animations | enabled — final Stage-2 proactive policy(委托决定:结构图逐页展开需要 Morph 与分步进场) |
| Narration Audio | disabled — workflow default |
| Created Date | 2026-09-23 |
| Delegated Confirmation | 用户原话"所有确认都交给你决定,不用问我":Stage 1 与 Stage 2 均由 Strategist 代为决定,未启动确认页、无 UI 回执;决定与理由见下方 §III Delegated decisions |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 左右 60 px,上 48 px,下 40 px |
| Content Area | x 60–1220,y 48–680 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: instructional, narrative
- **Mode Behavior**: 以 instructional 为主轴——先总图、再逐层拆解(分组 → 卡农阶梯 → 放大一级 → 低音地基 → 转折与小调 → 结尾回归),每页只教一件事,标题直接说这页教什么;古尔德两版与收束两页借 narrative 的"同一作品、两次人生"对照与回到起点的回环收尾。
- **Visual style**: custom
- **Visual Style References**: editorial, ink-notes
- **Visual Style Behavior**: 奶油色纸面上的墨色线条系统:editorial 负责衬线标题与无衬线正文的对位、细规则线、页边批注与出处小字;ink-notes 负责以线条而非卡片承载结构——五根平行谱线作为贯穿母题,拱形、阶梯、括号、连线用墨线勾勒,节点以小圆点/小音符头标记;暗红只用于"卡农"与当页唯一重点,灰蓝只用于小调;几乎不用阴影与卡片网格,留白由谱线与拱形组织。
- **Theme**: 乐谱即建筑——咏叹调是两端的柱脚,30 个变奏是拱身,每三首一根卡农"梁柱",低音线是地基
- **Tone**: 安静、精确、带一点手稿温度的导赏语气

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F4EFE4 | 奶油纸面主底 |
| Secondary background | #E9E1D0 | 纸面深一阶:批注带、表格表头、分区底 |
| Primary | #1F2A36 | 墨色:标题、谱线、结构线、咏叹调节点 |
| Accent | #9E2A2B | 暗红批注色:卡农节点与当页唯一重点 |
| Secondary accent | #A88452 | 旧铜金:次级强调、年份、Quodlibet 标记 |
| Body text | #2B2621 | 正文 |
| Secondary text | #6E655A | 注释、出处、页码 |
| Divider | #CBBFA8 | 细规则线、谱线浅色版 |
| Minor key | #4F6A80 | 灰蓝:仅标记三首 g 小调变奏 |

### AI Image Strategy

- **Image Rendering**: custom
- **Visual**: 18 世纪铜版雕刻/蚀刻插画线条,细密平行排线与交叉排线塑形,墨线印在奶油纸上,极少量暗红
- **Mood**: 安静庄重而精确,像 1741 年铜版印刷乐谱扉页旁的插画
- **Image Rendering Behavior**: Copperplate engraving and etching aesthetic: fine parallel hatching and cross-hatching build every form, uniform dark-ink line weight with tapered stroke ends, no gradients, no photographic texture, no color fills except the warm cream paper and at most one tiny muted red touch; depth comes only from hatch density; calm, exact, archival mood like an illustration beside an 18th-century engraved music title page.

### Delegated decisions

- **Stage 1**: 语言 zh-CN(用户中文);画布 ppt169(用户指定 16:9);沟通契约 6 项按上表由用户原话推出;`content_divergence` 留空=balanced;选择 free_design(用户未提模板且明确"别做成普通的商务模板")。
- **Stage 2 三方向**:① 「铜版纸上的建筑」(本方案,selected=0);② 「深夜录音室」:深炭灰底、琥珀色光、键盘节奏条,showcase+narrative,微软雅黑粗体+Segoe UI 同族对位,AI 图为摄影式明暗;③ 「声音蓝图」:深蓝图纸、白色线稿与尺寸线,blueprint 风格,黑体+Consolas。选①的理由:题目本身是"对称的建筑",而作品 1741 年以铜版印刷出版,纸面+墨线+谱线能同时给出"音乐感"与"建筑感";浅底对零乐理读者的结构图最易读;②偏情绪、不利于讲清结构,③偏工程感、音乐温度不足。
- **阅读模式** balanced:主讲为主但会后传阅;讲解细节由备注承担。**页数** 12(用户"12 页左右")。
- **字体**:标题 SimSun + Cambria(衬线,呼应乐谱印刷;Cambria 为衬线数字且为等高数字,适合 1741/32/30),正文 Microsoft YaHei + Segoe UI(投影可读);对比型搭配。
- **字号**:正文 22(balanced 带 22–25 的低端,因结构图页标注多),标题 38,副标题 28,导语 26,注释 16,脚注 14,展示数字 88,封面标题 60。
- **数字写法**:阿拉伯数字 + 中文量词("第 16 变奏""30 个变奏");年份用阿拉伯数字;音程用中文"同度/二度/…/九度";曲名首次出现附原文。
- **图片来源**:web(巴赫肖像、1741 初版扉页,只接受公共领域/开放许可,记 `image_sources.json`)+ ai(≤2 张:封面拱形铜版画、录音室空椅);古尔德本人照片无清楚开放许可,不放;五线谱/音符/结构图全部原生形状绘制。
- **图标**:tabler-outline,stroke 1.5(细线与墨线气质一致),只作小提示。
- **两次录音时长**:调研未找到官方或权威来源(仅维基百科转引数字 F041),按任务要求不写入页面、不做时长图表;对比页用原生表格承载可查证的事实。

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 印刷衬线,庄重 | SimSun | Cambria | serif |
| Body | 清晰无衬线 | Microsoft YaHei | Segoe UI | sans-serif |
| Display | 衬线等高数字 | SimSun | Cambria | serif |

- **Title stack**: SimSun, Cambria, serif
- **Body stack**: Microsoft YaHei, Segoe UI, sans-serif
- **Display stack**: SimSun, Cambria, serif
- **Role rationale**: display 角色用于封面与结构页的大号数字(32、30、1741、九度阶梯编号),与标题同族以保持印刷感。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 22 |
| Title | 38 |
| Subtitle | 28 |
| Lead | 26 |
| Annotation | 16 |
| Footnote | 14 |
| Display | 88 |
| Cover title | 60 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 标题(左上,衬线)→ 页面主图(结构线/谱线)→ 批注与出处;结构页让图占主导,文字作为页边批注
- **Composition tendency**: 以一条贯穿页面的"谱线/地平线"或拱形组织区域,而不是卡片网格;对比页用左右对页;封面与收尾使用大留白
- **Cross-page continuity**: 五根平行细谱线母题在每页以不同比例出现(封面为背景、结构页为基线、低音页为真实五线谱);32 个节点的拱形在 P03 建立,P04/P05/P06 由它变形而来
- **Spacing posture**: 结构页 dense 但开阔,解释页 breathing
- **Spacing anchors**: 页边距 60 px;块间距 28 px;栏间距 40 px;圆角 4 px;正文行距 1.55

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 1.5

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/tabler-outline/headphones.svg | 聆听任务、听什么 |
| icons/tabler-outline/ear.svg | 听辨提示 |
| icons/tabler-outline/vinyl.svg | 唱片、录音版本 |
| icons/tabler-outline/piano.svg | 键盘乐器 |
| icons/tabler-outline/repeat.svg | 反复、回到开头 |
| icons/tabler-outline/moon.svg | 失眠轶事、夜 |
| icons/tabler-outline/feather.svg | 书写、手稿 |
| icons/tabler-outline/calendar.svg | 日期、年份 |
| icons/tabler-outline/microphone.svg | 录音 |
| icons/tabler-outline/stairs-up.svg | 音程递升 |
| icons/tabler-outline/building-arch.svg | 建筑隐喻 |
| icons/tabler-outline/quote.svg | 引语 |
| icons/tabler-outline/clock.svg | 速度、时间 |
| icons/tabler-outline/music.svg | 旋律、民歌 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P10 | table | comparison_matrix | 以相同维度对照古尔德 1955 与 1981 两次录音的可查证事实 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_arch.jpg | 2752×1536 | 16:9 | P01 封面主视觉 | Illustration | 全幅画面作底,左侧留出安静区放原生标题 | adaptive | ai | Generated | 一座由细墨线雕刻出的古典石拱廊从右向左延伸,拱券的横梁上隐约排着五根平行的谱线,像一段被建成建筑的乐谱;右侧拱廊细节最密,左侧约 45% 画面是空白奶油纸,供标题 | none | hero_page |
| studio_chair.jpg | 848×1264 | 2:3 | P10 录音对比页侧栏氛围图 | Illustration | 竖长侧栏,与表格并置,为"两次录音、同一间录音室"提供场景 | adaptive | ai | Generated | 空旷的老式录音室里,一架三角钢琴前放着一把很矮的旧木折叠椅,远处是高大的墙面与一支立式话筒;无人物;竖构图,钢琴与椅子位于下半部 | none | local |
| bach_portrait.jpg | 2616×3438 | 约 3:4 | P02 巴赫真身肖像 | Photo | 左侧竖向肖像框,配出处小字 | adaptive | web | Sourced | Elias Gottlob Haussmann 所绘巴赫油画肖像(1746/1748 版本),手持乐谱,半身,公共领域图像 | none | local |
| title_page_1741.jpg | 2494×3754 | 约 2:3 | P02 1741 年初版扉页 | Photo | 与肖像并置的扉页小图,完整显示 | no-crop | web | Sourced | 巴赫《键盘练习曲》第四卷(哥德堡变奏曲)1741 年初版印本扉页,文字"Clavier Ubung … ARIA mit verschiedenen Veraenderungen"清晰可辨,公共领域 | none | local |

## IX. Content Outline

### Part 1: 进入作品

#### Slide 01 - 封面

- **Audience move**: 只知道"哥德堡变奏曲"这个名字 → 期待看到一张能听懂它的结构图
- **Relationships**: none
- **Cover impact**: 钩子"32 段音乐,同一条低音线";构图参考:左侧大字标题,右侧铜版拱廊画,谱线母题从画面延伸到标题下方
- **Title**: 哥德堡变奏曲:一座对称的建筑
- **Core message**: 这是一座用 32 段音乐搭起来的对称建筑
- **Content**: 主标题 / 副标题"巴赫 BWV 988 · 1741 · 零乐理导赏" / 钩子"32 段音乐,同一条低音线"
- **Images**: cover_arch.jpg
- **Fact IDs**: F001, F007

#### Slide 02 - 这部作品从哪里来

- **Audience move**: 不知道作品背景 → 知道它是 1741 年出版的键盘练习曲第四卷,为双键盘羽管键琴而写,"失眠伯爵"只是相传的故事
- **Relationships**: 出版事实与轶事是 contrast(可查证 vs 相传);肖像与扉页是 membership(同属作品身份)
- **Composition**: 左侧肖像+扉页并置,中间出版事实,右侧"相传"批注栏
- **Title**: 1741 年,一部写给双键盘羽管键琴的练习曲
- **Core message**: 它首先是巴赫亲自出版的《键盘练习曲》第四卷,"哥德堡"之名来自一个存疑的故事
- **Content**: 1741 出版《键盘练习曲》第四卷,"一首咏叹调及多种变奏,供双键盘羽管键琴"(旧说 1742) · 扉页指定两排手键盘,钢琴上双手交叠更难 · 巴赫 1685–1750 / 相传栏:福克尔 1802 年传记:失眠的凯瑟林伯爵让府中年轻键盘手哥德堡夜里弹奏,酬以盛一百金路易的金杯 · 学界存疑:乐谱无题献,出版时哥德堡只有 14 岁
- **Images**: bach_portrait.jpg, title_page_1741.jpg
- **Fact IDs**: F001, F002, F003, F005, F026, F027, F028, F029, F042

### Part 2: 看懂结构

#### Slide 03 - 全景:32 段 = 1 + 30 + 1

- **Audience move**: 以为是 30 首散曲 → 看到首尾同一首咏叹调、中间 30 个变奏、在第 16 变奏处对折的整体建筑
- **Relationships**: 咏叹调—30 变奏—咏叹调再现 order;首尾咏叹调 overlap(同一首);第 16 变奏开启后半 order;卡农(每第三首)、三首小调、第 30 变奏为 membership 标记
- **Composition**: 32 个节点排成一座对称拱形,两端为咏叹调,拱顶在第 15/16 之间;卡农节点暗红,小调节点灰蓝;图例在下方
- **Title**: 全景:首尾同一首咏叹调,中间 30 个变奏
- **Core message**: 全曲 32 段像一座拱:咏叹调站在两端,第 16 变奏把它对折成前后两半
- **Content**: 咏叹调(主题)→ 30 个变奏 → 咏叹调再现 · 32 段呼应咏叹调的 32 小节 · 每第 3 首是卡农 · 第 15、21、25 为小调 · 第 16 变奏(法国序曲)开启后半 · 第 30 为集腔曲
- **Visualization**: 32 节点对称拱形结构图(qualitative)
- **Motion suggestion**: 建立"结构地图";32 个节点组成的变奏场在下一页重新排列为分组网格(Morph 候选:本页 var-field → P04 var-field)
- **Fact IDs**: F006, F007, F011, F016, F018, F012

#### Slide 04 - 每三首一组

- **Audience move**: 看到 30 个点 → 发现它们每 3 首一组、共 10 组,每组以一首卡农收尾
- **Relationships**: 10 组 order;每组内 炫技曲—性格小品—卡农 membership;第 30 变奏以集腔曲取代第十首卡农 contrast
- **Composition**: 10 列 × 3 行网格,底行(卡农)为暗红一条"梁";第 10 列底格改为集腔曲
- **Title**: 每三首一组:一首炫技、一首小品、一首卡农
- **Core message**: 30 个变奏排成 10 组,每组第三首都是卡农,像 9 根有规律的梁柱
- **Content**: 10 组 × 3 首 · 典型组合:炫技的触技曲式 / 温和的性格小品 / 严格的卡农 · 第 30 变奏:集腔曲取代第十首卡农 · 注:"炫技/小品"是常见概括,并非每组都严格如此
- **Visualization**: 10×3 分组网格(qualitative)
- **Motion suggestion**: 承接 P03 的变奏场(Morph:P03 var-field → 本页 var-field);底行卡农梁在下一页变成音程阶梯(Morph 候选:本页 canon-row → P05 canon-row)
- **Fact IDs**: F011, F012

#### Slide 05 - 卡农的音程一路往上走

- **Audience move**: 知道有 9 首卡农 → 看出它们的音程从同度一级级升到九度
- **Relationships**: 9 首卡农按 同度→二度→…→九度 order;第 12、15 倒影 membership;第 27 无低音 contrast
- **Composition**: 9 级阶梯从左下升到右上,每级标变奏号与音程;两处倒影与第 27 变奏用批注
- **Title**: 卡农的音程:从同度一级级升到九度
- **Core message**: 第 3 变奏同度,之后每首卡农升高一级,到第 27 变奏是九度
- **Content**: 一句定义:卡农=一个声部追着另一个唱同一段旋律;"几度"=后起声部比先起声部高多少 · 3 同度 / 6 二度 / 9 三度 / 12 四度 / 15 五度 / 18 六度 / 21 七度 / 24 八度 / 27 九度 · 第 12、15 是倒影卡农(追随声部方向相反) · 第 27 是唯一没有低音支撑的卡农,只剩两个声部
- **Visualization**: 9 级音程阶梯(qualitative order)
- **Motion suggestion**: 承接 P04 卡农梁(Morph:P04 canon-row → 本页 canon-row);其中一级(第 9 变奏,三度)在下一页放大成两行谱例(Morph 候选:本页 step-focus → P06 step-focus)
- **Fact IDs**: F013, F014, F015

#### Slide 06 - 放大一级:什么叫"三度卡农"

- **Audience move**: "几度卡农"仍是抽象词 → 看到两行谱:第二个声部晚一步进来,把同一旋律整体抬高
- **Relationships**: 先起声部 → 追随声部 order(晚进入)与 overlap(同一旋律);音程高度差 contrast
- **Composition**: 两行示意谱上下排列,同形旋律用同色音符头,错开一个时间位置并整体抬高;批注解释"晚进来""抬高三度"
- **Title**: 放大一级:"三度卡农"是怎么追的
- **Core message**: 卡农就是轮唱;"三度"表示追随的声部起音比先唱的声部高三度
- **Content**: 类比:像轮唱《两只老虎》,后一组晚一步唱同一段 · 差别:巴赫让后起声部换一个高度——高三度 · 同理:同度=同一高度,九度=高出九度 · 示意谱为本页整理的简化图,不是巴赫原谱
- **Visualization**: 两行示意谱(qualitative,整理)
- **Motion suggestion**: 承接 P05 的第 9 变奏一级(Morph:P05 step-focus → 本页 step-focus);追随声部在先起声部之后进场
- **Fact IDs**: F013

### Part 3: 地基与转折

#### Slide 07 - 地基:一条 32 小节的低音线

- **Audience move**: 以为变奏是在改旋律 → 知道巴赫变的是低音线撑起的和声,旋律可以完全不同
- **Relationships**: 低音线 parent 于 32 段(所有变奏共用);32 小节 = 4 × 8 小节和声区 order(G—D—e—G);前 8 个低音 → 十四首卡农 BWV 1087 link
- **Composition**: 上方一行真实五线谱写出低音前 8 音(下行起步);下方一条 32 格小节带,按 8 小节分为 G 大调—D 大调—e 小调—G 大调;右侧批注 BWV 1087
- **Title**: 地基:所有变奏共用一条低音线
- **Core message**: 巴赫变奏的不是旋律,而是每小节低音线所暗示的和声
- **Content**: 低音开头八音 G–F♯–E–D–B–C–D–G(据 Kirkpatrick 版记谱,前四音逐级下行) · 32 小节,分两半各 16 小节,每半再按 8 小节落在 G 大调—D 大调—e 小调—G 大调 · 每首变奏都是两半等长、各奏两遍 · 1974 年发现的巴赫自用本末页:十四首卡农(BWV 1087)全建在这前八个低音上
- **Visualization**: 低音五线谱 + 32 小节和声带(qualitative)
- **Fact IDs**: F008, F009, F010, F022, F023, F024

#### Slide 08 - 转折:一次对折,三处阴影

- **Audience move**: 以为 30 首同一色调 → 注意到第 15 首后全曲"翻页"、三首 g 小调像三处阴影,第 25 首最深
- **Relationships**: 第 15 变奏 → 第 16 变奏 order(前半结束、后半开启);第 15、21、25 membership(g 小调);第 25 为三者中的焦点 contrast
- **Composition**: 一条横贯全页的 30 格变奏带,在 15|16 之间一道分隔(翻页);三格小调加深并下垂批注;第 25 变奏批注最大
- **Title**: 转折:第 16 首翻开后半,三首小调是三处阴影
- **Core message**: 第 15 首(第一首小调、五度倒影卡农)之后,第 16 首法国序曲开启后半;第 25 首 Adagio 被称作"黑珍珠"
- **Content**: 第 15:第一首小调,也是五度倒影卡农 · 第 16:法国序曲,后半开场 · 小调只有 15、21、25 三首(g 小调) · 第 25:巴赫自用本标 Adagio,兰多夫斯卡称"黑珍珠"
- **Visualization**: 30 格变奏带(qualitative)
- **Fact IDs**: F014, F016, F017, F018

#### Slide 09 - 终点回到起点

- **Audience move**: 以为结尾会是最难的卡农 → 看到第 30 首用民歌"玩笑"收束,然后咏叹调原样回来
- **Relationships**: 第 30 变奏取代第十首卡农 contrast;两首民歌与低音主题 overlap(叠合);第 30 变奏 → 咏叹调再现 order;咏叹调再现与开头 overlap(同一首)
- **Composition**: 左侧集腔曲批注(两首民歌的歌名与中文意),右侧一个回环箭头从第 30 变奏回到拱形起点的咏叹调
- **Title**: 终点回到起点:民歌玩笑之后,咏叹调原样回来
- **Core message**: 第 30 变奏把两首德国民歌叠在低音主题上,随后咏叹调原样再现,32 段合成一个回环
- **Content**: 集腔曲(Quodlibet,拉丁语"随心所欲"):延续巴赫家族拼接流行歌曲即兴合唱的习俗 · 相传叠入的两首民歌:"Ich bin so lang nicht bey dir g'west"(我好久没和你在一起)、"Kraut und Rüben haben mich vertrieben"(白菜萝卜把我赶走了) · 认定来源只有巴赫学生 Kittel 约 1801 年的口述记录,宜作"相传" · 最后:咏叹调再现(Aria da capo)
- **Fact IDs**: F006, F012, F019, F020, F021

### Part 4: 两次录音与聆听

#### Slide 10 - 古尔德:同一间录音室,相隔 26 年

- **Audience move**: 听说古尔德有两个版本 → 能说出 1955 与 1981 在年龄、速度气质、反复处理和命运上的差别,并知道时长数字未能核实
- **Relationships**: 1955 版与 1981 版 contrast(同一维度对照);1981 版发行 → 古尔德去世 order(约一个月)
- **Composition**: 右侧对照表为主,左侧窄栏为录音室氛围图;表下一行 Tim Page 的引语批注
- **Title**: 古尔德 1955 与 1981:同一间录音室,两种时间感
- **Core message**: 22 岁的 1955 版快而锋利,晚年的 1981 版慢而细密;后者发行一个月后古尔德去世
- **Content**: 录制:1955 年 6 月 10–16 日间四天 / 1981 年 4–5 月多次,均在纽约哥伦比亚 30 街录音室 · 古尔德年龄:22 岁 / 48 岁(按 1932 年 9 月生推算) · 发行:1956 年 1 月 / 1982 年 9 月 2 日 · 气质(Sony 官方表述):冲劲十足的快速度 / 缓慢、细腻刻画细节 · 反复:1955 版据维基百科不奏反复 / 1981 版奏了部分前半段反复(Sony 称 15 个,另说 13 个) · 荣誉:2003 年入选美国国家录音登记册 / 1983 年两项格莱美 · 古尔德 1982 年 10 月 4 日去世 · Tim Page:1955 版是"天真之歌" · 注:两版总时长未找到唱片公司或权威来源,故不列
- **Visualization**: gould-compare 对照表(1955 vs 1981 × 录制/年龄/发行/气质/反复/荣誉)
- **Native-ready**: gould-compare=yes
- **Images**: studio_chair.jpg
- **Fact IDs**: F031, F032, F033, F034, F035, F036, F037, F038, F039, F040

#### Slide 11 - 带着地图去听

- **Audience move**: 看懂了结构 → 拿到四个具体的聆听任务,下次听时能自己找到结构
- **Relationships**: 四个聆听任务 order(由浅入深);每项任务 link 到前面某页的结构要点
- **Composition**: 四个编号任务沿一行谱线从左到右排开,每项配一个小图标与"对应页"标注;页角注明"整理"
- **Title**: 带着地图去听:四个小任务
- **Core message**: 用四个任务把结构图变成耳朵能抓住的东西
- **Content**: 1 听地基:开头咏叹调里注意左手低音的下行起步 · 2 数卡农:每到第 3、6、9……首,留意"有人在追" · 3 找阴影:第 15、21、25 首转入小调,第 25 首最慢最暗 · 4 比两版:同一段咏叹调,先放 1955 再放 1981 · 标注"本页为整理的聆听建议"
- **Fact IDs**: F011, F016, F017, F022, F035

#### Slide 12 - 收束

- **Audience move**: 带着零散知识 → 记住一句话:地基不变,上面的建筑千变万化
- **Relationships**: 低音线(不变)与 30 种变化 contrast;回到咏叹调 order(回环)
- **Closing impact**: 结论"同一条低音线,撑起 32 段音乐——结构是地图,耳朵才是终点";构图参考:缩小的拱形回到页面下方,咏叹调两端节点点亮
- **Title**: 同一条低音线,撑起 32 段音乐
- **Core message**: 看懂"地基不变、上层万变",就能在每次聆听中听出秩序与自由
- **Content**: 结论句 · 三个关键词回顾:地基(低音线)/ 梁柱(9 首卡农,同度→九度)/ 回环(咏叹调首尾) · 主要资料来源一行(Tafelmusik、Bloomfield 节目单、美国国会图书馆、加拿大图书档案馆、Sony Music Japan)
- **Fact IDs**: F006, F009, F013

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 以口语讲解承担乐理解释:术语(卡农、音程、倒影、集腔曲、低音线)首次出现时用生活类比解释;引用事实时自然说出出处;"相传"类内容明确说是轶事;不朗读页码与装饰
- **Total duration**: 约 30–35 分钟(不含播放片段)
- **Notes style**: conversational,耐心导赏
- **Presentation purpose**: 导赏——看懂结构、对比两版、带着地图去听

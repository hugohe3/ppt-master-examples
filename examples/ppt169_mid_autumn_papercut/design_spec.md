<!-- ppt-master-schema: design-spec/v1 -->
# mid_autumn_papercut_default - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | mid_autumn_papercut_default_ppt169_20260902 |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 16 |
| Primary Language | zh-CN |
| Target Audience | 普通中文读者与听众，对中秋有生活经验但没有系统的历史知识；知道嫦娥、月饼、团圆，不知道这些说法各自出自哪一层文本 |
| Communication Intent | 先用一条可核实的物证线索（「月饼」二字的迁徙）把中秋从习惯变成历史；再解释每一个熟悉的意象是哪一代人加上去的；最后回到今天的假期与数字，让听众看见自己正站在这条线的末端 |
| Desired Audience Outcome | 听众能说出中秋从祭仪到节日的三个关键时点（周礼—唐诗—北宋定节），能说清「月饼」一词早于「中秋送月饼」这件事，能指出嫦娥化蟾不出自《淮南子》，并愿意在今年中秋把其中一条讲给别人听 |
| Core Message / Ask / Action | 中秋不是一个从来如此的节日：它的每一层——礼、诗、饼、传说、灯火、名录、假期——都有可查的加入时间；认识这些时点，今晚的月亮会更好看 |
| Delivery Context | 主：2026 年中秋前的线下文化分享，有主讲人，约 25 分钟；次：会后作为可独立阅读的图文材料在社群里传阅 |
| Artifact Afterlife | 作为可反复取用的文化科普材料留存与转发；引用的每条史实可回溯到 sources/ 中的 fact 编号 |
| Reading Mode | balanced |
| Content Strategy | 自由重构：源材料是按研究缺口组织的事实清单，不是页面结构；按叙事弧重新编排、补写过渡与转折，但一切可外部核实的断言只能来自已记录的 fact，不得外扩 |
| Design Style | 月出东山 — 夜色剪纸叙事（custom narrative + custom paper-cut） |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 用户显式指令（客户简报「Speaker notes on」） |
| Custom Animations | enabled — 最新显式用户指令（客户变更：本卷作为展廊示例，需要逐对象自定义动画，不止页面转场；对象级编排在 customize-animations 阶段完成） |
| Narration Audio | disabled — 用户显式指令（客户简报「narration off」） |
| Created Date | 2026-09-02 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 上下 56，左右 72 |
| Content Area | x 72–1208，y 56–664 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: narrative
- **Mode Behavior**: 以 narrative 的 situation → tension → resolution 贯穿全卷，并按本题材切成四幕：第一幕给出「熟悉但说不清」的处境，第二幕用「月饼一词早于送月饼」制造第一次转折，第三幕用「化蟾不出《淮南子》」制造第二次转折（把观众的既有认知本身变成冲突），第四幕以名录、假期、数字落回当下，以苏轼的词收束情绪。页标题写成推进弧线的句子而非标签；章页只承担换幕，不承担论证。
- **Visual style**: custom
- **Visual Style References**: paper-cut
- **Visual Style Behavior**: 完整采用 paper-cut 的分层剪纸体系——形体由略不规则的剪切边定义、不画描边，每个色值是一张纸，层与层之间落 8–12% 柔影，纸面带细颗粒；构图上用「一枚大剪圆（月）锚定画面」「模切窗口露出下层」「层叠波形纸自下而上堆叠」三种几何。唯一的定制是把 paper-cut 通常的暖白桌面换成深靛夜场：底层纸是夜，上层纸是月光金、朱砂红与米白，使剪纸的层叠关系靠明度而非暖度拉开。卡片网格被禁止性地替换为「纸片自由叠放」：内容块坐在裁切纸片上，纸片可出血、可轻微旋转、可互相压边。
- **Theme**: 月自海面升起，一路盈满 — 全卷保留一枚剪纸月亮作为连续状态，从封面右下的一弯细牙，经各幕逐页改变相位、尺寸与位置，到末页升至画面中央成为最大的满月；云带、桂枝、远山脊三个剪纸构件在不同页复用，构成前景/中景/背景三层纸的注册深度
- **Tone**: 沉静、有夜气、可触摸；不喜庆化，不做贺卡

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #131A33 | 夜场底纸，全卷页面底色 |
| Secondary background | #1E2748 | 抬起一层的靛蓝纸片，承载内容块与表格 |
| Primary | #E8B04B | 月光金 — 主导前景纸层、页标题、关键数字、月亮本体 |
| Accent | #D4453A | 朱砂红 — 顶层小面积剪出的强调纸片、印章式标记、转折点标注（不用于正文） |
| Secondary accent | #7FA8C9 | 月色青 — 注释、发丝线、次级引导、水面与远山 |
| Body text | #F2ECE0 | 米白宣纸色，正文与引文 |
| Secondary text | #B9C2D8 | 说明文字、图注、来源标注 |
| Divider | #33406B | 分隔线、纸片接缝、表格栏线 |
| Surface | #26305A | 再抬一层的纸面，用于表格头、引文块等需要与 secondary background 区分的层 |
| Scrim | #0C1026 | 压在整幅图像上的暗层，保证图上文字可读 |
| Block shade | #0E1329 | 纸层柔影颜色，比底纸暗一档 |

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: paper-cut
- **Visual**: 分层剪纸工艺 — 形体由略带手工不规则的剪切边界定，无任何描边；每一色为一张独立纸片，层间落 8–12% 柔影产生真实厚度；纸面带 10–15% 不透明度的纸纤维颗粒；造型简化为可辨的剪纸而非插画。全部元素在夜靛底纸上以月光金、朱砂红、米白、月色青四张纸构成
- **Mood**: 夜里的手工灯笼纸 — 温度来自纸的质地而非色温；像民间剪纸窗花被逆光照亮，安静、可触摸、带一点仪式感
- **Image Rendering Behavior**: 完全承接 paper-cut 预设的线质、纹理、深度与材质（剪切边、纸颗粒、层叠柔影、卡纸材质），只把它的默认暖白底纸换成本卷的深靛夜场，并规定层叠对比靠明度差建立；人物一律为剪影级简化，不做面部细节。

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 楷体书写体 / 有笔锋的中文标题字 | KaiTi | Georgia | serif |
| Body | 中性无衬线 / 屏幕与投影可读 | Microsoft YaHei | Arial | sans-serif |
| Quote | 楷体书写体 / 古典引文 | KaiTi | Georgia | serif |
| Data | 中性无衬线 / 表格与密集标注 | Microsoft YaHei | Arial | sans-serif |
| Annotation | 中性无衬线 | Microsoft YaHei | Arial | sans-serif |
| Footnote | 中性无衬线 | Microsoft YaHei | Arial | sans-serif |
| Hero number | 衬线数字 / 有重量的西文数字 | Georgia | Georgia | serif |

- **Title stack**: KaiTi, Georgia, serif
- **Body stack**: Microsoft YaHei, Arial, sans-serif
- **Quote stack**: KaiTi, Georgia, serif
- **Data stack**: Microsoft YaHei, Arial, sans-serif
- **Annotation stack**: Microsoft YaHei, Arial, sans-serif
- **Footnote stack**: Microsoft YaHei, Arial, sans-serif
- **Hero number stack**: Georgia, serif
- **Role rationale**: `quote` 单列一族，因为全卷有六页承载古籍原文与词句，需与正文黑体形成可识别的引文层；`hero_number` 单列 Georgia，因为楷体阿拉伯数字在大字号下结构松散，而全卷有五处需要大号数字（111、518、Ⅹ-5、1.07 亿、30 万吨）。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 42 |
| Cover title | 72 |
| Chapter title | 52 |
| Subtitle | 30 |
| Lead | 28 |
| Quote | 34 |
| Hero number | 88 |
| Data | 20 |
| Annotation | 18 |
| Footnote | 16 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 每页先有一个占据视觉重量的剪纸物件（月、饼、人物或整幅夜景），再由它引出一句判断句标题，最后才是解释文字；视线自图向文、自上而下或自右向左（跟随月亮所在的一侧）
- **Composition tendency**: 内容坐在裁切纸片上而不是卡片网格里；纸片允许出血、轻微旋转、互相压边；每页至少有一处「模切窗口」或「大剪圆」承担聚焦；禁止把一页平均切成等宽等重的多列格子
- **Cross-page continuity**: 月亮相位与位置构成全卷唯一的连续状态；云带、桂枝、远山脊三个剪纸构件跨页复用并改变尺度与角度；四枚剪纸字（中秋 / 月夕 / 月饼 / 团圆）分别落在封面与三处换幕点
- **Spacing posture**: 随 page_rhythm 变化 — anchor 页大量留出夜场底纸，dense 页允许纸片贴近但保持层间柔影可见，breathing 页只留一件主物加一句话
- **Spacing anchors**: 页边距 72px；块间距 32px；分栏间隙 40px；圆角半径 0px（剪纸不留圆角，边界靠不规则剪切路径）；正文行高 1.65

## VI. Icon Usage Specification

- **Primary bundled library**: none

| Icon Path | Suitable Scenarios |
| --- | --- |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P09 | table | comparison_matrix | 以五个流派为列、四项国标属性为行，比较广苏京潮滇的产地、饼皮工艺、口感与代表品种 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| sheet_moon.jpg | 2048×2048 | 1:1 | 月相与自然构件的剪纸元素母版 | Illustration Sheet | 母版不上页 | no-crop | ai | Generated | reusable illustration family: 六种月相 + 云带 + 桂枝 + 远山脊，3×3 方形格，用于跨页连续状态与前中后三层纸 | none | local |
| sheet_legend.jpg | 2528×1696 | 12:8 | 三则传说的人物与器物元素母版 | Illustration Sheet | 母版不上页 | no-crop | ai | Generated | reusable illustration family: 嫦娥、吴刚、桂树、玉兔、蟾蜍、药壶，2×3 方形格 | none | local |
| sheet_custom.jpg | 2048×2048 | 1:1 | 中秋习俗器物构件母版 | Illustration Sheet | 母版不上页 | no-crop | ai | Generated | reusable illustration family: 火龙、烧塔、竖中秋灯杆、博饼骰碗，2×2 方形格 | none | local |
| sheet_figures.jpg | 2048×2048 | 1:1 | 人物形构件母版（与器物分卷，形态族不同） | Illustration Sheet | 母版不上页 | no-crop | ai | Generated | reusable illustration family: 兔儿爷、走月行人，1×2 竖形格 | none | local |
| sheet_mooncake.jpg | 2528×1696 | 12:8 | 五派月饼与饼模的对照元素母版 | Illustration Sheet | 母版不上页 | no-crop | ai | Generated | illustrated-icon set: 广苏京潮滇五式月饼各一 + 木质饼模，2×3 方形格，需在 180px 尺度下仍能区分饼皮特征 | none | local |
| sheet_lettering.jpg | 2048×2048 | 1:1 | 四枚剪纸美术字 | Illustration Sheet | 母版不上页 | no-crop | ai | Generated | decorative lettering set: exact strings = 中秋 / 月夕 / 月饼 / 团圆，每格一枚竖排双字，2×2 方形格 | embedded | local |
| cover_night_field.jpg | 2752×1536 | 18:10 | 封面整幅夜景底纸（干净全画布底层） | Scene | 满版铺底，标题与剪纸构件叠在其上；底层不含主体，主体由透明切片承担 | no-crop | ai | Generated | 层叠剪纸的夜海与远岸：底部两三层波形纸构成海面，上方大片空夜，右下留出安放月牙的空区，左上三分之一保持低密度以承载竖排标题 | none | hero_page |
| kaifeng_night_market.jpg | 2752×1536 | 18:10 | P05 北宋开封中秋夜市的整幅场景 | Scene | 满版页面场，压暗层后承载文字；右侧三分之一留安静区 | no-crop | ai | Generated | 层叠剪纸的宋代城市夜市：酒楼台榭剪影、彩楼欢门、密集的灯与人形剪影自下而上堆叠三层，右上留出被云半掩的月位 | none | hero_page |
| moon_full.png | 495×500 | 10:10 | 满月 — 连续状态的终点 | Illustration element | 大剪圆锚定画面，可被文字压边或出血 | no-crop | slice | Generated | 由 sheet_moon.jpg 第 1 行第 1 格切出 | none | local |
| moon_gibbous.png | 490×492 | 10:10 | 盈凸月 — 换幕点的状态 | Illustration element | 小剪圆置于页角，随幕次改变位置 | no-crop | slice | Generated | 由 sheet_moon.jpg 第 1 行第 2 格切出 | none | local |
| moon_half.png | 254×500 | 10:20 | 上弦月 — 用作模切窗口 | Illustration element | 作为剪出的圆形窗口，露出下层纸与文字 | no-crop | slice | Generated | 由 sheet_moon.jpg 第 1 行第 3 格切出 | none | local |
| moon_crescent.png | 426×508 | 16:19 | 细牙月 — 连续状态的起点 | Illustration element | 封面右下低位，小而偏，留出上升空间 | no-crop | slice | Generated | 由 sheet_moon.jpg 第 2 行第 1 格切出 | none | local |
| moon_veiled.png | 653×464 | 24:17 | 被云半掩的月 | Illustration element | 与云带叠压，作夜市页右上角的呼吸口 | no-crop | slice | Generated | 由 sheet_moon.jpg 第 2 行第 2 格切出 | none | local |
| moon_reflection.png | 490×490 | 1:1 | 水面月影 | Illustration element | 置于页面下缘并被波形纸压住一半，暗示泛舟与照无眠 | no-crop | slice | Generated | 由 sheet_moon.jpg 第 2 行第 3 格切出 | none | local |
| cloud_band.png | 647×275 | 14:6 | 祥云带 — 中景纸层 | Illustration element | 横向掠过页面，压在月与文字之间建立中景 | no-crop | slice | Generated | 由 sheet_moon.jpg 第 3 行第 1 格切出 | none | local |
| osmanthus_sprig.png | 483×500 | 23:24 | 桂枝 — 角部构件 | Illustration element | 自页角斜出，可出血，跨页改变角度与尺度 | no-crop | slice | Generated | 由 sheet_moon.jpg 第 3 行第 2 格切出 | none | local |
| mountain_ridge.png | 621×191 | 13:4 | 远山脊 — 背景纸层 | Illustration element | 贴页面下缘的最底一层剪纸，建立地平线 | no-crop | slice | Generated | 由 sheet_moon.jpg 第 3 行第 3 格切出 | none | local |
| change_e.png | 755×633 | 19:16 | 嫦娥奔月剪影 | Illustration element | 主体人物，可被标题压边，形成前景层 | no-crop | slice | Generated | 由 sheet_legend.jpg 第 1 行第 1 格切出 | none | local |
| wu_gang.png | 393×706 | 10:18 | 吴刚伐桂剪影 | Illustration element | 与桂树成对放置，体现「树创随合」的循环 | no-crop | slice | Generated | 由 sheet_legend.jpg 第 1 行第 2 格切出 | none | local |
| osmanthus_tree.png | 704×623 | 17:15 | 月中桂树 | Illustration element | 与吴刚同页，作为被砍与复合的对象 | no-crop | slice | Generated | 由 sheet_legend.jpg 第 1 行第 3 格切出 | none | local |
| jade_rabbit.png | 524×605 | 13:15 | 玉兔捣药 | Illustration element | 长跪姿态，置于月轮之内或之侧 | no-crop | slice | Generated | 由 sheet_legend.jpg 第 2 行第 1 格切出 | none | local |
| toad.png | 579×481 | 12:10 | 蟾蜍 | Illustration element | 小件，与嫦娥并置以标出「化蟾」这一后加层 | no-crop | slice | Generated | 由 sheet_legend.jpg 第 2 行第 2 格切出 | none | local |
| elixir_jar.png | 408×508 | 12:15 | 不死药壶 | Illustration element | 小件，作为叙述起点的物证 | no-crop | slice | Generated | 由 sheet_legend.jpg 第 2 行第 3 格切出 | none | local |
| fire_dragon.png | 797×912 | 14:16 | 大坑舞火龙 | Illustration element | 习俗页最大的一件，斜向贯穿并可出血 | no-crop | slice | Generated | 由 sheet_custom.jpg 第 1 行第 1 格切出 | none | local |
| lantern_tower.png | 624×912 | 13:19 | 烧塔 / 瓦子灯 | Illustration element | 与火龙成组，尺度小一档 | no-crop | slice | Generated | 由 sheet_custom.jpg 第 1 行第 2 格切出 | none | local |
| lantern_pole.png | 376×932 | 2:5 | 树中秋彩灯高杆 | Illustration element | 竖向构件，用于打断横向节奏 | no-crop | slice | Generated | 由 sheet_custom.jpg 第 2 行第 1 格切出 | none | local |
| dice_bowl.png | 821×636 | 22:17 | 博饼骰碗 | Illustration element | 俯视小件，作为「玩法」一节的语义提示 | no-crop | slice | Generated | 由 sheet_custom.jpg 第 2 行第 2 格切出 | none | local |
| rabbit_lord.png | 891×1755 | 10:20 | 兔儿爷泥塑 | Illustration element | 名录页的单一主角，正面端坐 | no-crop | slice | Generated | 由 sheet_figures.jpg 第 1 格切出 | none | local |
| walking_pair.png | 934×1678 | 10:18 | 走月的一对行人 | Illustration element | 小尺度人形剪影，跨页复用于临安与习俗两页 | no-crop | slice | Generated | 由 sheet_figures.jpg 第 2 格切出 | none | local |
| cake_guang.png | 611×635 | 23:24 | 广式月饼 | Illustrated icon | 与表格首列对齐的行标识，不进容器 | no-crop | slice | Generated | 由 sheet_mooncake.jpg 第 1 行第 1 格切出 | none | local |
| cake_su.png | 629×503 | 10:8 | 苏式月饼 | Illustrated icon | 同上；另在 P08 放大作为「南宋点心」的物证 | no-crop | slice | Generated | 由 sheet_mooncake.jpg 第 1 行第 2 格切出 | none | local |
| cake_jing.png | 602×592 | 10:10 | 京式月饼 | Illustrated icon | 同上；另在 P08 放大作为「明代馈赠」的物证 | no-crop | slice | Generated | 由 sheet_mooncake.jpg 第 1 行第 3 格切出 | none | local |
| cake_chao.png | 599×604 | 10:10 | 潮式月饼 | Illustrated icon | 与表格首列对齐的行标识 | no-crop | slice | Generated | 由 sheet_mooncake.jpg 第 2 行第 1 格切出 | none | local |
| cake_dian.png | 633×504 | 10:8 | 滇式月饼 | Illustrated icon | 与表格首列对齐的行标识 | no-crop | slice | Generated | 由 sheet_mooncake.jpg 第 2 行第 2 格切出 | none | local |
| cake_mold.png | 678×638 | 17:16 | 木质月饼模子 | Illustration element | 章页与转折页的主物件，可大幅出血 | no-crop | slice | Generated | 由 sheet_mooncake.jpg 第 2 行第 3 格切出 | none | local |
| letter_zhongqiu.png | 874×615 | 17:12 | 剪纸美术字「中秋」 | Decorative lettering | 封面显示层，与原生标题分置两处 | no-crop | slice | Generated | 由 sheet_lettering.jpg 第 1 行第 1 格切出；原生标题另行保留 | embedded | local |
| letter_yuexi.png | 845×620 | 15:11 | 剪纸美术字「月夕」 | Decorative lettering | 第一幕章页的幕标 | no-crop | slice | Generated | 由 sheet_lettering.jpg 第 1 行第 2 格切出；章名另有原生文字 | embedded | local |
| letter_yuebing.png | 871×614 | 17:12 | 剪纸美术字「月饼」 | Decorative lettering | 第二幕章页的幕标 | no-crop | slice | Generated | 由 sheet_lettering.jpg 第 2 行第 1 格切出；章名另有原生文字 | embedded | local |
| letter_tuanyuan.png | 855×606 | 24:17 | 剪纸美术字「团圆」 | Decorative lettering | 末页的收束标记 | no-crop | slice | Generated | 由 sheet_lettering.jpg 第 2 行第 2 格切出；结语另有原生文字 | embedded | local |
| cover_night_field_dawn.jpg | 1600×893 | 18:10 | 末页的同场景低能量变体 | Derivative | 满版铺底，比封面暗一档、偏金，作为首尾呼应的同一片海 | no-crop | ai | Generated | Derived from cover_night_field.jpg; treatment=duotone+brightness | none | local |
| mooncake_mold_wash.png | 678×638 | 17:16 | 表格页背后的超大低对比纹样 | Derivative | 放大出血的背景纹样，压在表格之下不与文字争对比 | no-crop | ai | Generated | Derived from cake_mold.png; treatment=grayscale+brightness+fit | none | local |
| changee_flight_scrim.png | 755×633 | 19:16 | 嫦娥页的远层虚影 | Derivative | 同一主体的远层：巨大、低对比，与前景清晰切片形成注册深度 | no-crop | ai | Generated | Derived from change_e.png; treatment=desaturate+brightness | none | local |

## IX. Content Outline

### Part 1: 起 — 一个说不清来历的熟悉节日

#### Slide 01 - 封面：一枚月饼里的八百年

- **Audience move**: 把中秋当成年年如此的习惯 → 意识到它是被一层层加上去的，且每一层有日期
- **Relationships**: 标题、副标题、时间落点三个单元为 link 关系；副标题给出全卷唯一的物证线索
- **Cover impact**: 钩子 = 「在南宋的一张菜单上，月饼还只是一味四时皆有的点心」——它与「团圆」毫无关系（binding）
- **Composition**: 整幅夜海铺底，左上三分之一竖排承载剪纸字与原生标题，右下低位放一弯细牙月，云带横掠中景；月亮此处最小最低，为全卷的上升留出空间
- **Title**: 中秋：一枚月饼里的八百年
- **Core message**: 今天所有关于中秋的常识，都是可以查到加入时间的
- **Content**:
  - 主标题「中秋：一枚月饼里的八百年」，剪纸字「中秋」作显示层，原生标题与之并置
  - 副标题：从南宋《梦粱录》的一味市井点心，到今天的团圆信物，近八百年
  - 落款行：2026 年中秋 · 9 月 25 日
- **Images**: cover_night_field.jpg 作干净全画布底层；moon_crescent、cloud_band、osmanthus_sprig 作透明切片叠放；letter_zhongqiu 作显示层，原生标题另置一处
- **Fact IDs**: F017, F019, F075

#### Slide 02 - 为什么偏偏是八月十五

- **Audience move**: 只知道「八月十五是中秋」 → 知道古人自己给出过两条理由：时序对半、月相恰圆
- **Relationships**: 时序理由与天象理由为 parent 关系（同属「古人自己的解释」），两者与 2026 年的具体日期为 link
- **Composition**: 一枚大剪圆作为模切窗口占据右半页，窗口内是月，窗口外是夜；左侧竖向排布两条理由，页面下缘压一道远山脊
- **Title**: 三秋恰半，蟾兔正圆
- **Core message**: 八月十五不是随意挑的，它同时满足时序的正中与月相的正圆
- **Content**:
  - 时序：《梦粱录》释名「此日三秋恰半，故谓之『中秋』」；因月色倍明又称「月夕」
  - 天象：此夜月亮最大最圆最亮；别称尚有秋节、仲秋节、八月节
  - 唐人欧阳詹《玩月》诗序的两句归纳：「稽于天道，则寒暑均，取于月数，则蟾兔圆」
  - 落到今年：2026 年中秋为公历 9 月 25 日（国办发明电〔2025〕7 号）
- **Images**: moon_half 作为圆形模切窗口的内容；mountain_ridge 贴下缘作背景纸层
- **Fact IDs**: F014, F002, F009, F075

#### Slide 03 - 第一幕 · 起

- **Audience move**: 准备听一个从祭仪讲到节日的段落
- **Relationships**: none
- **Composition**: 大面积夜场留白，剪纸字「月夕」居中偏右，盈凸月升到页面上三分之一，云带自左掠过
- **Title**: 一 · 起：从一场祭仪到一个节日
- **Core message**: 中秋先是礼，其次是诗，最后才是节
- **Content**:
  - 幕标「月夕」（剪纸字）＋原生章名
  - 一句引导：它花了大约一千年，才从祭仪变成假日
- **Images**: letter_yuexi 作幕标；moon_gibbous 相位推进；cloud_band 复用改变尺度
- **Fact IDs**: F014

#### Slide 04 - 周代的礼，唐代的诗

- **Audience move**: 以为中秋自古就是节日 → 知道「中秋」二字最早指时令与祭仪，唐代才因诗与神话成为风尚
- **Relationships**: 周代礼制与唐代风尚为 order 关系；111 首诗与 65 位诗人为该风尚的 evidence
- **Composition**: 左侧一列时间纸片（周—唐）自下而上叠起，右侧一枚大号数字压在水面月影之上
- **Title**: 先有「中秋夜迎寒」，一千年后才有赏月的诗
- **Core message**: 唐代把神话接进了月亮，赏月才从祭仪变成风尚
- **Content**:
  - 周代已有「中秋夜迎寒」「中秋献良裘」「秋分夕月」三类活动——此时的「中秋」是时令与祭仪
  - 唐人把中秋与嫦娥、吴刚等神话结合，赏月之风由此大兴
  - 证据：四万余首《全唐诗》中写八月十五赏月者 111 首，出自 65 位诗人之手
  - 唐人赏月的具体场景：寺院与观星台、泛舟水滨、登山望月、值宿宫禁、置酒赋诗联句，以及借月思念远人
- **Images**: moon_reflection 压在页面下缘的波形纸之间；osmanthus_sprig 自右上角斜出
- **Fact IDs**: F001, F003, F008, F010

#### Slide 05 - 北宋开封：一座通宵不睡的城

- **Audience move**: 抽象地知道「宋代中秋很热闹」 → 看见一条具体的、有酒有市声的街
- **Relationships**: 节前酒市与节夜城景为 order 关系；《东京梦华录》把中秋与其他岁时节日并列成条，是「已成节日」的 membership 证据
- **Composition**: 整幅夜市场景铺满，压一层暗色使文字可读；文字集中在右侧安静区，被云半掩的月落在右上
- **Title**: 「至午未间，家家无酒，拽下望子」
- **Core message**: 北宋把八月十五定成了节，开封的街替它作了证
- **Content**:
  - 北宋定八月十五为中秋节
  - 节前：「诸店皆卖新酒，重新结络门面彩楼花头……市人争饮，至午未间，家家无酒，拽下望子」
  - 节夜：「贵家结饰台榭，民间争占酒楼玩月。丝篁鼎沸……闾里儿童，连宵嬉戏。夜市骈阗，至于通晓」
  - 结构性证据：《东京梦华录》卷八「中秋」条与四月八日、端午、七夕、中元、立秋、秋社、重阳并列
- **Images**: kaifeng_night_market.jpg 作整幅页面场；moon_veiled 叠在右上与云带压边
- **Fact IDs**: F004, F011, F012, F013

#### Slide 06 - 南宋临安：连宵禁都为它让路

- **Audience move**: 认为节日热闹是富人的事 → 看到它已覆盖到「陋巷贫窭之人」，并让宵禁开了口子
- **Relationships**: 贵家、铺席之家、陋巷之人三层为 membership 关系；宵禁豁免与全民参与为 link
- **Composition**: 呼吸页 — 大片夜场，一对走月行人剪影置于下方偏左，一段引文竖排在右
- **Title**: 「虽陋巷贫窭之人……不肯虚度」
- **Core message**: 到南宋，中秋已经不分阶层，且是一整夜的事
- **Content**:
  - 阶层覆盖：「王孙公子，富家巨室，莫不登危楼，临轩玩月……至如铺席之家，亦登小小月台，安排家宴，团子女，以酬佳节。虽陋巷贫窭之人，解衣市酒，勉强迎欢，不肯虚度」
  - 时间覆盖：「此夜天街卖买，直到五鼓……盖金吾不禁故也」——这一夜宵禁不执行
- **Images**: walking_pair 小尺度剪影置于下缘波形纸之间
- **Fact IDs**: F015, F016

### Part 2: 饼 — 一个词的迁徙

#### Slide 07 - 第二幕 · 饼

- **Audience move**: 准备接受一次认知转折
- **Relationships**: none
- **Composition**: 剪纸字「月饼」居左，木质饼模大幅出血压在右下角，盈凸月升到右上
- **Title**: 二 · 饼：这个词，比这个习俗早三百年
- **Core message**: 「月饼」和「中秋送月饼」不是同时出现的
- **Content**:
  - 幕标「月饼」（剪纸字）＋原生章名
  - 一句设问：如果南宋人已经在吃月饼，他们为什么不在中秋送？
- **Images**: letter_yuebing 作幕标；cake_mold 大幅出血；moon_gibbous 复用改变位置
- **Fact IDs**: F017

#### Slide 08 - 从菜单到信物：四次转身

- **Audience move**: 以为月饼一直是中秋专属 → 看清它先是市井小吃，明代才被绑定到中秋与团圆，再成为社交货币
- **Relationships**: 四条文本记载构成严格的 order 关系（南宋 → 明中 → 明万历 → 明末），每一步是前一步的状态改变
- **Composition**: 一条自左向右上升的纸带串起四个时点，纸片依次抬高一层；两枚放大的月饼分别压在首尾两端
- **Title**: 南宋菜单上的点心，怎么变成一饼值数百钱
- **Core message**: 月饼被写进历史的顺序是：先有词，后有俗，再有价
- **Content**:
  - 南宋：「月饼」一词最早见于《梦粱录》卷十六「荤素从食店」，与芙蓉饼、菊花饼并列，「四时皆有，任便索唤」——不属于任何节日
  - 同时代：《武林旧事》把月饼列在临安五十余种蒸食之中
  - 明代绑定：《西湖游览志余》「八月十五日谓之中秋，民间以月饼相遗，取团圆之义」——时间、行为、意义三要素同时出现
  - 明万历：《宛署杂记》「八月馈月饼」条载「大小不等，呼为月饼。市肆至以果为馅，巧名异状，有一饼值数百钱者」
  - 明末：《帝京景物略》记北京月饼「饼有径二尺者」
- **Images**: cake_su 放大置于纸带起点；cake_jing 放大置于纸带终点；cake_mold 复用为小尺度接点
- **Fact IDs**: F017, F018, F019, F020, F021, F022

#### Slide 09 - 五个流派，一套国标

- **Audience move**: 只会说「广式苏式好吃」 → 能说出五派的饼皮工艺差别，并知道这是国家标准里的定义
- **Relationships**: 五个流派与四项属性构成 contrast 关系；五派与国标九派之间是 membership（五是九的一部分）
- **Composition**: 左列五枚月饼纵向排开与表格行对齐，右侧是四栏对照表；超大饼模纹样压在整页之下作低对比背景
- **Title**: 差别不在馅，在饼皮怎么起
- **Core message**: 五派月饼的分野是工艺分野，且写在现行国家标准里
- **Content**:
  - 依据：GB/T 19855—2023《月饼质量通则》，2023-09-07 发布、2024-04-01 实施，全部代替 2015 版
  - 国标按地方派式分九类：广式、京式、苏式、潮式、滇式、晋式、琼式、台式、哈式——本页讲其中五个
  - 广式：广东；加或不加糖浆制饼皮，包馅成形刷蛋后烘烤；口感柔软；蓉沙 / 果仁 / 蛋黄
  - 苏式：苏州；另以粉油制酥，制酥皮后包馅烘烤；成品具酥层、口感松酥；蓉沙 / 果仁 / 果蔬
  - 京式：北京；提浆工艺制糖浆皮，或制松酥皮 / 酥皮；口感松酥或松软；提浆 / 自来白 / 自来红 / 大酥皮
  - 潮式：潮汕；以小麦粉或食用淀粉及其制品加油脂制皮；酥皮 / 水晶皮 / 奶油皮
  - 滇式：云南；小麦粉和 / 或杂粮粉制皮，以云腿肉、果仁、食用花卉、食用菌为馅；云腿 / 食用花卉
  - 冷知识两条：果仁总量不低于 20% 且仅限核桃、杏、橄榄、瓜子、芝麻五仁加广东工艺，才叫「广式五仁」；莲子添加量 100% 才叫「纯莲蓉」，不低于 60% 叫「莲蓉」
  - 这不是学术分类：标准由中国商业联合会提出，起草单位含广州酒家利口福、北京稻香村、苏州稻香村、杏花楼等六十余家
- **Visualization**: mooncake-schools — 五个流派为列、产地/饼皮工艺/口感/代表品种四项为行的对照表
- **Native-ready**: mooncake-schools=yes
- **Images**: cake_guang、cake_su、cake_jing、cake_chao、cake_dian 五枚作行标识；mooncake_mold_wash.png 作整页低对比背景纹样
- **Fact IDs**: F032, F033, F035, F036, F037, F038, F039, F040, F041, F042, F043

### Part 3: 说 — 月亮里的三个人

#### Slide 10 - 第三幕 · 说

- **Audience move**: 准备接受第二次转折：熟悉的传说，细节多半记错了
- **Relationships**: none
- **Composition**: 满月首次以较大尺度出现在页面中上，云带自下托住，章名横排在月下
- **Title**: 三 · 说：月亮里的三个人，各自来自不同的书
- **Core message**: 嫦娥、吴刚、玉兔不是同一部书里的邻居
- **Content**:
  - 一句设问：嫦娥变成蟾蜍，出自《淮南子》吗？
- **Images**: moon_full 首次出现（中等尺度）；cloud_band 复用作托底中景
- **Fact IDs**: F023, F029, F031

#### Slide 11 - 嫦娥：一次避讳，一场千年误引

- **Audience move**: 认为「嫦娥奔月化为蟾蜍」出自《淮南子》 → 知道《淮南子》只写奔月、用「姮娥」，化蟾出自张衡《灵宪》，且「嫦」字来自避讳
- **Relationships**: 《归藏易》—《淮南子》—《灵宪》为 order（文本层次）；《淮南子》原文与流行说法为 contrast；避讳与名字变化为 parent
- **Composition**: 巨大的低对比嫦娥虚影铺在右半页作远层，清晰的小尺度嫦娥切片压在其上作近层；左侧竖排三段文本层次，蟾蜍与药壶两个小件分别落在对应段落旁
- **Title**: 《淮南子》里没有蟾蜍
- **Core message**: 我们熟悉的嫦娥，是三部书叠加出来的形象，其中一层还改过名字
- **Content**:
  - 现存最早完整记载：《淮南子·览冥训》「譬若羿請不死之藥於西王母，姮娥竊以奔月，悵然有喪，無以續之」
  - 关键核对：该段用字为「姮娥」而非「嫦娥」，且全段不含「蟾蜍」
  - 化蟾之说实出东汉张衡《灵宪》「姮娥遂托身于月，是为蟾蜍」
  - 更早一层：《归藏易》；刘勰《文心雕龙》称其「乃称羿毙十日，恒娥奔月」，1993 年出土秦简仅存「昔者恒我窃毋死之……奔月」两枚残简
  - 名字为何变：刘安编《淮南子》避汉文帝刘恒之讳，改「恒」为「嫦」，「恒我」遂演变为「嫦娥」与「姮娥」
- **Images**: changee_flight_scrim.png 作远层虚影；change_e 清晰切片作近层；toad 与 elixir_jar 两小件分列
- **Fact IDs**: F023, F024, F025, F026, F027, F028

#### Slide 12 - 吴刚与玉兔：一个徒劳，一个长跪

- **Audience move**: 把吴刚和玉兔当作气氛角色 → 记住各自的出处与其中的意象
- **Relationships**: 吴刚与玉兔为 contrast（徒劳的循环 vs 恒久的服务）；桂树与吴刚为 link
- **Composition**: 呼吸页 — 页面对半分给两个场景，中间不放分隔线而靠夜场留白断开；水面月影压在下缘串起两侧
- **Title**: 树创随合，长跪捣药
- **Core message**: 这两位的故事，一个讲无尽的重复，一个讲无尽的等待
- **Content**:
  - 吴刚伐桂始见于唐人段成式《酉阳杂俎》：「月桂高五百丈，下有一人常斫之，树创随合。人姓吴名刚，西河人，学仙有过，谪令伐树」
  - 更早的「月中有桂」见晋代虞喜《安天论》：「俗传月中仙人桂树……渐已成形，桂树后生焉」
  - 玉兔捣药见汉乐府《董逃行》：「玉兔长跪捣药蛤蟆丸，奉上陛下一玉盘，服此药可得神仙」——所捣者是蛤蟆丸
  - 桂的余脉：中秋饮桂花酒的习俗与吴刚伐桂相连
- **Images**: wu_gang 与 osmanthus_tree 成对置于左半页；jade_rabbit 置于右半页；moon_reflection 复用压在下缘
- **Fact IDs**: F029, F030, F031, F064

### Part 4: 俗与今 — 从一夜的火光到一天的假期

#### Slide 13 - 一夜之内，中国有多少种过法

- **Audience move**: 以为中秋各地都是吃饼赏月 → 看到火龙、烧塔、灯杆、骰子、走月这些互不相同的具体做法
- **Relationships**: 五种习俗为 membership（同属中秋夜的地方实践），彼此并列无先后；火龙的起源与做法为 parent
- **Composition**: 火龙斜向贯穿整页并出血，其余四件按不同尺度与角度散落在它两侧，不排成等距一行；文字贴各自的物件而非集中成块
- **Title**: 同一个晚上，有人扎火龙，有人掷骰子
- **Core message**: 中秋从来不是一种过法，而是几十种地方实践共用一个日子
- **Content**:
  - 香港大坑舞火龙：相传光绪六年（1880）大坑发生瘟疫，村民扎火龙巡游驱瘟；做法是在龙骨内插满点燃的线香；八月十四晚在莲花宫开光，连巡三晚，十六晚「游大运」后投龙入海，称「龙归天」
  - 燃灯与树中秋：湖广以瓦片叠塔燃灯称「瓦子灯」，江南有灯船；广东、香港把各式彩灯竖于高杆，称「树中秋」
  - 江西烧塔：流行于赣州、吉安、萍乡、上饶，尤以安福为盛；分垒塔、烧塔、封塔三段
  - 厦门博饼：六个骰子轮流投掷，博状元至秀才六个等第，按等第取大小不同的月饼
  - 走月：衣着华美三五结伴，游街市、泛舟或登楼观月华；明代曾有望月楼、玩月桥
- **Images**: fire_dragon 斜向贯穿并出血；lantern_tower、lantern_pole、dice_bowl、walking_pair 以不同尺度与角度散落
- **Fact IDs**: F053, F054, F055, F056, F062, F057, F047, F063

#### Slide 14 - 名录上的中秋：一个编号，五个地方

- **Audience move**: 把非遗当成一个笼统的荣誉 → 知道中秋节在名录里是一个共用编号下的五条记录，各由不同地区申报
- **Relationships**: 主项与四个扩展项为 parent 关系（共用 Ⅹ-5 / 453）；兔儿爷与中秋节为 link 但分属不同名录条目（contrast）
- **Composition**: 超大编号「Ⅹ-5」作为页面锚点压在左侧，右侧五条记录像五张叠起的纸签自上而下排布；兔儿爷剪影单独站在右下角并被一条注释线牵出
- **Title**: 同一个编号 Ⅹ-5，写着五个地方的名字
- **Core message**: 中秋节的非遗身份是一个主项加四个地方扩展项，不是一块笼统的牌子
- **Content**:
  - 名录本体：国发〔2006〕18 号，2006 年 5 月 20 日公布第一批国家级非遗名录，共 518 项、十个类别，其中民俗类 70 项
  - 中秋节（主项）：编号 Ⅹ-5、序号 453、民俗类，2006 年第一批，文化部申报，文化和旅游部保护
  - 中秋节（中秋博饼）：2008 年第二批，福建省厦门市
  - 中秋节（泽州中秋习俗）：2011 年第三批，山西省泽州县；珏山有「中国赏月名山」之称，核心仪式为拜「月婆婆」
  - 中秋节（秋夕）：2011 年第三批，吉林省延边朝鲜族自治州；含茶礼、省墓、荐新与摔跤、秋千
  - 中秋节（大坑舞火龙）：2011 年第三批，香港特别行政区
  - 不要合并表述：泥塑（北京兔儿爷）是另一条目——编号 Ⅶ-47、序号 346、传统美术类、2014 年第四批；造型兔首人身、着红袍披金甲、手持捣药杵，工艺有「三分塑七分彩」之说
- **Images**: rabbit_lord 单独置于右下并以注释线牵出说明
- **Fact IDs**: F044, F045, F046, F049, F050, F051, F052, F053, F059, F060, F061

#### Slide 15 - 2008 年起，它成了一天法定假

- **Audience move**: 以为中秋一直放假、且法定就是三天 → 知道 2008 年才成为法定节假日，法定天数始终是一天，三天是调休的结果
- **Relationships**: 1949 年发布与四次修订为 order；「法定 1 天」与「实际 3 天」为 contrast；出游与产业数字为该节日现状的 evidence
- **Composition**: 上半页是一条横向时间纸带（1949 → 2007/2008 → 2024/2025 → 2026），下半页三个大号数字各坐一张纸片，尺度不等；盈凸月退到右上角小尺度
- **Title**: 法定是一天，我们过的是三天
- **Core message**: 中秋成为法定假日只有十八年，而且法定天数从来只有一天
- **Content**:
  - 《全国年节及纪念日放假办法》1949 年 12 月 23 日由政务院发布，此后四次修订
  - 2007 年第二次修订由国务院令第 513 号公布、2008 年 1 月 1 日起施行，新增「（六）中秋节，放假 1 天（农历中秋当日）」——中秋自此成为法定节假日
  - 2024 年第四次修订（国令第 795 号，2025 年 1 月 1 日施行）增加除夕与 5 月 2 日，中秋法定假期仍为 1 天
  - 口径提醒：2026 年中秋「9 月 25 日至 27 日放假共 3 天」是调休后的实际假期；且与国庆假期彼此分离
  - 规模一：2024 年中秋假期（同为独立三天）全国国内出游 1.07 亿人次，出游总花费 510.47 亿元，按可比口径较 2019 年同期增长 6.3% 和 8.0%
  - 规模二：中国焙烤食品糖制品工业协会预计 2024 年中秋月饼产量约 30 万吨、销售额约 200 亿元；全国月饼相关企业约 1.89 万家，广东省居首
- **Images**: moon_gibbous 复用，退到右上角最小尺度
- **Fact IDs**: F071, F072, F073, F074, F075, F076, F077, F080

#### Slide 16 - 但愿人长久

- **Audience move**: 记住了一串时点 → 带走一个可以今晚就用的句子，并知道它是谁在什么处境下写的
- **Relationships**: 词的写作处境与词句为 parent 关系；千年前的分离与今夜的团圆为 link
- **Closing impact**: 收束句 = 「这条线的末端是今晚：同一轮月亮，第九百五十次照着有人在等另一个人」——落到 1076 年苏轼与苏辙分别七年这个具体处境（binding）
- **Composition**: 满月升到全卷最大、最高、居中；同一片夜海以更暗更偏金的变体铺底，与封面首尾呼应；词句竖排在月的一侧，剪纸字「团圆」压在页脚
- **Title**: 但愿人长久，千里共婵娟
- **Core message**: 中秋最后留下的不是考据，是一个人在异乡写给弟弟的一句话
- **Content**:
  - 处境：苏轼因与变法者政见不同自求外放，1074 年差知密州；作此词时与胞弟苏辙分别已七年未得团聚
  - 小序：「丙辰中秋，欢饮达旦，大醉，作此篇，兼怀子由」——丙辰即熙宁九年，公元 1076 年
  - 上片：「明月几时有？把酒问青天……起舞弄清影，何似在人间。」
  - 下片：「转朱阁，低绮户，照无眠……人有悲欢离合，月有阴晴圆缺，此事古难全。但愿人长久，千里共婵娟。」
  - 收束：从《梦粱录》记下「月饼」二字到今天近八百年，从这首词到今天九百五十年；今晚的月亮还是同一轮
- **Images**: cover_night_field_dawn.jpg 作整幅底纸与封面呼应；moon_full 全卷最大尺度居中；letter_tuanyuan 压在页脚
- **Fact IDs**: F066, F067, F068, F069, F070

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页讲稿以页面上的可见状态为锚，先接上一页的悬念，再说清本页的一个判断，最后抛出通向下一页的问句；古籍引文在讲稿中口语化转述而不逐字念读；所有可外部核实的数字与年份只使用页面已引的 fact，讲稿不得引入新的外部断言
- **Total duration**: 约 25 分钟（16 页，平均每页 80–110 秒，章页更短）
- **Notes style**: conversational — 像和听众聊天而不是念报告，用设问制造悬念，用「差不多三分之一」这类口语化说法处理数据
- **Presentation purpose**: 先用「月饼」一词的迁徙把中秋从习惯变成历史，再解释每个熟悉意象的加入时点，最后落回今天的假期与数字

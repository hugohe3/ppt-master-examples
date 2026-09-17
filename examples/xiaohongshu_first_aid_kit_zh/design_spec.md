<!-- ppt-master-schema: design-spec/v1 -->
# first_aid_kit_zh_xhs_20260917 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | first_aid_kit_zh_xhs_20260917 |
| Canvas Format | 小红书 (RED) 1242×1660,3:4 竖版 |
| Page Count | 9 |
| Primary Language | zh-CN |
| Target Audience | 中国大陆普通家庭的小红书读者(非医护),多为家里有孩子或老人、想把急救包一次性配齐的人 |
| Communication Intent | 先让读者认清"四类齐全"这个骨架并照着配齐,再让他清掉家里不该留的旧药,最后教会两条最常用的现场处置流程;科普与动员并重,动员优先 |
| Desired Audience Outcome | 读者能照着清单把急救包配齐、把红药水紫药水和过期药清出去、给急救包定一个固定位置和 3 个月的检查节点,并在割伤或烫伤发生时按流程处置而不是凭土办法 |
| Core Message / Ask / Action | 急救包不是囤药,是"止血包扎 + 消毒 + 常用药 + 工具"四类齐全、位置固定、每 3 个月一查;今天就把红药水紫药水和过期药清出去 |
| Delivery Context | 主要为小红书图文轮播的手机端自读,无讲者,任何一张被单独转发也要读得懂;次要为社区急救科普小课的投屏讲解 |
| Artifact Afterlife | 读者长按保存的清单总表;社区讲课可复用的素材 |
| Reading Mode | text |
| Content Strategy | 自由重组研究材料成轮播叙事,页面顺序与标题由沟通目标决定;但医学类说法一律带出处与年份,国内外口径冲突时取国内官方口径并在页面上写明存在争议的条目 |
| Design Style | 手帐急救课(custom mode + custom visual style,暖米纸手绘手帐) |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 用户原话"我也会拿 PPT 去社区讲",委托确认下按最新显式用户意图启用 |
| Custom Animations | enabled — 用户原话"要有动画",委托确认下按最新显式用户意图启用,范围为逐页对象动画加相邻页 Morph 转场 |
| Narration Audio | disabled — 用户未提旁白,委托确认下取工作流默认值 |
| Created Date | 2026-09-17 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | 小红书 |
| Dimensions | 1242 × 1660 |
| viewBox | `0 0 1242 1660` |
| Margins | 上下左右各 88px;底部另留 104px 出处条带 |
| Content Area | x 88–1154(宽 1066),y 88–1468(高 1380),出处条带占 y 1468–1572 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: instructional
- **Mode Behavior**: 按"先给骨架、再逐类展开、再纠错、再落地、最后给两条现场流程和一张总表"的学习顺序推进;页标题写这一页教什么,不写论断;同级的四个类别用同一形状、同一深度并列展开,便于读者在脑子里映射;每一条处置步骤都先给动作、再给参数、再给"别做什么"的注记,注记永远挂在它解释的那一步旁边而不是独立成段。
- **Visual style**: custom
- **Visual Style References**: sketch-notes, editorial
- **Visual Style Behavior**: 由 sketch-notes 提供主体质地——暖米纸底、带轻微手抖的黑墨轮廓、略微溢出边线的柔和色块、稀疏的手绘小装饰与波浪箭头、全平面无投影;由 editorial 提供竖版所需的纵向层级——眉题(kicker)、发丝分隔线、一条贯穿页面的纵向标尺挂载内容、超大序号或数字作为页面锚点、非均分的不对称分栏。两者的分工是:形状与质地归手绘,秩序与层级归编辑排版,避免手帐感变成散乱的涂鸦板。
- **Theme**: 一本摊开的家庭急救手帐——每一页都像手写在暖米纸上的一页笔记,靠一条贯穿左侧的纵向标尺和统一的手绘圆角卡片维持九页的同一性;跨页母题是"急救箱开合":封面是合着的箱子,P02 打开成四格,P07/P08 变成同一条手绘步骤链,P09 收拢成一张可保存的总表。
- **Tone**: 可靠、克制、不吓人;像社区里一位耐心的护士在纸上一条条写给你

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FBF6EC | 暖米纸主底,九页统一 |
| Secondary background | #F2E8D5 | 分区色块、表格隔行、次级卡片底 |
| Primary | #1F6F5C | 墨绿,页标题、纵向标尺、主要图标与正向结构色 |
| Accent | #D94F3D | 急救红,仅用于超大标题字、十字/警示图形与重点标记,不作正文色 |
| Secondary accent | #E8A33D | 暖橙,提醒类注记、检查周期、时间参数 |
| Body text | #2B2A26 | 墨黑正文与手绘轮廓线 |
| Secondary text | #6B6558 | 说明、出处、页码指示 |
| Divider | #D9CDB8 | 发丝线、表格线、卡片边 |

补充锁定的语义中性层与极性角色:`surface` #FFFDF7(卡片纸面)、`block-shade` #EFE3CC(手绘色块的低饱和铺底)、`positive` #3F8F5B(该留/正确做法)、`warning` #E8A33D(注意事项)、`negative` #C0392B(该清出去/禁止做法)。Accent 与 negative 对纸底对比度约 3.8:1,因此只用于 56px 以上的大字与图形,正文与注记一律使用 body text 或 secondary text。

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: sketch-notes
- **Visual**: 暖米纸底上的黑墨手绘线稿,线条带轻微手抖、粗细均匀;色块是从墨绿/暖橙/急救红派生出的低饱和柔和平涂,并略微溢出轮廓线,呈手绘上色的错位感;物体简化到可辨识即可,不追求解剖级细节;画面留白充裕,无投影、无渐变、无高光。
- **Mood**: 温和、可靠、像社区诊室墙上贴的手绘科普图,或一位老师在教学笔记本上画给你看的示意图
- **Image Rendering Behavior**: 手绘教学笔记风格——黑墨轮廓带轻微手抖,色块从 deck 的墨绿、暖橙、急救红三个角色派生为低饱和柔和平涂并略微溢出轮廓,纸面带 8–12% 的纸纹;深度完全平面,不加投影与渐变;偶有极少量手绘小装饰(短线、圆点)增加温度。九张图共用同一线宽与同一上色错位量,以此保证一致性。

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 无衬线/厚重,像马克笔写在纸上的板书标题 | SimHei | Arial Black | sans-serif |
| Body | 无衬线/人文清晰,长时间手机阅读不累 | Microsoft YaHei | Arial | sans-serif |
| Display | 无衬线/超粗,用于封面主标 | SimHei | Arial Black | sans-serif |
| Hero number | 无衬线/超粗,用于页面英雄数字(3 个月、20 分钟) | SimHei | Arial Black | sans-serif |
| Annotation | 无衬线/清晰小字,与正文同族以免手帐页面出现第三种字味 | Microsoft YaHei | Arial | sans-serif |
| Footnote | 无衬线/清晰小字,承载出处条与页序指示 | Microsoft YaHei | Arial | sans-serif |

- **Title stack**: SimHei, Arial Black, sans-serif
- **Body stack**: Microsoft YaHei, Arial, sans-serif
- **Display stack**: SimHei, Arial Black, sans-serif
- **Hero number stack**: SimHei, Arial Black, sans-serif
- **Annotation stack**: Microsoft YaHei, Arial, sans-serif
- **Footnote stack**: Microsoft YaHei, Arial, sans-serif
- **Role rationale**: Display 与 Title 同族但独立成锚,因为封面主标 128px 与英雄数字 96px 在九页里反复出现,不能依赖 Executor 的 ±2px 带;Annotation / Footnote 与 Body 同族,只是尺寸角色,单独声明是为了让出处条、注记、页序指示在九页之间保持同一字号。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 44 |
| Title | 80 |
| Subtitle | 56 |
| Annotation | 32 |
| Display (cover title) | 128 |
| Hero number | 96 |
| Lead | 52 |
| Kicker | 36 |
| Step number | 48 |
| Table cell | 36 |
| Footnote | 26 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 竖版从上往下读——眉题 → 页标题 → 一句核心判断 → 分块内容 → 底部出处条;每页只给一个视觉主角(一张插画、一个英雄数字、一条步骤链或一张表),其余元素退为支撑。
- **Composition tendency**: 纵向堆叠优先,横向最多二等分;左侧一条贯穿全页的纵向标尺(墨绿细线加节点)承担"这是同一本手帐"的连续性;分类内容用非均分的上下带状分区而不是均匀卡片网格;每页至少有一处让内容越出分区边界(插画压线、序号出框)以打破网格感。
- **Cross-page continuity**: 纵向标尺、眉题位置、底部出处条、页序指示九页不变;插画风格、线宽、上色错位量不变;卡片圆角与色块用法不变。变化的是分区节奏、主角类型与色块的主色。
- **Spacing posture**: variable by page rhythm——anchor 页(P01/P02/P09)大留白,dense 页(P03–P08)压缩块间距但保持行距不变
- **Spacing anchors**: page margin 88px · block gap 48px · column gutter 40px · corner radius 28px · body leading 72px

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| tabler-outline/first-aid-kit | 急救包本体、总览、封面与总表的身份标记 |
| tabler-outline/bandage | 止血包扎类目、创可贴与敷料相关条目 |
| tabler-outline/vaccine-bottle | 消毒类目、碘伏与生理盐水等瓶装物 |
| tabler-outline/pills | 常用药类目、按用途分类的药品条目 |
| tabler-outline/thermometer | 工具类目中的体温计、体征测量 |
| tabler-outline/scissors | 工具类目中的圆头剪刀、剪开粘连衣物 |
| tabler-outline/droplet | 冲洗、生理盐水、流动水相关动作 |
| tabler-outline/flame | 烫伤主题标记 |
| tabler-outline/alert-triangle | 注意事项、争议条目、必须就医的判断 |
| tabler-outline/trash | 清理出去、过期药处置 |
| tabler-outline/calendar-repeat | 每 3 个月自查、每年彻底复核 |
| tabler-outline/clock-hour-3 | 时间参数(冲洗时长、浸泡时长、止血带时限) |
| tabler-outline/phone-call | 拨打 120、紧急联系电话 |
| tabler-outline/ban | 禁止做法(红药水紫药水、冰敷、挑破水疱) |
| tabler-outline/hand-stop | 直接压迫止血、用手掌按压的动作 |
| tabler-outline/mask | 医用外科口罩、施救前防护 |
| tabler-outline/shield-check | 防护到位、正确做法确认 |
| tabler-outline/cut | 割伤主题标记 |
| tabler-outline/tools | 工具类目总标记 |
| tabler-outline/bottle | 液体类物品(酒精、碘酊、双氧水)与该清出去的旧药瓶 |
| tabler-outline/stethoscope | 就医、专业处置 |
| tabler-outline/medical-cross | 急救身份标记、总表页页眉 |
| tabler-outline/snowflake | 不要冰敷、低温相关禁忌 |
| tabler-outline/bath | 别放卫生间的存放禁忌 |
| tabler-outline/clipboard-list | 检查五步、清单与记录 |
| tabler-outline/home | 存放位置、家庭场景 |
| tabler-outline/bulb | 手电筒、提示与小知识 |
| tabler-outline/emergency-bed | 送医、必须就医的判断 |
| tabler-outline/circle-number-1 | 流程步骤序号 |
| tabler-outline/circle-number-2 | 流程步骤序号 |
| tabler-outline/circle-number-3 | 流程步骤序号 |
| tabler-outline/circle-number-4 | 流程步骤序号 |
| tabler-outline/circle-number-5 | 流程步骤序号 |
| tabler-outline/arrow-narrow-right | 步骤之间的推进指向 |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P09 | table | record_table | 把四类必备物品与两条"该清出去"逐条列成可长按保存的总表,每行一件物品,列为分类 / 物品 / 要点 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_kit.jpg | 1792×2400 | 3:4 | 封面主视觉:一只摊开的家用急救包 | Illustration | 满幅竖版底图,上三分之一留白让主标与钩子句落在纸面上,物件集中在下三分之二 | adaptive | ai | Generated | 俯视一只打开的布质家用急救包,内容物向外摊开:纱布卷、绷带、创可贴盒、碘伏小瓶、棉签、圆头剪刀、镊子、体温计、一次性手套。构图为竖版,画面上三分之一为空白暖米纸,物件在下三分之二呈散开的放射状,视线落点在正中的急救包本体 | none | hero_page |
| kit_bandage.jpg | 715×688 | 1.04:1 | 止血包扎类目图 | Illustrated icon | 类目标题左侧的图示,与同页另外三格同尺寸并列 | no-crop | slice | Generated | Derived from illus_sheet_a.png; cell=1 | none | local |
| kit_antiseptic.jpg | 685×682 | 1.00:1 | 消毒类目图 | Illustrated icon | 类目标题左侧的图示,与同页另外三格同尺寸并列 | no-crop | slice | Generated | Derived from illus_sheet_a.png; cell=2 | none | local |
| kit_medicine.jpg | 757×656 | 1.15:1 | 常用药类目图 | Illustrated icon | 类目标题左侧的图示,与同页另外三格同尺寸并列 | no-crop | slice | Generated | Derived from illus_sheet_a.png; cell=3 | none | local |
| kit_tools.jpg | 819×726 | 1.13:1 | 工具类目图 | Illustrated icon | 类目标题左侧的图示,与同页另外三格同尺寸并列 | no-crop | slice | Generated | Derived from illus_sheet_a.png; cell=4 | none | local |
| no_old_drugs.jpg | 804×772 | 1.04:1 | "该清出去"的旧药瓶与拆开的旧药板 | Illustrated icon | 放在禁止区块内,与手绘禁止符号叠合 | no-crop | slice | Generated | Derived from illus_sheet_b.png; cell=1 | none | local |
| kit_storage.jpg | 870×817 | 1.06:1 | 存放位置示意:抽屉柜里的急救包 | Illustrated icon | 存放区块右侧的图示,与左侧的位置条目并排 | no-crop | slice | Generated | Derived from illus_sheet_b.png; cell=2 | none | local |
| cut_press.jpg | 860×837 | 1.03:1 | 直接压迫止血动作示意 | Illustrated icon | 压在"压"这一步的步骤节点旁,与序号同高 | no-crop | slice | Generated | Derived from illus_sheet_b.png; cell=3 | none | local |
| burn_water.jpg | 857×805 | 1.06:1 | 流动自来水冲洗烫伤动作示意 | Illustrated icon | 压在"冲"这一步的步骤节点旁,与序号同高 | no-crop | slice | Generated | Derived from illus_sheet_b.png; cell=4 | none | local |

## IX. Content Outline

### Part 1: 先把骨架立住

#### Slide 01 - 封面:家用急救包怎么配

- **Audience move**: 以为家里"有个药箱就算有急救包"→ 意识到只囤药、不备纱布碘伏,真出血时会直接卡壳
- **Relationships**: 三个单元——主标题、钩子判断句、权威出处署名;钩子句是主标题的 link(说明为什么值得看),署名是钩子句的 parent(它的可信度来源);none 之外无其他关系
- **Composition**: 满幅手绘急救包底图,上三分之一暖米纸留白承载主标与钩子句;主标超大,钩子句一行,底部一条细线压出处
- **Cover impact**: 钩子(binding)——"只囤药、不备纱布碘伏,真出血时直接卡壳";构图为 Reference
- **Title**: 家用急救包怎么配
- **Core message**: 家里那盒药不等于急救包,四类齐全才算
- **Content**: 主标题"家用急救包怎么配" · 钩子句"只囤药、不备纱布碘伏,外伤时直接卡壳" · 副标"9 图讲清:配什么 / 别放什么 / 放哪儿 / 怎么用" · 出处署名"依据:应急管理部、北京急救中心、国家药监局科普(2020—)"
- **Images**: cover_kit.jpg 作为满幅底图,不裁掉散开的物件边缘
- **Motion suggestion**: 封面中央的急救包本体在 P02 变成四格类目板,是本页与下一页之间的 Morph 候选;本页内的语义顺序为主标 → 钩子句 → 出处署名
- **Fact IDs**: F025
- **page_rhythm**: anchor

#### Slide 02 - 记住四类,比记数量有用

- **Audience move**: 面对网上几十项的清单不知从何下手 → 记住"止血包扎 / 消毒 / 常用药 / 工具"四类,能自己判断家里缺哪一类
- **Relationships**: 四个类目是同级 membership(共同构成一个完整的急救包),彼此之间无先后;两份官方目录是这四类的 parent(分类依据来源)
- **Composition**: 四格等重的手绘卡片纵向 2×2 排布,每格一张类目插画加一个类目名加一句作用;上方一句核心判断,下方一行官方目录署名
- **Title**: 记住四类,比记数量有用
- **Core message**: 急救包齐不齐,看四类是否都在,不看件数多少
- **Content**: 核心判断"齐不齐看四类,不看件数" · 止血包扎:先止住、先盖住 · 消毒:清洁创面、降低感染 · 常用药:对症备用,不盲目囤货 · 工具:让施救者能动手、能防护 · 分类依据:应急管理部《全国基础版家庭应急物资储备建议清单》(2020-11-29)与北京急救中心《家庭医疗应急物品指导目录》(2020-08-02);前者是家庭应急口径,后者才是医疗急救口径
- **Images**: kit_bandage.jpg / kit_antiseptic.jpg / kit_medicine.jpg / kit_tools.jpg 四张同尺寸并列,分别落在四格卡片内,四张共用同一线宽与上色错位量
- **Motion suggestion**: 承接 P01 的急救包本体展开为四格;四格类目板整体在 P03 被继承并只保留前两格放大,是与下一页之间的 Morph 候选;本页内语义顺序为核心判断 → 四类依次 → 署名
- **Fact IDs**: F001, F014, F015, F010, F009, F012, F011
- **page_rhythm**: anchor

### Part 2: 四类里具体配什么

#### Slide 03 - 第一类·止血包扎 / 第二类·消毒

- **Audience move**: 只知道要买"纱布和消毒水" → 知道具体买哪几样、买什么规格,以及碘伏为什么优于酒精碘酒
- **Relationships**: 两个类目并列 membership,组内各条目同级;"碘伏可直接用于伤口"与"酒精碘酒只能用于伤口周围"构成 contrast;禁忌注记是它所解释条目的 link
- **Composition**: 上下两条带状分区,上带止血包扎、下带消毒;每带左侧类目插画压住分区边界,右侧纵向条目清单;禁忌注记以手绘短线挂在对应条目右侧
- **Title**: 第一类·止血包扎,第二类·消毒
- **Core message**: 止血包扎按"盖 - 包 - 固定"配齐,消毒首选碘伏加生理盐水
- **Content**: 止血包扎:无菌纱布(3×3、4×4 英寸各 5 片)· 弹力绷带(3 英寸、4 英寸各 1 卷)· 三角巾 2 条 · 多尺寸创可贴约 25 片 · 医用胶带 1 卷 · 消毒:医用碘伏加无菌棉签或棉球——碘伏对皮肤黏膜无刺激无腐蚀,可直接用于伤口并在创面形成保护膜 · 0.9% 生理盐水——冲洗伤口最好的处理方法 · 消毒湿巾用于清洁伤口周围皮肤 · 注记:碘过敏者禁用碘伏,甲亢病人慎用 · 注记:数量参考美国红十字会四口之家最小配置,按家庭人数增减
- **Images**: kit_bandage.jpg 与 kit_antiseptic.jpg 各压一条分区边界,与 P02 同一张切片复用以保持类目身份
- **Motion suggestion**: 本页的两条带状分区继承自 P02 的前两格类目卡片,是与上一页之间的 Morph 候选;本页内语义顺序为止血包扎条目 → 消毒条目 → 两条禁忌注记,注记必须在其所解释的条目之后出现
- **Fact IDs**: F010, F004, F005, F009, F016, F017, F006
- **page_rhythm**: dense

#### Slide 04 - 第三类·常用药 / 第四类·工具

- **Audience move**: 把家里所有药一股脑塞进急救箱 → 按五个用途备药、按家庭成员追加,并知道工具类才是外伤时真正动手的部分
- **Relationships**: 两个类目并列 membership;"按用途备的通用药"与"按家庭成员追加的专用药"是 parent-child;工具组内条目同级
- **Composition**: 与 P03 同构的上下两条带状分区,保持同一边界位置与同一插画压线方式;常用药带内再分"五用途"与"按人追加"两小块
- **Title**: 第三类·常用药,第四类·工具
- **Core message**: 常用药按五个用途备、按家里人追加;工具齐了才动得了手
- **Content**: 常用药按五个用途:退烧止痛 / 抗过敏 / 肠胃应急 / 外用止痛 / 清凉解暑,对症备用,不盲目囤货 · 按家庭成员追加:确诊冠心病的老人常备硝酸甘油片或速效救心丸与上臂式电子血压计;有小孩的家庭补儿童退热药、退热贴、无菌敷贴、蚊虫叮咬膏、生理盐水洗鼻剂 · 加上本人长期服用的药和写好的紧急联系电话 · 工具:一次性医用外科手套 · 医用圆头剪刀 · 镊子 · 电子体温计(非水银非玻璃)· 电子血压计(定期检查电量与校准)· 护目镜与医用外科口罩 · 急救毯 · 带单向阀的人工呼吸面膜 · 手电筒(建议放床头)· 注记:本页只给品类,具体用药遵医嘱或看说明书,不给剂量
- **Images**: kit_medicine.jpg 与 kit_tools.jpg 各压一条分区边界,沿用 P02 的同一批切片
- **Motion suggestion**: 本页的两条带状分区与 P03 完全同构,是与上一页之间的 Morph 候选(分区框架保持、内容替换);本页内语义顺序为五用途 → 按人追加 → 工具条目 → 用药注记
- **Fact IDs**: F012, F013, F008, F011, F015, F007, F003
- **page_rhythm**: dense

### Part 3: 该清出去的和该定下来的

#### Slide 05 - 这几样,今天就清出去

- **Audience move**: 觉得红药水紫药水是"老经验、总没错" → 知道它们含汞、有潜在致癌风险且消毒不可靠,并知道清出来的药该怎么扔
- **Relationships**: 四个该清的条目同级 membership,与 P03/P04 的"该留"条目构成 contrast;"清出来怎么扔"是这组条目的 order 后继;"止血粉"是一条被标注的争议 overlap(两份官方材料口径不一致)
- **Composition**: 上部一块低饱和禁止区,四个该清条目纵向排列,每条左侧一个手绘禁止标记;下部一条独立的处置带,横向三步;最下方一条细边争议注记
- **Title**: 这几样,今天就清出去
- **Core message**: 红药水、紫药水、直接上伤口的酒精碘酒和过期药,都该离开急救包
- **Content**: 红药水(红汞、汞溴红):穿透力弱、抑菌小、消毒效果不可靠,含汞对人体有毒,大面积擦伤时可能造成大块皮肤坏死 · 紫药水(龙胆紫、甲紫):深或脏的伤口易在痂下积存脓液,且被发现是潜在致癌剂 · 药监口径:最好不用红汞、龙胆紫涂擦伤口,红汞还不能与碘酊混用或同一部位先后使用 · 酒精与碘酒:只能消毒伤口周围皮肤,不能直接涂在伤口上;碘酊涂后还需用 75% 酒精脱碘 · 过期药与变质药:药效全无还可能引发不良反应;变色、粘连、变硬变软、开裂缺角的,即使没到有效期也别用 · 清出来怎么扔:破坏药品包装盒后随生活垃圾分散丢弃,或送到正规回收点集中无害化处理 · 争议注记:止血粉在应急管理部清单里被列入外用药品,但国防部科普明确不建议用于伤口(刺激创面、盖住伤口、影响医生二次处理),本清单不列为必备
- **Images**: no_old_drugs.jpg 叠在禁止区左上,与手绘禁止符号重叠
- **Motion suggestion**: 四个该清条目按语义顺序逐条出现,每条的理由注记紧随该条之后;处置带整体在四条之后出现;争议注记最后出现
- **Fact IDs**: F018, F019, F020, F024, F021, F022, F025, F026, F075, F073, F072, F002, F028
- **page_rhythm**: dense

#### Slide 06 - 放哪儿,多久查一次

- **Audience move**: 急救包塞在某个柜子深处、几年没动 → 给它定一个固定位置和 3 个月的检查节点,并知道一次检查要做哪五件事
- **Relationships**: "放哪儿"与"多久查"是两个并列单元;每条存放要求与其禁忌(别放卫生间、别放手套箱)是 contrast;检查五步是 order
- **Composition**: 上半存放区,左侧条目右侧插画;下半检查区,以一个超大"3 个月"数字作为锚点,右侧纵向五步序号链;保质期参考压在页面底部作为一条细带
- **Title**: 放哪儿,多久查一次
- **Core message**: 阴凉干燥、儿童够不着但大人一伸手就到;每 3 个月自查一次,每年彻底翻一次
- **Content**: 放哪儿:阴凉干燥、通风避光,远离炉灶、水槽和发热电器;抽屉、橱柜、储物盒、壁橱都可以 · 别放卫生间:淋浴与洗手台的高温潮气会让药品在有效期前变质 · 儿童看不见也够不着,最好放在带儿童安全锁扣的柜子里 · 位置要让家里成年人都熟悉、都能一伸手拿到 · 车上可以另放一个急救包,但药品不要放在汽车手套箱(可能过热、过冷或受潮)· 多久查:每 3 个月自查 1 次(查有效期、查工具是否完好、补齐缺失、换掉过期破损);每年再彻底复核一次,没有有效期标注的逐件判断是否还能用 · 检查五步:开合与箱体是否完好 → 逐件查包装破损污渍渗漏与有效期 → 清理箱内灰尘碎屑 → 更换过期或损坏的物品 → 记录检查时间并把记录留在箱边 · 保质期参考:胶带、敷料、纱布绷带、无菌纱布、冰袋、手套、剪刀、镊子在包装完好时可达 5 年;酒精湿巾与抗生素软膏约 2 年;创可贴与胶布的黏性会随时间下降,纱布包装受潮或变色即使未过期也应更换
- **Motion suggestion**: 存放条目按语义顺序出现,每条的禁忌注记紧随其后;"3 个月"英雄数字在存放区讲完之后单独出现,五步序号链再依次接上;保质期细带最后出现
- **Images**: kit_storage.jpg 放在存放区右侧,与左侧条目并排
- **Fact IDs**: F029, F033, F030, F031, F032, F034, F035, F036, F037, F040, F038, F039
- **page_rhythm**: dense

### Part 4: 两条最常用的现场流程

#### Slide 07 - 割伤出血:压住、盖上、别揭

- **Audience move**: 出血时手忙脚乱、想着先找药水 → 知道分小伤口与大出血两条路,并记住"直接压迫、渗血不揭敷料、不拔大异物"三条硬规则
- **Relationships**: 一个分支点(伤口深浅/是否止得住)下挂两条 order 序列;小伤口序列四步,大出血序列五步;每条禁忌注记 link 到它所属的那一步;"打 120 的四种情况"是整页的 parent 级判断条件
- **Composition**: 一条从上往下的手绘步骤链,在第一节点分出左右两支;左支小伤口、右支大出血;禁忌注记以手绘短线挂在对应步骤外侧;底部一条 120 判断带
- **Title**: 割伤出血:压住、盖上、别揭
- **Core message**: 小伤口先冲洗再覆盖,大出血先打 120 再用手掌直接压住
- **Content**: 分支判断:伤口浅、出血能止住 → 走左边;伤口很深、出血不止或不确定严重程度 → 走右边并立即拨打 120 · 小伤口:洗手 → 用流动清水冲洗伤口,用肥皂清洗周围但别让肥皂进伤口 → 伤口用碘伏、周围用酒精或碘酒,由内向外消毒 → 薄涂抗生素软膏或凡士林保持创面湿润,再用创可贴或纱布覆盖 · 小伤口注记:浅表伤口不要"让它自然风干",愈合需要湿润环境;包扎也不宜过紧,过紧会阻碍血液循环、减慢愈合 · 大出血:打 120 → 有条件先戴一次性手套 → 不拔出大的或深嵌的异物、不探查伤口(明显的表面异物可清除)→ 用无菌纱布或干净布覆盖,用手掌用力按压直到出血停止,可能时把伤处抬高到心脏水平以上 → 先盖后包、力度适中地加压包扎,过松止不住、过紧会造成远端组织缺血坏死 · 大出血注记:血渗透后在原敷料上再加纱布继续按压,不要把原敷料揭下来 · 大出血注记:让伤者躺下并保暖;出现虚弱、皮肤湿冷、脉搏加快等休克征象时抬高双脚并尽量让其保持不动 · 大出血注记:不要按压眼部损伤处与嵌入异物处,怀疑颅骨骨折时不要按压头部伤口 · 止血带:能控制四肢危及生命的大出血,但只在有成品止血带且受过训练时使用,不要用围巾皮带自制;国内口径为连续使用不超过 2 小时、每隔 30 分钟放松 2~3 分钟 · 立即打 120 的四种情况:持续胸痛超过 15 分钟 / 意识模糊或抽搐昏迷 / 严重创伤或出血不止 / 呼吸困难面色青紫
- **Images**: cut_press.jpg 压在大出血支的"直接压迫"节点旁,与该步序号同高
- **Visualization**: 手绘步骤链(qualitative topology),一个分支点加左右两条步骤序列,节点用圆形序号、连接用手绘连线
- **Motion suggestion**: 分支点先出现,再左支四步依次,再右支五步依次;每一步的禁忌注记必须在该步之后出现,不能静态地先摆在那里;止血带说明与 120 判断带最后出现;整条步骤链骨架在 P08 被同构复用,是与下一页之间的 Morph 候选
- **Fact IDs**: F041, F042, F017, F021, F043, F055, F045, F046, F053, F047, F052, F048, F050, F049, F054, F056
- **page_rhythm**: dense

#### Slide 08 - 烫伤:冲 脱 泡 盖 送

- **Audience move**: 想着抹牙膏、抹酱油或者拿冰块敷 → 知道第一件事是常温自来水冲够时间,并记住五步顺序与四条禁忌
- **Relationships**: 五个步骤是严格 order;每步的参数与禁忌 link 到该步;"必须就医"的判断是整页的收束条件
- **Composition**: 与 P07 同构的手绘步骤链,但改为单线五节点;"20 分钟"作为英雄数字压在第一节点旁;四条禁忌集中在链条右侧一条独立的禁止带
- **Title**: 烫伤:冲、脱、泡、盖、送
- **Core message**: 第一步永远是常温自来水冲够 15 分钟以上,越早越好、越久越好
- **Content**: 冲:用 15~25℃ 常温自来水持续冲洗 15~30 分钟,至少 15 分钟,时间越长越好 · 冲的国际口径:英国 NHS 为流动冷水冲 20 分钟并尽量在事发 3 小时内开始;澳新复苏委员会为至少 20 分钟,即使 3 小时内才开始冷却仍可能有帮助 · 脱:冲洗后轻柔脱去衣物;衣物与皮肤粘连时用剪刀剪开周围部分、保留粘连部分,避免二次撕裂创面 · 泡:小面积烫伤可用冷水浸泡 10~20 分钟;大面积烫伤以及老人、儿童禁止长时间浸泡 · 盖:用无菌纱布或干净棉布轻覆创面;待创面冷却后可把保鲜膜平铺覆盖,不要缠绕肢体;不要用创可贴或带黏性的敷料 · 送:烫伤面积大于手掌、皮肤起泡或变色、位于头面部或关节、患者为婴幼儿或老人、伤口渗液有异味、化学或电烧伤,须立即就医 · 禁忌:不要涂牙膏、酱油、醋、香油、草木灰,也不要涂任何乳膏、油类或黄油——会封住热量、造成刺激并加重损伤 · 禁忌:不要直接用冰块或冰水冷却,可能造成进一步组织损伤 · 禁忌:不要强行撕扯粘在烧伤皮肤上的衣物 · 禁忌:不要挑破水疱——水疱有防感染作用;直径小于 1 厘米的小水疱保留,大于 1 厘米的必须由医生处理,严禁自己挑破、撕掉疱皮或挤水 · 提醒:冷却时盖好未烧伤部位给伤者保暖,幼儿尤其容易迅速出现低体温;并在肿胀出现前轻轻摘下戒指、腰带等紧束物品
- **Images**: burn_water.jpg 压在"冲"这一节点旁,与该步序号同高
- **Visualization**: 手绘步骤链(qualitative topology),单线五节点,右侧并挂一条禁止带
- **Motion suggestion**: 承接 P07 的步骤链骨架,链条本身是 Morph 候选(分支双支收拢为单线五节点);本页内语义顺序为五步依次 → 每步参数与注记紧随该步 → 禁止带在五步走完之后整体出现 → 就医判断收束
- **Fact IDs**: F057, F063, F066, F058, F059, F060, F064, F061, F067, F069, F062, F068, F070
- **page_rhythm**: dense

### Part 5: 收进一张表

#### Slide 09 - 一张总表,长按保存

- **Audience move**: 看完八页记不全 → 拿到一张可长按保存的总表,按表去买、去清、去查
- **Relationships**: 表内每行一件物品,行与行同级;分类列把行归入四类加一个"该清出去"组,构成 membership;结尾行动句是全卷的 order 收束
- **Composition**: 页面几乎全部让给表格;表头之上只留一行页标题与一句"按这张去买",表格之下一条行动带与完整出处条
- **Title**: 一张总表,长按保存
- **Core message**: 照着这张表去买、去清、去查,今年就不用再翻九张图
- **Content**: 表格列为 分类 / 物品 / 要点,14 行数据 · 止血包扎:无菌纱布(3×3、4×4 英寸各 5 片)——覆盖创面,渗血再加盖不揭;弹力绷带(3、4 英寸各 1 卷)与三角巾 2 条——先盖后包,力度适中;多尺寸创可贴约 25 片与医用胶带 1 卷——包装完好可存约 5 年,黏性会随时间下降 · 消毒:医用碘伏加无菌棉签——温和不刺激,可直接用于伤口;0.9% 生理盐水——冲洗伤口的首选;消毒湿巾——只清洁伤口周围皮肤,约 2 年 · 常用药:退烧止痛 / 抗过敏 / 肠胃应急 / 外用止痛 / 清凉解暑——对症备用,不盲目囤货;家庭成员专用药——老人心血管急救药、儿童退热药等,遵医嘱 · 工具:医用圆头剪刀与镊子——剪开粘连衣物、取表浅异物;一次性手套与医用外科口罩——施救前防护;电子体温计——非水银非玻璃;急救毯、人工呼吸面膜、手电筒——保暖、通气、夜间取用 · 该清出去:红药水与紫药水——含汞或潜在致癌,清出去;过期或变色变质药——破坏包装后随生活垃圾丢 · 行动带:备对药加懂急救才是双重保障,建议家里至少一人参加一次红十字会或急救中心的培训,学会止血、包扎、心肺复苏
- **Closing impact**: 收束判断(binding)——"备对药 + 懂急救,才是双重保障";构图为 Reference
- **Visualization**: checklist-master —— 分类 / 物品 / 要点 三列、14 行数据的纯文本网格表(`table/record_table`);`Native-ready`: checklist-master=yes
- **Motion suggestion**: 表格先整体出现,行动带在表格之后出现;本页的表格框架与 P02 的四格类目板同源(四类收拢成四个分类段),是全卷首尾呼应的 Morph 候选
- **Fact IDs**: F005, F048, F052, F004, F039, F038, F009, F016, F017, F006, F012, F013, F011, F058, F015, F045, F007, F003, F018, F019, F020, F025, F075, F073, F076
- **page_rhythm**: anchor

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Content**: 每页备注按该页最终 SVG 的可见分组逐块讲解,面向社区急救科普小课的现场讲者;用 instructional 的耐心讲解口吻,先说这一页要解决什么问题,再按页面上的语义顺序讲每一块,并补充页面上放不下的出处细节(发布机构与年份)与口径差异(如国内 3 个月 vs 美国红十字会 1 年、国内 15~30 分钟 vs NHS/ANZCOR 20 分钟);只引用 `sources/first_aid_kit_zh_research.facts.json` 里已有的 fact,不新增外部说法,不给任何剂量建议
- **Total duration**: 约 12–15 分钟(9 页,每页 80–110 秒)
- **Notes style**: conversational(耐心讲解型,面向非医护听众)
- **Presentation purpose**: 先让读者认清"四类齐全"的骨架并照着配齐,再让他清掉不该留的旧药,最后教会割伤与烫伤两条现场处置流程

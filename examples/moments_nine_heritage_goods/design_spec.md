<!-- ppt-master-schema: design-spec/v1 -->
# nine_heritage_goods - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | nine_heritage_goods |
| Canvas Format | Moments/Instagram 1080×1080 |
| Page Count | 11 |
| Primary Language | zh-CN |
| Target Audience | 微信朋友圈里刷到九宫格的普通中文读者，对老物件、上海制造、怀旧题材有兴趣但不了解具体年份与厂家 |
| Communication Intent | 先让每一张单独成立地讲清一件老国货的来历与它当年为什么风靡，再把怀旧收束到“今天还能怎么遇见它”这件可行动的事上；九张连起来还要看得出一条 1935→1972 的时间线 |
| Desired Audience Outcome | 读者看完能说出其中几件的诞生年份与产地，知道哪几件今天仍买得到或看得到，并愿意转发或去找一件 |
| Core Message / Ask / Action | 这九件 1935–1972 年的中国国货不是回忆里的东西，它们大多还在生产、还在货架上、还在博物馆里——今天仍然遇得到 |
| Delivery Context | 主要为微信朋友圈九宫格连发，读者自主浏览、无主讲人、单图停留数秒；次要用途是单张转发与存图 |
| Artifact Afterlife | 单张转发与存图；PPTX 作为可再编辑源文件保留，讲者备注作为每张的朋友圈配文草稿 |
| Reading Mode | balanced |
| Content Strategy | 事实必须严格来自 `sources/nine_heritage_goods_research.facts.json`，查不到的写 NO DATA、不编造；文案措辞可自由重写为海报口吻，年份、产地、厂名、数字与奖项不得改动 |
| Design Style | 方向 A「国营门市」：showcase 叙事 × vintage-poster 视觉，暖土色三主色平涂 + 黑体美术字标题；九件按诞生年份排成一条线，编号徽章逐页承接 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — 最新显式指示未涉及，采用最终 Stage-2 主动值 true；备注在本项目承担“每张的朋友圈配文草稿”这一实际职能 |
| Custom Animations | enabled — 用户显式要求“自定义动画必跑（≥2 对 Morph、入场用 entrance 家族）” |
| Narration Audio | disabled — 最新显式指示未涉及，采用最终 Stage-2 主动值 false |
| Created Date | 2026-09-04 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | Moments/Instagram |
| Dimensions | 1080 × 1080 |
| viewBox | `0 0 1080 1080` |
| Margins | 72 |
| Content Area | 72, 72 – 1008, 1008（936 × 936） |

## III. Visual Theme

### Theme Style

- **Mode**: showcase
- **Visual style**: vintage-poster
- **Theme**: 国营门市部的印刷海报——牛皮纸色纸面、三块暖土色平涂、略微离轴的圆角几何、半调网点当油墨；一件物、一个年份、一枚编号徽章，九张连成一条 1935→1972 的时间线
- **Tone**: 温热、笃定、不煽情；像柜台上贴了三十年的那张纸，褪色但字还很硬

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F4E7CE | 纸面主场，每页的底色 |
| Secondary background | #E3CFA4 | 牛皮纸色的次级大块——地平线带、拱门、叠块的底层 |
| Primary | #B3402F | 主色朱红：大块平涂、题字底板、编号徽章、主要几何体 |
| Accent | #E0952B | 芥黄：太阳盘、射线楔、半调网点着色、关键数字 |
| Secondary accent | #2F6B5E | 松绿：第三块平涂，用于“今天”一栏与对比块 |
| Body text | #2A2420 | 正文与标签的暖近黑油墨 |
| Secondary text | #6B5C4A | 注释、来源、图注 |
| Divider | #C3AC80 | 细分隔线、栏界、边框 |

### AI Image Strategy

- **Image Rendering**: vintage-poster
- **Visual**: 中世纪现代主义海报的减法造型——厚而带手感的轮廓线、圆角有机边、限定三到五块平涂色、网点或纸纹叠在填色上；实物一律画成图形化剪影而非写实，题字为中文美术字，字形本身就是画面
- **Mood**: 温暖、笃定、怀旧而不媚俗——1950–70 年代旅行海报与国营商店门头的气质，接近 Saul Bass 与老上海月份牌之间

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 展示体／厚重黑体，海报美术字的骨架 | SimHei | SimHei | — |
| Body | 中性无衬线，读小字不费劲 | Microsoft YaHei | Microsoft YaHei | — |

- **Title stack**: SimHei
- **Body stack**: Microsoft YaHei
- **Numeral stack**: SimHei
- **Role rationale**: `numeral` 承担每页的诞生年份大数字与封面的“9”，与正文的中性无衬线必须拉开重量，故沿用标题的黑体骨架并单列角色。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 30 |
| Title | 54 |
| Subtitle | 38 |
| Lead | 36 |
| Annotation | 22 |
| Footnote | 18 |
| Numeral | 88 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 先看见一件物与它的名字，再看见年份，最后才读到四行小字；视线从大色块的重心走向标签行
- **Composition tendency**: 每页换一种 vintage-poster 的构图母题（太阳盘／拱门／射线楔／地平线带／徽章封印／取景框／离轴叠块／同心弧），九件不重复；一件物永远压着某条边或某个块缝，不居正中
- **Cross-page continuity**: 编号徽章①–⑨逐页承接并换位；纸面底色、三主色比例、标签行的四个图标语汇全卷不变；每页右下角保留同一枚方形印章
- **Spacing posture**: 由页面节奏决定——dense 页四行标签齐整，breathing 页只留一行与大片纸面
- **Spacing anchors**: 页边距 72、块间距 32、栏间距 40、圆角半径 24、正文行距 46

## VI. Icon Usage Specification

- **Primary bundled library**: chunk-filled

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/chunk-filled/calendar.svg | 诞生年份标签 |
| icons/chunk-filled/factory.svg | 产地与厂家标签 |
| icons/chunk-filled/fire.svg | 当年为什么风靡 |
| icons/chunk-filled/shop.svg | 今天还能怎么遇见它 |
| icons/chunk-filled/trophy.svg | 获奖、纪录、第一次这类荣誉性事实 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| word_cover.png | 1320x327 | 4.04:1 | 封面题字《九件老国货》 | Decorative lettering | 压在太阳盘上缘、占封面上半的显示层，原生标题另置一行 | no-crop | slice | Generated | 切自母表 cover_sheet.png（1x1 单枚） | embedded | local |
| word_huili.png | 601x450 | 1.34:1 | P02 名号题字「回力」 | Decorative lettering | 拱门顶端，原生标题在其下 | no-crop | slice | Generated | 切自母表 letter_sheet.png 第 1 行 1 格 | embedded | local |
| word_yongjiu.png | 600x436 | 1.38:1 | P03 名号题字「永久」 | Decorative lettering | 骑在射线扇的轴线上 | no-crop | slice | Generated | 切自母表 letter_sheet.png 第 1 行 2 格 | embedded | local |
| word_guangming.png | 600x442 | 1.36:1 | P04 名号题字「光明」 | Decorative lettering | 悬在地平线带之上的天空区 | no-crop | slice | Generated | 切自母表 letter_sheet.png 第 1 行 3 格 | embedded | local |
| word_shanghai.png | 640x431 | 1.48:1 | P05 名号题字「上海牌」 | Decorative lettering | 压在圆盘上缘、略微离轴 | no-crop | slice | Generated | 切自母表 letter_sheet.png 第 2 行 1 格 | embedded | local |
| word_dabaitu.png | 640x437 | 1.46:1 | P06 名号题字「大白兔」 | Decorative lettering | 徽章封印内侧的横向字带 | no-crop | slice | Generated | 切自母表 letter_sheet.png 第 2 行 2 格 | embedded | local |
| word_yingxiong.png | 600x432 | 1.39:1 | P07 名号题字「英雄」 | Decorative lettering | 大留白页的左上，独自成立 | no-crop | slice | Generated | 切自母表 letter_sheet.png 第 2 行 3 格 | embedded | local |
| word_haiou.png | 600x429 | 1.40:1 | P08 名号题字「海鸥」 | Decorative lettering | 取景框外的上边缘，跨出框线 | no-crop | slice | Generated | 切自母表 letter_sheet.png 第 3 行 1 格 | embedded | local |
| word_hudie.png | 621x430 | 1.44:1 | P09 名号题字「蝴蝶」 | Decorative lettering | 压在两块离轴叠块的缝上 | no-crop | slice | Generated | 切自母表 letter_sheet.png 第 3 行 2 格 | embedded | local |
| word_hongdeng.png | 600x436 | 1.38:1 | P10 名号题字「红灯」 | Decorative lettering | 同心弧圆心一侧，字面朝向声波 | no-crop | slice | Generated | 切自母表 letter_sheet.png 第 3 行 3 格 | embedded | local |
| good_shoe.png | 1040x718 | 1.45:1 | P02 回力球鞋插画 | Illustration | 斜置在拱门内，鞋头越过拱线 | no-crop | slice | Generated | 切自母表 goods_sheet.png 第 1 行 1 格 | none | local |
| good_bike.png | 1280x806 | 1.59:1 | P03 永久自行车插画 | Illustration | 骑在射线扇的对角线上，前轮压出页边 | no-crop | slice | Generated | 切自母表 goods_sheet.png 第 1 行 2 格 | none | local |
| good_icebrick.png | 554x761 | 0.73:1 | P04 光明冰砖插画 | Illustration | 立在地平线带上，四周大量纸面 | no-crop | slice | Generated | 切自母表 goods_sheet.png 第 1 行 3 格 | none | local |
| good_watch.png | 582x801 | 0.73:1 | P05 上海牌手表插画 | Illustration | 压在巨型圆盘中心偏上，略微离轴 | no-crop | slice | Generated | 切自母表 goods_sheet.png 第 2 行 1 格 | none | local |
| good_candy.png | 680x632 | 1.08:1 | P06 大白兔奶糖插画 | Illustration | 徽章封印中央，另有散粒糖果作节奏 | no-crop | slice | Generated | 切自母表 goods_sheet.png 第 2 行 2 格 | none | local |
| good_pen.png | 1036x1064 | 0.97:1 | P07 英雄100钢笔插画 | Illustration | 沿一条强对角线横贯整页 | no-crop | slice | Generated | 切自母表 goods_sheet.png 第 2 行 3 格 | none | local |
| good_camera.png | 494x842 | 0.59:1 | P08 海鸥双反相机插画 | Illustration | 取景框内居中，镜头对着读者 | no-crop | slice | Generated | 切自母表 goods_sheet.png 第 3 行 1 格 | none | local |
| good_sewing.png | 1040x764 | 1.36:1 | P09 蝴蝶缝纫机插画 | Illustration | 横跨两块离轴叠块的缝 | no-crop | slice | Generated | 切自母表 goods_sheet.png 第 3 行 2 格 | none | local |
| good_radio.png | 840x603 | 1.39:1 | P10 红灯711收音机插画 | Illustration | 同心声波弧的圆心处，弧线自机身发出 | no-crop | slice | Generated | 切自母表 goods_sheet.png 第 3 行 3 格 | none | local |
| deco_sun.png | 522x520 | 1.00:1 | 半调太阳盘装饰件 | Illustration | P04 地平线带之上的天空，低对比 | no-crop | slice | Generated | 切自母表 deco_sheet.png 第 1 行 1 格 | none | local |
| deco_rays.png | 873x877 | 1.00:1 | 射线扇装饰件 | Illustration | P03 自行车背后的印刷射线，压在页角 | no-crop | slice | Generated | 切自母表 deco_sheet.png 第 1 行 2 格 | none | local |
| deco_badge.png | 886x881 | 1.01:1 | 玫瑰花徽章装饰件 | Illustration | P06 奶糖背后的封印底盘 | no-crop | slice | Generated | 切自母表 deco_sheet.png 第 2 行 1 格 | none | local |
| deco_stamp.png | 256x256 | 1.00:1 | 方形印章装饰件（全卷复用的页角落款） | Illustration | P01 与 P11 的页角落款，同一枚重复出现 | no-crop | slice | Generated | 切自母表 deco_sheet.png 第 2 行 2 格 | none | local |

## IX. Content Outline

### Part 1: 开卷

#### Slide 01 - 九件老国货

- **Audience move**: 从“又一条怀旧内容”到“这九件有确切年份和厂名，值得一张张看下去”
- **Relationships**: 九件国货互为并列成员，共同从属“1935–1972 年上海制造”这一时段；来源陈述的年份把它们排成先后
- **Composition**: Reference — 巨型太阳盘占据画面下半做底，射线楔从盘心向上散开；题字压在盘的上缘，原生标题与副标题在题字之下；右下角一枚方形印章
- **Cover impact**: 钩子是“九件都还活着”这一反差——把最早的 1935 与最晚的 1972 当作一条线的两端亮出来；构图为 Reference
- **Title**: 九件老国货
- **Core message**: 1935 到 1972，九件中国国货，今天大多还遇得到
- **Content**:
  - 主题字（图像层）＋原生标题「九件老国货」
  - 副标题：1935–1972 · 九件仍然活着的中国制造
  - 时段两端的年份对照：最早 1935，最晚 1972
  - 一行读法提示：一件一张，九张连成一条线
- **Images**: word_cover.png 作显示层题字；deco_stamp.png 作页角落款
- **Motion suggestion**: 太阳盘是本卷的第一枚承接物，应从封面的巨大尺度过渡到下一页拱门顶端的小圆
- **Fact IDs**: F002, F047

### Part 2: 九件

#### Slide 02 - 回力 1935

- **Audience move**: 从“回力是个运动鞋牌子”到“它是 1935 年注册的上海橡胶厂商标，拿过国家银质奖，今天还在联名”
- **Relationships**: 名号、诞生（年份＋产地厂家）、当年风靡的理由、今天的去处四个单元；来源把诞生→风靡→今天陈述为时间先后，插画与名号指同一件实物
- **Composition**: Reference — 一道巨大的拱门做底占据画面中部，球鞋斜置在拱内、鞋头越过拱线；底部一条地平线带承住四行标签；编号徽章①落在拱肩
- **Title**: 回力
- **Core message**: 一双为奥运球场设计的上海胶鞋，把国家银质奖穿成了日常
- **Content**:
  - 诞生：1935 年 4 月「回力」商标注册（工厂 1927 年在上海创办）
  - 产地：上海 · 正泰橡胶厂（今上海回力鞋业）
  - 当年：1956 年专为奥运中国篮球选手设计 565 长球鞋，1988 年获国家银质奖
  - 今天：仍在生产，与故宫、敦煌博物馆等联名，电商与直播都能买到
- **Images**: word_huili.png 名号题字；good_shoe.png 主体插画
- **Fact IDs**: F001, F002, F003, F005

#### Slide 03 - 永久 1949

- **Audience move**: 从“永久是老自行车”到“1949 年启用的品牌，四十年造了五千万辆，占全国六分之一”
- **Relationships**: 四个单元同上；产量与全国拥有量之间是来源陈述的占比关系
- **Composition**: Reference — 射线楔从左下角向右上散开做印刷背景，自行车骑在这条对角线上、前轮压出页边；诞生年份以大数字压在射线之间；编号徽章②在右上
- **Title**: 永久
- **Core message**: 从上海第一家自行车厂里出来的牌子，撑起了自行车王国的六分之一
- **Content**:
  - 诞生：1949 年底「永久」试制成功并启用（前身 1940 年秋昌和制作所）
  - 产地：上海杨浦 · 昌和制作所 → 上海自行车厂
  - 当年：1949–1990 年累计产约 5000 万辆，约占当时全国自行车社会拥有量的六分之一
  - 今天：由中路股份生产，产品线已扩到电动自行车、童车与轮椅
- **Images**: word_yongjiu.png 名号题字；good_bike.png 主体插画；deco_rays.png 印刷射线
- **Fact IDs**: F006, F007, F008, F009

#### Slide 04 - 光明 1950

- **Audience move**: 从“冰砖是童年味道”到“1950 年的牌子，名字有出处，十七年没涨过价”
- **Relationships**: 四个单元同上；命名缘由与品牌名之间是来源陈述的因果说明
- **Composition**: Reference — 一条地平线带把页面分成天与地，半调太阳盘悬在天空，冰砖立在带上；大片纸面留空，只留一行短句；编号徽章③贴在地平线带右端
- **Title**: 光明
- **Core message**: 名字取自“天亮了”，价格十七年没动过
- **Content**:
  - 诞生：1950 年 5 月「光明」牌冷饮推出
  - 产地：上海 · 益民食品一厂（前身可溯至 1913 年海宁洋行，1953 年 6 月定名）
  - 当年：小中大三种规格分别卖 1 角 9 分、4 角 2 分、7 角，此后十七年未涨价
  - 今天：2018 年因“难买到”重新走红，同年 12 月光明乳业以 1.43 亿元收购益民一厂股权
- **Images**: word_guangming.png 名号题字；good_icebrick.png 主体插画；deco_sun.png 半调太阳盘
- **Fact IDs**: F034, F035, F036, F037, F038

#### Slide 05 - 上海牌 1958

- **Audience move**: 从“上海牌是块老表”到“中国第一家手表厂 1958 年的产物，一块表等于三个月工资”
- **Relationships**: 四个单元同上；售价与月工资之间是来源陈述的对比，「三大件」是它与自行车、缝纫机的并列成员关系
- **Composition**: Reference — 一个巨型圆盘占据画面中心偏上做表盘暗喻，手表压在盘心、略微离轴；四行标签沿盘下方横排；编号徽章④嵌在盘缘
- **Title**: 上海牌
- **Core message**: 中国第一家手表厂的第一批表，上市当天被抢空
- **Content**:
  - 诞生：1958 年 4 月 23 日上海手表厂建成投产，当年产 A581 型 13600 只
  - 产地：上海 · 地方国营上海手表厂
  - 当年：1958 年 7 月 1 日首次上市当天抢购一空；1978 年全钢防震表约 120 元、凭票购买，约合普通职工三个月工资，与自行车、缝纫机并称结婚“三大件”
  - 今天：中华老字号，已开出致敬、复兴等系列，南京西路与蟠龙天地都有新店，全国约 46 家
- **Images**: word_shanghai.png 名号题字；good_watch.png 主体插画
- **Fact IDs**: F015, F016, F017, F018

#### Slide 06 - 大白兔 1959

- **Audience move**: 从“大白兔就是奶糖”到“它是国庆十周年献礼产品，一天只做八百公斤”
- **Relationships**: 四个单元同上；“七粒顶一杯牛奶”是来源陈述的当年流行说法，与走红之间为因果
- **Composition**: Reference — 一枚徽章封印主导画面、几乎占满中部，奶糖压在封印中央，散粒糖果沿半调网点铺出节奏；编号徽章⑤压在封印左下
- **Title**: 大白兔
- **Core message**: 国庆十周年的献礼糖，一天八百公斤，很多工序还靠手
- **Content**:
  - 诞生：1959 年，作为新中国成立十周年献礼产品推出
  - 产地：上海 · 爱民糖果厂（1976 年并入冠生园）
  - 当年：投产初期一条生产线、日产约 800 公斤，多道工序靠手工；“七粒大白兔顶一杯牛奶”的说法流行开来
  - 今天：仍在生产，与气味图书馆做过奶糖味香氛，天猫上线 10 分钟售出超 14000 件
- **Images**: word_dabaitu.png 名号题字；good_candy.png 主体插画；deco_badge.png 封印底盘
- **Fact IDs**: F027, F028, F030

#### Slide 07 - 英雄 1962

- **Audience move**: 从“英雄钢笔很常见”到“它占过国内一半市场，签过中英联合声明”
- **Relationships**: 四个单元同上；“英雄赶派克”的口号与 1962 年定型之间是来源陈述的先后与因果
- **Composition**: Reference — 大留白，钢笔沿一条强对角线横贯整页，题字与一句引语分踞对角两端；四行标签压到底部一栏；编号徽章⑥在右上角单独成立
- **Title**: 英雄
- **Core message**: 一句“英雄赶派克”，赶出了国内一半的钢笔市场
- **Content**:
  - 诞生：1962 年「英雄100」重新设计定型（工厂 1931 年在上海创办）
  - 产地：上海 · 华孚金笔厂 → 上海英雄（集团）
  - 当年：鼎盛期占国内钢笔市场约五成，远销 60 多个国家和地区；1984 年中英联合声明与 2001、2014 年 APEC 的领导人签字用笔都是它
  - 今天：上海英雄仍在运营，2017 年网上销售额约 4000 万元
- **Images**: word_yingxiong.png 名号题字；good_pen.png 主体插画
- **Fact IDs**: F019, F020, F021, F022

#### Slide 08 - 海鸥 1963

- **Audience move**: 从“海鸥是老相机”到“中国第一款出口相机，年产二十万架，停产后又回来了”
- **Relationships**: 四个单元同上；“上海牌→海鸥牌”是同一产品的改名，与出口需要之间为因果
- **Composition**: Reference — 一个取景框做页面主场，四角有对焦刻痕，相机在框内正对读者；题字跨出框的上边线，图注落在框外；编号徽章⑦压在框的右下角
- **Title**: 海鸥
- **Core message**: 中国第一款出口的相机，1980 年一年造二十万架
- **Content**:
  - 诞生：1963 年底 4 型双反相机批量生产（工厂 1958 年 3 月成立）
  - 产地：上海 · 上海照相机厂（1967 年因出口把“上海牌”改为“海鸥牌”，1968 年元旦启用）
  - 当年：中国第一款出口相机；1980 年年产 20 万架，是全国最大照相机专业生产企业，累计产量超 2066 万台
  - 今天：2004 年停产；2011 年海鸥数码成立，2014 年推出 CK20、CF100 等复古数码相机，2020 年转做高精度工业相机
- **Images**: word_haiou.png 名号题字；good_camera.png 主体插画
- **Fact IDs**: F023, F024, F025, F026

#### Slide 09 - 蝴蝶 1966

- **Audience move**: 从“缝纫机是老家具”到“1966 年才叫蝴蝶，一台要四个月工资，还得凭票”
- **Relationships**: 四个单元同上；售价与月工资之间是来源陈述的对比，「三大件」是它与自行车、手表的并列成员关系
- **Composition**: Reference — 三块离轴叠块斜压出层次，缝纫机横跨其中两块的缝，机头压在最上一块之外；四行标签顺着叠块的斜边排；编号徽章⑧钉在最下一块的左下
- **Title**: 蝴蝶
- **Core message**: 1966 年才换上“蝴蝶”这个名字，一台顶普通职工四个月工资
- **Content**:
  - 诞生：1966 年商标由「无敌牌」更名为「蝴蝶牌」（前身 1919 年 1 月协昌铁车铺）
  - 产地：上海 · 协昌铁车铺 → 上海协昌缝纫机厂（1982 年定名）
  - 当年：1972 年第四季度起凭票供应，上海平均约 80 人才配一张券；售价 130–140 元，而普通职工月工资仅 30–40 元，与永久自行车、上海牌手表并称结婚“三大件”
  - 今天：上海蝴蝶进出口仍在做蝴蝶牌家用缝纫机，侧重电商与非洲等海外市场
- **Images**: word_hudie.png 名号题字；good_sewing.png 主体插画
- **Fact IDs**: F043, F044, F045, F046

#### Slide 10 - 红灯 1972

- **Audience move**: 从“红灯收音机眼熟”到“711 型八年造了 186 万台，全国厂家抢着仿，今天在博物馆里”
- **Relationships**: 四个单元同上；收音机与自行车、缝纫机、手表在“三转一响”里互为并列成员
- **Composition**: Reference — 若干同心弧从机身一侧向外扩成声波，收音机压在圆心；大片纸面留白，只留一行短句与四行标签；编号徽章⑨落在最外一道弧上
- **Title**: 红灯
- **Core message**: “三转一响”里的那一响，八年造了一百八十六万台
- **Content**:
  - 诞生：1972 年 6 月 711 型六灯两波段电子管收音机上市
  - 产地：上海 · 上海无线电二厂
  - 当年：1972–1980 年累计约 186 万台，创同期单一型号最高产量纪录，全国厂家纷纷仿制；收音机是“三转一响”里的“一响”
  - 今天：作为展品收藏于上海无线电博物馆，该馆 2017 年 11 月起免费向公众开放
- **Images**: word_hongdeng.png 名号题字；good_radio.png 主体插画
- **Fact IDs**: F047, F048, F049, F050

### Part 3: 落款

#### Slide 11 - 来源

- **Audience move**: 从“这些说法大概是真的”到“每一条都点得开、查得到，查不到的地方它自己说了 NO DATA”
- **Relationships**: 每一条来源与其对应的国货页一一对应；两条 NO DATA 与红灯一页构成缺口说明关系
- **Composition**: Reference — 页面回到最安静的纸面，一组细分隔线把九条来源排成清单；标题与落款印章分踞上下；无插画
- **Closing impact**: 收束的承诺是“可核查”——九条来源可点击，两处查不到的地方明写 NO DATA
- **Title**: 来源与说明
- **Core message**: 九件的年份、厂家与数字都有出处，查不到的地方我们写 NO DATA
- **Content**:
  - 九条按页序排列的来源条目：页码 · 国货名 · 来源标题（整条可点击跳转）
  - NO DATA 说明一：上海无线电二厂的建厂年份未能核实，红灯一页的诞生年份按「711 型 1972 年上市」表述
  - NO DATA 说明二：红灯品牌今天是否仍生产收音机整机未能核实
  - 一行体例说明：年份指品牌／型号的诞生或上市年份，与工厂创办年份不同的地方已在各页标出
- **Images**: deco_stamp.png 页角落款（与封面同一枚）
- **Fact IDs**: F002, F008, F018, F022, F026, F030, F037, F046, F050

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 每页备注写成可直接使用的朋友圈配文草稿：先一句把这件东西拉进读者的生活，再交代年份、产地与当年那条最硬的事实，最后落到今天还能怎么遇见它。数字、年份、厂名一律取自页面上已核实的内容，不得新增页面上没有的事实；不写“这张图显示”“左边是”这类描述画面的话。
- **Total duration**: 全卷约 4 分钟（每页 20–25 秒的朗读量）
- **Notes style**: 口语、短句、克制的怀旧，不煽情不感叹号堆砌
- **Presentation purpose**: 让每一张单独成立地讲清一件老国货，并把怀旧收束到“今天还能怎么遇见它”

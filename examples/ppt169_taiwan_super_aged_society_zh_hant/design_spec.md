<!-- ppt-master-schema: design-spec/v1 -->
# taiwan_super_aged_society_zh_hant - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | 臺灣進入超高齡社會 |
| Canvas Format | ppt169（1280 × 720） |
| Page Count | 15 |
| Primary Language | zh-Hant-TW |
| Target Audience | 參加公開講座的一般民眾：對「人口老化」有生活感受，但不熟悉人口推估、扶養比等統計用語 |
| Communication Intent | 先說清楚「超高齡社會」的定義與臺灣跨過三道門檻的時間差，再用國發會推估解釋背後的機制（出生變少、壽命變長、出生與死亡交叉、年齡結構翻轉），最後把推估連到勞動、照顧與已公布的政策方向 |
| Desired Audience Outcome | 聽眾能說出臺灣在 2025 年底跨過 20%、從 14% 到 20% 只花 7 年；能用出生死亡交叉與金字塔翻轉解釋原因；知道扶養比、勞動力與照顧需求的推估方向與政府已公布的對策架構 |
| Core Message / Ask / Action | 20% 不是終點：臺灣老化得比多數國家快，接下來改變的是出生、工作與照顧的整體結構 |
| Delivery Context | 主講者現場講演為主（約 35 分鐘公開講座、投影）；會後提供簡報檔給聽眾自行閱讀 |
| Artifact Afterlife | 會後分享給聽眾參考；每頁保留來源與年份，收束頁保留可點擊的原始來源 |
| Reading Mode | balanced |
| Content Strategy | 未指定（平衡預設）：依國發會報告重組成講座敘事，所有數字保持出處 |
| Design Style | 刻度與證據：暖白紙面上的深藍資料新聞版式，時間刻度尺為跨頁母題，磚紅只標門檻與老年人口 |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — final Stage-2 proactive policy（委託確認取推薦值） |
| Custom Animations | enabled — final Stage-2 proactive policy（委託確認取推薦值；使用者任務要求自訂動畫） |
| Narration Audio | disabled — workflow default |
| Created Date | 2026-09-11 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 左右 64、上 48、下 40 |
| Content Area | x 64–1216，y 48–680 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: pyramid, instructional
- **Mode Behavior**: 每頁標題就是該頁唯一的主導判斷句，副標一句給出關鍵數字與比較；全卷按「門檻 → 原因 → 結構 → 影響 → 已公布對策」的學習順序推進，先定義再使用術語，並列概念保持同形同深；每個資料頁都寫出來源與推估情境。
- **Visual style**: custom
- **Visual Style References**: data-journalism, editorial
- **Visual Style Behavior**: 暖白紙面上的資料新聞版式：圖表是頁面的脊柱，文字繞著圖表排而不是裝進卡片；以細髮絲線、欄線與一條橫貫的時間刻度尺分區，重點數字用欄寬級的大字，來源列固定在頁尾。磚紅只標門檻、老年人口與關鍵年份，深藍承擔主體與工作年齡，鼠尾草綠承擔出生與幼年；幾乎不用陰影，深度只來自圖片的色調處理與裁切形狀。
- **Theme**: 時間刻度尺（7% → 14% → 20% → 30% …）作為跨頁母題，在門檻頁、國際比較與收束頁以不同尺度重現
- **Tone**: 冷靜、清楚、可查證；像一篇有溫度的資料報導

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F6F3EC | 暖白紙面底色 |
| Secondary background | #ECE6DA | 側欄、表頭、分區底 |
| Primary | #1F3A5F | 標題、主體資料、工作年齡人口、死亡數 |
| Accent | #B5462F | 門檻標記、65 歲以上人口、關鍵年份 |
| Secondary accent | #5E8C6A | 出生數、幼年人口、正向變化 |
| Body text | #1E232B | 內文 |
| Secondary text | #5A6270 | 圖說、註解、來源列 |
| Divider | #D5CCBC | 髮絲線、欄線、表格線 |
| Grid | #E3DCCF | 圖表格線，比分隔線更淡 |
| Surface | #FFFFFF | 表格與圖表面板的輕微抬升 |

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: screen-print
- **Visual**: 絹印海報式的平塗剪影：深藍、磚紅、紙白與少量鼠尾草綠，過渡處加半調網點，人物以輪廓清楚的剪影呈現，不畫五官細節
- **Mood**: 安靜、有尊嚴的日常；像公共圖書館海報上的社區插畫
- **Image Rendering Behavior**: 以 2–4 個平塗色塊構成畫面，形體是乾淨的鏤空剪影、邊緣略帶手工感，無漸層；過渡區用疏密變化的半調網點，整體覆蓋約 12% 的紙張顆粒與輕微套色偏移。題材是臺灣日常街景與人物（長者、孩子、照顧者），以大面積留白與幾何框構圖。圖中不出現任何文字、數字、招牌字樣或標誌。

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 繁中黑體，粗體承擔權威 | Microsoft JhengHei | Segoe UI | sans-serif |
| Body | 繁中黑體，清楚中性 | Microsoft JhengHei | Segoe UI | sans-serif |

- **Title stack**: 'Segoe UI', 'Microsoft JhengHei', sans-serif
- **Body stack**: 'Segoe UI', 'Microsoft JhengHei', sans-serif
- **Role rationale**: 繁中投影講座選用 Windows 內建的微軟正黑體（臺灣字形標準），不用微軟雅黑以免出現大陸字形；全卷同一家族，以字重與字級對比。

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 40 |
| Subtitle | 30 |
| Annotation | 18 |
| Lead | 28 |
| Footnote | 14 |
| Cover title | 72 |
| Hero | 88 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 左上判斷句標題 → 大數字或圖表主體 → 右側或下方的解讀 → 頁尾來源列
- **Composition tendency**: 以不對稱欄位與橫向刻度尺組織頁面；圖表與時間尺佔主要面積，解讀文字貼著資料排；少用等寬卡片
- **Cross-page continuity**: 頁尾來源列與頁碼固定；時間刻度尺、磚紅門檻標記、三色年齡語意（綠幼年／藍工作年齡／紅老年）全卷一致；人口金字塔在相鄰兩頁以同一組長條變形
- **Spacing posture**: 依頁面節奏變化：dense 頁收緊欄距，breathing 頁大留白
- **Spacing anchors**: 頁邊 64、區塊間距 32、欄距 40、圓角 4、內文行距 1.5

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-filled

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/tabler-filled/user.svg |  |
| icons/tabler-filled/man.svg |  |
| icons/tabler-filled/woman.svg |  |
| icons/tabler-filled/baby-carriage.svg |  |
| icons/tabler-filled/briefcase.svg |  |
| icons/tabler-filled/school.svg |  |
| icons/tabler-filled/medical-cross.svg |  |
| icons/tabler-filled/heart.svg |  |
| icons/tabler-filled/home.svg |  |
| icons/tabler-filled/hourglass.svg |  |
| icons/tabler-filled/external-link.svg |  |
| icons/tabler-filled/file-analytics.svg |  |
| icons/tabler-filled/flag.svg |  |
| icons/tabler-filled/bed.svg |  |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P05 | table | metric_table | 比較各國跨越 7%、14%、20% 的年份與所需年數 |
| P07 | chart | line_chart | 1990–2075 年出生數與死亡數的變化與 2020 年交叉 |
| P08 | chart | butterfly_chart | 2026 年分性別五歲組人口金字塔 |
| P09 | chart | butterfly_chart | 2075 年分性別五歲組人口金字塔 |
| P10 | chart | stacked_bar_chart | 2026–2075 年扶幼比與扶老比組成的扶養比 |
| P11 | chart | stacked_bar_chart | 2026、2040、2075 年工作年齡人口的年齡組成占比 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_street.png | 2752×1536 | 16:9 | 封面街景原圖，只供色調派生 | Source | 不直接上頁，僅作為雙色調派生的來源 | adaptive | ai | Generated | 清晨的臺灣騎樓街景：一位拄杖長者坐在騎樓下的長椅，一個背書包的孩子從畫面另一側走過，兩人之間隔著大片留白；畫面左側 40% 保持安靜的牆面與天空，供標題使用；騎樓柱列形成縱向節奏 | none | hero_page |
| cover_street_duotone.jpg | 1600×893 | 16:9 | 封面主視覺：同一條街上兩個世代 | Photography | 滿版底圖，左側安靜區放標題，人物落在右側三分之一 | adaptive | ai | Generated | Derived from cover_street.png; treatment=duotone; 深藍 #1F3A5F 暗部、紙白 #F6F3EC 亮部，讓標題文字在單一明度底上清楚 | none | hero_page |
| hands_generations.jpg | 1024×1024 | 1:1 | 章節轉折頁：少子與長壽兩股力量 | Illustration | 以圓形或拱形裁切的主圖，放在兩個關鍵數字之間 | adaptive | ai | Generated | 一隻布滿皺紋的長者的手輕握一隻嬰兒的小手，特寫，背景為大面積紙白留白，兩隻手位於畫面中央偏下，四周留白足以圓形裁切 | none | local |
| care_home.jpg | 896×1200 | 3:4 | 照顧需求頁：居家照顧的日常場景 | Illustration | 拱形裁切的直幅圖，放在頁面一側，另一側是大數字 | adaptive | ai | Generated | 室內居家場景：一位照顧者蹲在坐輪椅的年長者身旁整理毯子，窗光從左側進來，構圖主體位於中央，上方與兩側留白可做拱形裁切 | none | local |

## IX. Content Outline

### Part 1: 三道門檻

#### Slide 01 - 封面

- **Audience move**: 以為高齡化只是遙遠的統計 → 意識到「每 5 人就有 1 位 65 歲以上」已是現在式
- **Relationships**: 標題、主張句與封面數字為同一主張的層級（parent）
- **Composition**: 滿版雙色調街景，左側安靜區放大標題與 20.06% 主數字，副標一行，右下角放講座資訊與來源
- **Title**: 臺灣進入超高齡社會
- **Core message**: 2025 年底，臺灣 65 歲以上人口占 20.06%，正式跨過超高齡門檻
- **Content**: 主數字 20.06% · 副標「20% 之後，臺灣的人口結構正在重新排列」· 資料依據：國發會《中華民國人口推估（2026 年至 2075 年）》、內政部 2025 年 12 月底戶籍統計
- **Cover impact**: hook＝「每 5 個人，就有 1 位 65 歲以上」與 20.06%；構圖為 Reference
- **Images**: cover_street_duotone.jpg
- **Fact IDs**: F002

#### Slide 02 - 20% 是什麼意思

- **Audience move**: 對「超高齡」只有模糊印象 → 知道它的定義與 2025 年底的實際人數
- **Relationships**: 五個人形為一個整體（membership），其中一位代表 65 歲以上；定義與實際值為對照（contrast）
- **Composition**: 一排五個人形圖示，其中一個以磚紅標出；右側大數字 467 萬人，下方一行定義
- **Title**: 每 5 個人，就有 1 位 65 歲以上
- **Core message**: 65 歲以上人口占總人口 20% 以上稱為超高齡社會；2025 年 12 月底臺灣 65 歲以上人口 467 萬 3,155 人，占 20.06%
- **Content**: 定義：65 歲以上人口占比 7% 高齡化社會／14% 高齡社會／20% 超高齡社會 · 2025 年 12 月底總人口 2,329 萬 9,132 人、65 歲以上 467 萬 3,155 人（20.06%）· 來源：內政部戶籍統計（中央社 2026-01-09 報導）；國發會報告表 21
- **Fact IDs**: F002

#### Slide 03 - 三道門檻的時間差

- **Audience move**: 以為老化是均速發生 → 看見從 14% 到 20% 只用了 7 年，比前一段快三倍多
- **Relationships**: 1993（7%）→ 2018（14%）→ 2025（20%）為時間順序（order）；兩段間隔 25 年與 7 年為對比（contrast）
- **Composition**: 一條橫貫全頁的時間刻度尺，三個門檻標記依年份定位，兩段區間用括號標出 25 年與 7 年；刻度尺右端延伸出畫面，預告下一頁
- **Title**: 從 14% 到 20%，臺灣只用了 7 年
- **Core message**: 臺灣 1993 年跨過 7%、2018 年跨過 14%、2025 年跨過 20%；前一段 25 年，後一段只有 7 年
- **Content**: 1993 年 65 歲以上占比超過 7%（149 萬人）邁入高齡化社會 · 2018 年超過 14%（343 萬人）邁入高齡社會 · 2025 年超過 20%（467 萬人）邁入超高齡社會 · 7%→14% 用 25 年；14%→20% 用 7 年 · 來源：國發會《中華民國人口推估（2026 年至 2075 年）》人口重要年表、表 24-11
- **Motion suggestion**: 三個門檻依時間順序出現，最後出現兩段間隔的年數對比；與下一頁為同一條刻度尺的前後狀態

#### Slide 04 - 下一道門檻

- **Audience move**: 以為 20% 是頂點 → 知道依中推估，30%、40%、50% 的門檻都已排上時間表
- **Relationships**: 延續上一頁的同一刻度尺（order）；過去實際值與未來推估值為對比（contrast）
- **Composition**: 同一條刻度尺向右推移並縮小比例，過去三個門檻壓縮到左側，右側展開 2037、2049、2065 三個推估門檻，推估段以虛線或淡色區分
- **Title**: 下一站：2037 年超過 30%
- **Core message**: 依國發會中推估，65 歲以上占比 2037 年超過 30%、2049 年達 40%、2065 年超過 50%，2075 年為 52.9%
- **Content**: 2037 年 超過 30%（652 萬人）· 2049 年 達 40%（769 萬人，表 19-3）· 2065 年 超過 50%（748 萬人）· 2075 年 52.9% · 65 歲以上人口 2050 年達最高峰 771 萬人 · 標註：2026 年以後為中推估 · 來源：國發會《中華民國人口推估（2026 年至 2075 年）》
- **Motion suggestion**: 刻度尺從上一頁的狀態平移縮放到新比例，未來門檻依序出現

#### Slide 05 - 國際比較

- **Audience move**: 不確定臺灣算快還是慢 → 看到臺灣與韓國從 14% 到 20% 都只用 7 年，是報告所列國家中最快
- **Relationships**: 各國為並列成員（membership）；「7%→14%」與「14%→20%」兩段年數為對比（contrast）
- **Composition**: 一張精簡的比較表占主要面積，臺灣列以磚紅強調；右側一句判讀
- **Title**: 從高齡到超高齡，臺灣與韓國都只用 7 年
- **Core message**: 國發會表 24-11 所列 18 國中，臺灣與韓國 14%→20% 只用 7 年，最快；日本 11 年、德國 36 年、法國 28 年
- **Content**: 表格欄位：國家／7% 年份／14% 年份／20% 年份／7%→14% 年數／14%→20% 年數 · 列：臺灣 1993/2018/2025/25/7；日本 1970/1994/2005/24/11；韓國 2000/2018/2025/18/7；美國 1942/2013/2029*/71/16*；英國 1929/1975/2028*/46/53*；德國 1932/1971/2007/39/36；法國 1864/1990/2018/126/28 · 註：* 為中推估；各國基準日不同 · 來源：國發會報告表 24-11
- **Visualization**: aging-speed-table：table/metric_table，七國比較
- **Native-ready**: aging-speed-table=yes

### Part 2: 為什麼這麼快

#### Slide 06 - 兩股力量

- **Audience move**: 以為老化只是「老人變多」→ 理解是「出生變少」與「壽命變長」同時發生
- **Relationships**: 少子女化與壽命延長為並列原因（link），共同導致高齡化
- **Composition**: 章節轉折頁：中央為圓形裁切的兩代之手，左側總生育率 0.695 人，右側平均壽命 81.3 歲→87.7 歲，上方一句問題
- **Title**: 兩股力量同時作用：出生變少、壽命變長
- **Core message**: 2025 年總生育率降至 0.695 人的歷史低點；零歲平均餘命由 2025 年 81.3 歲，推估 2075 年升至 87.7 歲
- **Content**: 總生育率 2024 年 0.885 人 → 2025 年 0.695 人 · 零歲平均餘命 2025 年 81.3 歲 → 2075 年 87.7 歲（中推估）· 戰後嬰兒潮世代陸續邁入老年 · 來源：國發會《中華民國人口推估（2026 年至 2075 年）》
- **Images**: hands_generations.jpg

#### Slide 07 - 出生與死亡的交叉

- **Audience move**: 不知道人口何時開始減少 → 看見 2020 年死亡數首度超過出生數，之後差距持續拉大
- **Relationships**: 出生數與死亡數兩條時間序列（order）在 2020 年交叉，之後形成缺口（contrast）
- **Composition**: 折線圖占頁面約三分之二寬，交叉點標註 2020；右側解讀欄放 2075 年兩個端點數字
- **Title**: 2020 年起，死亡數超過出生數
- **Core message**: 2020 年死亡 17.3 萬人、出生 16.5 萬人，人口自然增加由正轉負；中推估 2075 年出生僅 2.7 萬人、死亡 30.5 萬人
- **Content**: 出生數（萬人）1990 33.6、1995 33.0、2000 30.5、2005 20.6、2010 16.7、2015 21.4、2020 16.5、2025 10.8、2030 7.9、2035 6.8、2040 6.0、2045 5.7、2050 5.6、2055 5.0、2060 4.1、2065 3.3、2070 2.9、2075 2.7 · 死亡數（萬人）1990 10.6、1995 11.9、2000 12.6、2005 13.9、2010 14.6、2015 16.4、2020 17.3、2025 20.0、2030 21.4、2035 23.7、2040 26.3、2045 28.8、2050 30.6、2055 31.5、2060 31.8、2065 31.7、2070 31.4、2075 30.5 · 死亡數 2061 年達高峰 31.8 萬人 · 註：2025 年以前為實際值（內政部），2026 年以後為中推估 · 來源：國發會報告表 19-2、表 21-2
- **Visualization**: births-deaths-line：chart/line_chart，兩條折線，單位萬人，只在 2020 與 2075 標數據標籤
- **Native-ready**: births-deaths-line=yes

#### Slide 08 - 2026 年的人口金字塔

- **Audience move**: 對「年齡結構」沒有畫面 → 看到 2026 年是中間寬、兩端窄的燈籠型
- **Relationships**: 男、女兩側分性別五歲組人口（contrast），年齡由下而上排列（order）；三個年齡段（0–14、15–64、65 以上）為成員分組（membership）
- **Composition**: 左右對稱的金字塔長條占頁面中央偏左，以三色標示三個年齡段；右側兩行解讀與三段占比
- **Title**: 2026 年：中間寬、兩端窄的「燈籠型」
- **Core message**: 2026 年 45–49 歲是人數最多的年齡組；0–14 歲占 11.1%、15–64 歲占 67.9%、65 歲以上占 20.9%
- **Content**: 分性別五歲組人口（萬人，男/女）：0–4 32.2/30.0；5–9 45.8/42.7；10–14 55.4/51.7；15–19 50.2/46.3；20–24 57.4/52.7；25–29 73.9/68.6；30–34 82.4/77.4；35–39 82.0/77.7；40–44 88.2/89.6；45–49 97.5/101.7；50–54 86.6/92.0；55–59 84.7/90.1；60–64 84.8/91.9；65–69 76.4/85.4；70–74 63.4/74.0；75–79 40.9/50.7；80–84 19.5/27.1；85–89 12.0/19.4；90–94 4.5/8.3；95–99 1.4/2.2；100+ 0.2/0.3 · 三段占比 11.1%／67.9%／20.9% · 來源：國發會人口推估查詢系統開放資料（中推估）
- **Visualization**: pyramid-2026：chart/butterfly_chart，保持 SVG 幾何以便與下一頁 Morph
- **Native-ready**: pyramid-2026=no
- **Fact IDs**: F004
- **Motion suggestion**: 與下一頁為同一組長條的前後狀態，長條寬度變形呈現 2026 → 2075

#### Slide 09 - 2075 年的人口金字塔

- **Audience move**: 以為金字塔只是縮小 → 看到它翻轉成以高齡為主的「倒金鐘型」，而頂部的人今天都已出生
- **Relationships**: 與上一頁同一組分性別年齡長條（order：2026 → 2075）；50 歲以上屬已出生世代、49 歲以下受生育率影響（contrast）
- **Composition**: 同一金字塔長條原地變形為 2075 年形狀，頂部加寬、底部收窄；右側解讀改為 2075 年三段占比與「50 歲以上皆已出生」的說明
- **Title**: 2075 年：翻轉成以高齡為主的「倒金鐘型」
- **Core message**: 中推估 2075 年總人口 1,215 萬人，65 歲以上占 52.9%；75–79 歲成為人數最多的年齡組
- **Content**: 分性別五歲組人口（萬人，男/女）：0–4 9.3/7.6；5–9 10.7/8.6；10–14 12.3/10.0；15–19 14.5/12.2；20–24 16.5/14.1；25–29 17.2/15.4；30–34 17.3/16.3；35–39 18.2/18.1；40–44 20.6/20.9；45–49 23.5/23.8；50–54 35.2/35.5；55–59 45.7/46.2；60–64 50.2/51.8；65–69 44.3/46.9；70–74 49.2/53.9；75–79 57.2/66.7；80–84 51.4/65.9；85–89 36.7/55.7；90–94 23.3/47.3；95–99 9.2/25.0；100+ 2.2/8.3 · 三段占比 4.8%／42.3%／52.9% · 2075 年 50 歲以上的人都已出生，規模不受生育假設影響 · 來源：國發會人口推估查詢系統開放資料（中推估）、國發會報告第參章四
- **Visualization**: pyramid-2075：chart/butterfly_chart，保持 SVG 幾何以便與上一頁 Morph
- **Native-ready**: pyramid-2075=no
- **Fact IDs**: F004

### Part 3: 結構改變了什麼

#### Slide 10 - 扶養比

- **Audience move**: 對「扶養比」這個詞陌生 → 知道 2026 年每 3.2 位青壯年對應 1 位長者，2075 年只剩 0.8 位
- **Relationships**: 扶養比由扶幼比與扶老比組成（parent/membership）；六個年份為時間順序（order）
- **Composition**: 堆疊直條圖占頁面左側約三分之二，扶老比以磚紅、扶幼比以綠色；右側大數字 3.2 → 0.8 與一行定義
- **Title**: 從 3.2 位青壯年扶持 1 位長者，到 0.8 位
- **Core message**: 扶養比由 2026 年 47.2 上升到 2075 年 136.6，2057 年超過 100；上升主要來自扶老比
- **Content**: 扶幼比／扶老比：2026 16.4/30.8（合計 47.2）；2035 10.7/44.5（55.2）；2045 8.9/63.9（72.8）；2055 10.3/86.1（96.4）；2065 11.6/113.3（125.0）；2075 11.4/125.2（136.6）· 潛在支持比 2026 年 3.2 → 2075 年 0.8 · 定義：每 100 位 15–64 歲人口對應的 0–14 歲與 65 歲以上人口數，只反映年齡結構，不代表實際經濟扶養 · 註：中推估；四捨五入致合計可能差 0.1 · 來源：國發會報告表 7
- **Visualization**: dependency-stacked：chart/stacked_bar_chart，六年份直條堆疊
- **Native-ready**: dependency-stacked=yes

#### Slide 11 - 工作年齡人口

- **Audience move**: 以為勞動力只是變少 → 看到它同時變老：45–64 歲在工作年齡人口中的占比從 46.3% 升到 60.8%
- **Relationships**: 工作年齡人口內三個年齡組（membership）在三個年份的組成變化（order）；人數減少與年齡結構變老為並列趨勢（link）
- **Composition**: 三條百分比堆疊橫條（2026／2040／2075）占頁面下半；上方一條人數刻度 1,737 → 1,576 → 1,309 → 513 萬人
- **Title**: 工作年齡人口不只變少，也在變老
- **Core message**: 15–64 歲人口 2015 年達最高峰 1,737 萬人，2026 年 1,576 萬人，中推估 2075 年 513 萬人；其中 45–64 歲占比由 46.3% 升至 60.8%
- **Content**: 人數：2015 年 1,737 萬（最高峰）· 2026 年 1,576 萬 · 2040 年 1,309 萬 · 2075 年 513 萬 · 組成占比（15–24／25–44／45–64）：2026 13.1%/40.6%/46.3%；2040 12.4%/35.7%/51.9%；2075 11.2%/28.1%/60.8% · 註：工作年齡人口指 15–64 歲人口，不等於實際就業人數；2026 年以後為中推估 · 來源：國發會報告表 10、人口重要年表
- **Visualization**: working-age-mix：chart/stacked_bar_chart，百分比堆疊橫條
- **Native-ready**: working-age-mix=yes

#### Slide 12 - 照顧需求

- **Audience move**: 只想到「老人變多」→ 意識到「老人也更老」：85 歲以上人口將增加到 4 倍多
- **Relationships**: 85 歲以上人口是 65 歲以上人口的子集（parent）；2026 → 2039 → 2075 為時間順序（order）
- **Composition**: 左側拱形裁切的照顧場景插畫，右側大數字 48 萬 → 208 萬，下方三個里程碑
- **Title**: 長者不只變多，也更高齡
- **Core message**: 85 歲以上人口 2026 年 48 萬人（占老年人口 10.0%），2039 年超過 100 萬人，中推估 2075 年 208 萬人（32.3%）
- **Content**: 2026 年 48 萬人，每 10 位長者中 1 位 85 歲以上 · 2039 年超過 100 萬人，每 6.5 位長者中 1 位 · 2075 年 208 萬人，約每 10 位長者中 3 位 · 報告指出「老老照顧」漸成常態，失能、失智等專業照護需求相應擴張 · 來源：國發會報告第參章六、表 8、人口重要年表
- **Images**: care_home.jpg

### Part 4: 已公布的方向與收束

#### Slide 13 - 政府已公布的對策架構

- **Audience move**: 不知道政府有沒有動作 → 知道已成立跨部會小組、推出家庭支持篇，另有三篇規劃中
- **Relationships**: 「人口對策新戰略」為上位架構（parent），家庭支持篇（已推出）與銀髮世代篇、全齡育才篇、全球攬才篇（規劃中）為成員（membership）；已推出與規劃中為對比（contrast）
- **Composition**: 上方一條架構標題帶，下方四個篇章並列，家庭支持篇實心、其餘三篇以淡色或虛線表示規劃中；家庭支持篇展開五個措施類別
- **Title**: 已推出家庭支持篇，另有三篇規劃中
- **Core message**: 行政院成立「人口對策新戰略執行小組」，2026 年 5 月推出「台灣人口對策新戰略—家庭支持篇」共 18 項措施，並規劃銀髮世代篇、全齡育才篇、全球攬才篇
- **Content**: 家庭支持篇（2026 年 5 月）：安心生養 · 強化托育 · 教育加碼 · 友善職場 · 居住減壓，共 18 項措施 · 規劃中：銀髮世代篇 · 全齡育才篇 · 全球攬才篇 · 來源：國發會新聞稿（2026 年 8 月 28 日）

#### Slide 14 - 對一般人意味著什麼（整理）

- **Audience move**: 覺得數字離自己很遠 → 能把推估對應到家庭、職場、學校與公共服務四個生活場景
- **Relationships**: 四個生活場景為並列成員（membership），每個場景連到一項推估事實（link）
- **Composition**: 四欄並列，每欄一個圖示、一個場景名、一個推估數字與一行報告中的課題；頁首標示「整理」
- **Title**: 推估落到生活裡的四個場景
- **Core message**: 整理自國發會報告：家裡長輩更高齡、職場同事更年長、學校生源減少、公共資源向高齡傾斜
- **Content**: 家庭：2075 年約每 10 位長者中 3 位 85 歲以上 · 職場：2075 年工作年齡人口約 6 成為 45–64 歲 · 學校：6 歲入學年齡人口 2026 學年度 17 萬人，2040 學年度降為 7–8 萬人 · 公共服務：扶養比 2057 年超過 100，照護資源逐步向高齡傾斜 · 標示：整理自國發會報告「相關課題」，非個人建議

#### Slide 15 - 收束

- **Audience move**: 帶著零散數字 → 帶走一句結論與可以自行查證的來源
- **Relationships**: 結論句為上位（parent），四個來源連結為成員（membership）
- **Composition**: 左側大字結論與刻度尺母題的最後一次出現（標出現在位置 20%），右側來源清單，每條為可點擊連結
- **Title**: 20% 不是終點，是結構改變的起點
- **Core message**: 臺灣老化速度快於多數國家；接下來的變化在出生、工作與照顧的整體結構
- **Content**: 結論句 · 來源連結：國發會人口推估查詢系統 https://pop-proj.ndc.gov.tw/ · 《中華民國人口推估（2026 年至 2075 年）》報告 PDF https://ppws.ndc.gov.tw/Download.ashx?u=LzAwMS9VcGxvYWQvNDY0L3JlbGZpbGUvMTAzNDcvMTY4L2VjN2NmNjg1LWJlZjYtNGQwNS05YmVkLWQzNWFlMDA2ZThjZi5wZGY%3d&n=5Lit6I%2bv5rCR5ZyL5Lq65Y%2bj5o6o5LywKDIwMjblubToh7MyMDc15bm0KeWgseWRii5wZGY%3d&icon=.pdf · 國發會新聞稿 PDF https://ppws.ndc.gov.tw/Download.ashx?u=LzAwMS9VcGxvYWQvNDY0L3JlbGZpbGUvMTAzNDcvMTcwLzBiYTliOTJlLTViM2UtNDE1OC1iZDZiLWQ3NTE4NWJmZGMxZi5wZGY%3d&n=5Lit6I%2bv5rCR5ZyL5Lq65Y%2bj5o6o5LywKDIwMjblubToh7MyMDc15bm0KeaWsOiBnueovy5wZGY%3d&icon=.pdf · 中央社報導內政部 2025 年底戶籍統計 https://www.cna.com.tw/news/ahel/202601090067.aspx
- **Closing impact**: takeaway＝「20% 不是終點，是結構改變的起點」；構圖為 Reference
- **Fact IDs**: F001, F002

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 以繁體中文（臺灣用語）寫講稿，每頁先講結論再補數字；只使用 sources/ 內國發會報告、新聞稿、開放資料與內政部統計報導的數字，推估值口頭說明為「中推估」；不提供個人理財或生活建議
- **Total duration**: 約 35 分鐘
- **Notes style**: 口語、平實、面向一般民眾的公開講座
- **Presentation purpose**: 說明超高齡社會的定義與臺灣的時間差，解釋背後機制，並把推估連到勞動、照顧與已公布的政策方向

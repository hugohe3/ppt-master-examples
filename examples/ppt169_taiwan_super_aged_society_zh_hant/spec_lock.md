<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: zh-Hant-TW
- audience: 參加公開講座的一般民眾，對人口老化有生活感受但不熟悉人口推估與扶養比等統計用語
- objective: 說清楚超高齡社會的定義與臺灣跨過三道門檻的時間差，用國發會推估解釋出生、壽命與年齡結構的機制，再連到勞動、照顧與已公布的政策方向，讓聽眾能說出 2025 年底跨過 20%、14% 到 20% 只花 7 年，並理解之後的結構變化
- core_message: 20% 不是終點：臺灣老化得比多數國家快，接下來改變的是出生、工作與照顧的整體結構
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: pyramid, instructional
- mode_behavior: 每頁標題就是該頁唯一的主導判斷句，副標一句給出關鍵數字與比較；全卷按「門檻 → 原因 → 結構 → 影響 → 已公布對策」的學習順序推進，先定義再使用術語，並列概念保持同形同深；每個資料頁都寫出來源與推估情境。

## visual_style
- visual_style: custom
- visual_style_references: data-journalism, editorial
- visual_style_behavior: 暖白紙面上的資料新聞版式：圖表是頁面的脊柱，文字繞著圖表排而不是裝進卡片；以細髮絲線、欄線與一條橫貫的時間刻度尺分區，重點數字用欄寬級的大字，來源列固定在頁尾。磚紅只標門檻、老年人口與關鍵年份，深藍承擔主體與工作年齡，鼠尾草綠承擔出生與幼年；幾乎不用陰影，深度只來自圖片的色調處理與裁切形狀。

## colors
- background: #F6F3EC
- secondary_bg: #ECE6DA
- primary: #1F3A5F
- accent: #B5462F
- secondary_accent: #5E8C6A
- body_text: #1E232B
- secondary_text: #5A6270
- divider: #D5CCBC
- grid: #E3DCCF
- surface: #FFFFFF
- image_rendering: custom
- image_rendering_references: screen-print
- image_rendering_behavior: 以 2–4 個平塗色塊構成畫面，形體是乾淨的鏤空剪影、邊緣略帶手工感，無漸層；過渡區用疏密變化的半調網點，整體覆蓋約 12% 的紙張顆粒與輕微套色偏移。題材是臺灣日常街景與人物（長者、孩子、照顧者），以大面積留白與幾何框構圖。圖中不出現任何文字、數字、招牌字樣或標誌。

## typography
- font_family: 'Segoe UI', 'Microsoft JhengHei', sans-serif
- title_family: 'Segoe UI', 'Microsoft JhengHei', sans-serif
- body_family: 'Segoe UI', 'Microsoft JhengHei', sans-serif
- body: 24
- title: 40
- subtitle: 30
- annotation: 18
- lead: 28
- footnote: 14
- cover_title: 72
- hero: 88

## icons
- library: tabler-filled
- inventory: tabler-filled/user, tabler-filled/man, tabler-filled/woman, tabler-filled/baby-carriage, tabler-filled/briefcase, tabler-filled/school, tabler-filled/medical-cross, tabler-filled/heart, tabler-filled/home, tabler-filled/hourglass, tabler-filled/external-link, tabler-filled/file-analytics, tabler-filled/flag, tabler-filled/bed

## images
- cover: images/cover_street_duotone.jpg | source=ai | crop=adaptive
- hands: images/hands_generations.jpg | source=ai | crop=adaptive
- care: images/care_home.jpg | source=ai | crop=adaptive

## page_rhythm
- P01: anchor
- P02: breathing
- P03: dense
- P04: dense
- P05: dense
- P06: anchor
- P07: dense
- P08: dense
- P09: dense
- P10: dense
- P11: dense
- P12: breathing
- P13: dense
- P14: dense
- P15: anchor

## page_visualizations
- P05: table/metric_table
- P07: chart/line_chart
- P08: chart/butterfly_chart
- P09: chart/butterfly_chart
- P10: chart/stacked_bar_chart
- P11: chart/stacked_bar_chart

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters

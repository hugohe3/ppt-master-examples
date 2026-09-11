<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: ko-KR
- audience: 제주 해녀에 관심 있는 일반 시민(공개 강연 청중)
- objective: 물질의 조직과 유산 지정의 이유를 설명하고 인원·연령 변화로 전승 과제를 드러내, 청중이 상군·중군·하군·불턱·어촌계와 두 국제 유산의 이유를 설명하고 1970년 14,143명 → 2025년 2,371명, 60세 이상 4.6% → 90.1%의 의미를 이해하게 한다
- core_message: 제주 해녀는 '숨'이라는 개인 기량을 공동체의 규칙으로 묶어 바다밭을 함께 가꾸어 온 체계이며, 그 체계를 이어 갈 사람이 빠르게 줄고 있다
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: narrative
- mode_behavior: 상황(물질의 모습) → 구조(무리·기량·불턱·바다밭) → 평가(여섯 번의 지정과 이유) → 긴장(인원·연령 변화, 유입과 감소) → 실마리(전승 장치) → 정리로 흐르는 서사; 모든 제목은 판단 문장, 한 쪽 한 주장; 수치 쪽은 출처와 연도를 쪽 아래에, 자체 틀은 「정리」로 표시한다.

## visual_style
- visual_style: custom
- visual_style_references: editorial
- visual_style_behavior: 소금기 종이색 바탕의 잡지형 편집 — 가는 수평 규칙선, 비대칭 2단, 세리프 제목 × 산세리프 본문, 킥커와 쪽 아래 출처 줄; 교차 모티프 '수면선'(수평 헤어라인)과 수심이 의미를 가질 때만 붙는 0·5·10m 눈금; 이미지는 실크스크린 판화 평면 블록으로 원형·아치 창이나 넓은 띠로 잘림; 데이터 쪽은 넓은 여백과 강조 숫자 하나; 그림자 없음; 표지·장 전환·마무리는 짙은 바다색 전면 면으로 반전.

## colors
- background: #F4F1EA
- secondary_bg: #E3ECEB
- primary: #123B4A
- accent: #E0662B
- secondary_accent: #3F8C8A
- body_text: #1E2A30
- secondary_text: #5B6970
- divider: #C9CFCC
- image_rendering: custom
- image_rendering_references: screen-print
- image_rendering_behavior: 실크스크린 포스터 판화 — 덱 색 역할 안의 3~4색 평면 블록, 물의 명암 전환부 하프톤 점, 1~2px 판 어긋남, 종이결 15%, 스텐실 실루엣 인물(얼굴 세부 없음), 그림 안 글자 없음.

## typography
- font_family: 'Segoe UI', 'Malgun Gothic', sans-serif
- title_family: 'Cambria', 'Batang', serif
- body_family: 'Segoe UI', 'Malgun Gothic', sans-serif
- body: 24
- title: 40
- subtitle: 30
- annotation: 18
- lead: 28
- footnote: 14
- cover_title: 96
- display: 96

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/ripple, tabler-outline/fish, tabler-outline/swimming, tabler-outline/lungs, tabler-outline/clock, tabler-outline/calendar, tabler-outline/users-group, tabler-outline/flame, tabler-outline/school, tabler-outline/currency-won, tabler-outline/certificate, tabler-outline/world, tabler-outline/map-pin, tabler-outline/external-link, tabler-outline/ruler-measure, tabler-outline/heart-handshake, tabler-outline/basket, tabler-outline/book, tabler-outline/hourglass, tabler-outline/user-plus, tabler-outline/user-minus, tabler-outline/trending-down, tabler-outline/plant

## images
- cover: images/cover_surface.jpg | source=ai | crop=adaptive
- cover_dim: images/cover_surface_dim.jpg | source=ai | crop=adaptive
- dive: images/dive_column.jpg | source=ai | crop=adaptive
- bulteok: images/bulteok_ring_duo.jpg | source=ai | crop=adaptive
- sea_field: images/sea_field.jpg | source=ai | crop=adaptive
- two_divers: images/two_divers.jpg | source=ai | crop=adaptive

## page_visualizations
- P08: table/record_table
- P10: chart/column_chart
- P11: chart/stacked_bar_chart
- P12: chart/column_chart

## page_rhythm
- P01: anchor
- P02: anchor
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: breathing
- P08: dense
- P09: dense
- P10: dense
- P11: dense
- P12: dense
- P13: dense
- P14: breathing
- P15: anchor

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters

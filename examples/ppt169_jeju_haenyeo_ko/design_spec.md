<!-- ppt-master-schema: design-spec/v1 -->
# 제주 해녀 - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | jeju_haenyeo_ko_20260911 |
| Canvas Format | ppt169 (PPT 16:9, 1280×720) |
| Page Count | 15 |
| Primary Language | ko-KR |
| Target Audience | 제주 해녀에 관심 있는 일반 시민(공개 강연 청중). "해녀=제주의 잠수하는 여성" 정도의 사전 지식을 가진 사람들 |
| Communication Intent | 먼저 물질이 어떤 방식과 규칙으로 조직되는지 설명하고, 그 공동체 방식이 왜 유네스코·FAO 유산으로 평가받았는지 보여 준 뒤, 해녀 수와 연령 구성의 변화로 전승 위기를 드러내고 무엇이 전승을 가능하게 하는지 생각하게 한다 |
| Desired Audience Outcome | 청중이 물질의 조직(상군·중군·하군, 불턱, 어촌계)과 두 국제 유산 지정의 이유를 자기 말로 설명할 수 있고, 1970년 14,143명 → 2025년 2,371명, 60세 이상 4.6% → 90.1%라는 변화가 무엇을 뜻하는지 이해한다 |
| Core Message / Ask / Action | 제주 해녀는 '숨'이라는 개인 기량을 공동체의 규칙으로 묶어 바다밭을 함께 가꾸어 온 체계이며, 그 체계를 이어 갈 사람이 빠르게 줄고 있다 |
| Delivery Context | 주: 발표자가 진행하는 일반 시민 대상 공개 강연(약 35분). 부: 강연 후 청중이 다시 열어 보는 공유 자료 |
| Artifact Afterlife | 강연 후 배포·열람. 수치마다 출처와 연도를 쪽에 남기고, 마지막 쪽에서 주요 출처로 바로 이동할 수 있게 한다 |
| Reading Mode | balanced |
| Content Strategy | 지정 없음 — 균형(balanced) 기본값: 조사 자료의 사실을 모두 유지하되 서사 순서로 재구성; 자체 틀은 「정리」로 표시 |
| Design Style | 방향 A「수심의 기록」 — custom mode(narrative 기반) + custom visual style(editorial 기반) + custom 이미지 렌더링(screen-print 기반) |
| AI Image Acquisition Path | auto (위임 확인에서 추천값 채택; Path A `image_gen.py --manifest` 우선) |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — final Stage-2 proactive policy (위임 확인, 추천값 true) |
| Custom Animations | enabled — final Stage-2 proactive policy (위임 확인, 추천값 true: 인접 쪽 Morph 두 쌍과 주인공 요소 입장이 순서를 설명함) |
| Narration Audio | disabled — workflow default |
| Created Date | 2026-09-11 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 좌우 64, 위 56, 아래 48 |
| Content Area | x 64–1216, y 56–672 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: narrative
- **Mode Behavior**: 상황(물질의 모습) → 구조(무리·기량·불턱·바다밭) → 평가(여섯 번의 지정과 그 이유) → 긴장(인원과 연령 구성의 변화, 들어오는 사람과 떠나는 사람) → 실마리(전승 장치) → 정리로 흐르는 서사. 모든 쪽 제목은 판단 문장이고 한 쪽에 한 주장만 세운다. 수치 쪽은 출처와 연도를 쪽 아래에 적고, 조사 자료에 없는 자체 틀은 「정리」로 표시한다.
- **Visual style**: custom
- **Visual Style References**: editorial
- **Visual Style Behavior**: 소금기 밴 종이색 바탕 위의 잡지형 편집. 가는 수평 규칙선과 비대칭 2단, 세리프 제목 × 산세리프 본문, 제목 위 킥커와 쪽 아래 출처 줄이 위계를 만든다. 교차 모티프는 '수면선' — 쪽마다 한 줄의 수평선이 수면 역할을 하고, 수심이 의미를 가질 때만 0·5·10m 눈금이 붙는다. 이미지는 실크스크린 판화처럼 평면 색 블록으로 들어와 원형·아치 창이나 넓은 띠로 잘리고, 데이터 쪽은 장식 없이 넓은 여백과 강조 숫자 하나로 선다. 그림자는 쓰지 않고, 표지·장 전환·마무리는 짙은 바다색 전면 면으로 반전한다.
- **Theme**: 수심의 기록 — 바다의 단면, 판화 같은 해녀 이미지, 신문 지면 같은 사실 기록
- **Tone**: 담담하고 단단함. 감상보다 사실이 먼저 말하고, 사람의 무게는 이미지와 숫자 하나가 짊어진다

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #F4F1EA | 소금기 종이색 본문 바탕 |
| Secondary background | #E3ECEB | 옅은 물빛 면, 표·보조 영역 |
| Primary | #123B4A | 짙은 바다색: 제목, 반전 면, 차트 주 계열 |
| Accent | #E0662B | 테왁 주황: 강조 숫자 하나, 킥커 규칙선, 핵심 막대 |
| Secondary accent | #3F8C8A | 옥빛 물: 보조 계열, 수심 눈금, 아이콘 |
| Body text | #1E2A30 | 본문 |
| Secondary text | #5B6970 | 캡션, 출처 줄, 주석 |
| Divider | #C9CFCC | 규칙선, 표 테두리, 헤어라인 |

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: screen-print
- **Image Rendering Behavior**: 실크스크린 포스터 판화. 덱 색 역할(짙은 바다·옥빛 물·테왁 주황·소금 종이) 안에서 3~4색 평면 블록만 쓰고, 물의 명암이 바뀌는 곳에 하프톤 점을 두며, 판이 1~2px 어긋난 흔적과 종이결 15%를 남긴다. 인물은 스텐실로 오린 실루엣으로만 그려 얼굴 세부가 없고, 그림 안에 글자는 없다.
- **Visual**: 스텐실 실루엣 해녀 + 평면 색 블록 바다 + 하프톤 물빛
- **Mood**: 담담하고 단단한 1960년대 문화 포스터 — 해양 박물관 기획전 포스터를 떠올리게 하는 분위기

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 한글 명조 계열 세리프, 기록물 같은 무게 | Batang | Cambria | serif |
| Body | 중립 한글 고딕, 투사 가독성 | Malgun Gothic | Segoe UI | sans-serif |

- **Title stack**: 'Cambria', 'Batang', serif
- **Body stack**: 'Segoe UI', 'Malgun Gothic', sans-serif
- **Role rationale**: 표지 제목(cover_title)·강조 숫자(display)·리드(lead)·출처 줄(footnote)은 크기만 다른 반복 역할이며 가족은 Title/Body를 따른다.

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 40 |
| Subtitle | 30 |
| Annotation | 18 |
| Lead | 28 |
| Footnote | 14 |
| Cover title | 96 |
| Display | 96 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 킥커 → 판단 문장 제목 → 리드 한 줄 → 증거(이미지·차트·표) → 쪽 아래 출처 줄
- **Composition tendency**: 비대칭 2단(좁은 글 단 + 넓은 증거 단)과 전면 반전 면의 교대; 한 쪽에 초점 하나
- **Cross-page continuity**: 수면선 모티프(수평 헤어라인)가 모든 본문 쪽에 있고, 물질 쪽에서만 수심 눈금이 붙는다. 킥커는 장 번호 + 장 이름. 출처 줄 형식은 「출처: 기관명, 자료명(연도)」로 고정
- **Spacing posture**: 쪽 리듬에 따라 가변 — dense 쪽은 2단 정보 밀도, breathing 쪽은 넓은 여백
- **Spacing anchors**: 쪽 여백 64 · 블록 간격 32 · 단 사이 40 · 모서리 반경 0 · 본문 행간 36

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/tabler-outline/ripple.svg | |
| icons/tabler-outline/fish.svg | |
| icons/tabler-outline/swimming.svg | |
| icons/tabler-outline/lungs.svg | |
| icons/tabler-outline/clock.svg | |
| icons/tabler-outline/calendar.svg | |
| icons/tabler-outline/users-group.svg | |
| icons/tabler-outline/flame.svg | |
| icons/tabler-outline/school.svg | |
| icons/tabler-outline/currency-won.svg | |
| icons/tabler-outline/certificate.svg | |
| icons/tabler-outline/world.svg | |
| icons/tabler-outline/map-pin.svg | |
| icons/tabler-outline/external-link.svg | |
| icons/tabler-outline/ruler-measure.svg | |
| icons/tabler-outline/heart-handshake.svg | |
| icons/tabler-outline/basket.svg | |
| icons/tabler-outline/book.svg | |
| icons/tabler-outline/hourglass.svg | |
| icons/tabler-outline/user-plus.svg | |
| icons/tabler-outline/user-minus.svg | |
| icons/tabler-outline/trending-down.svg | |
| icons/tabler-outline/plant.svg | |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P08 | table | record_table | 여섯 번의 유산 지정을 연도·대상·지정·범위 레코드로 나열 |
| P10 | chart | column_chart | 1970~2025년 현직 해녀 수의 감소를 연도별 막대로 비교 |
| P11 | chart | stacked_bar_chart | 1970년과 2025년의 연령 구성 비율(%)을 두 막대로 대비 |
| P12 | chart | column_chart | 2015~2022년 신규 해녀 어촌계 가입 인원을 연도별로 제시 |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_surface.jpg | 2752×1536 | 16:9 | 표지 훅: 막 떠오른 해녀와 주황 테왁 | Illustration | 전면 배경; 왼쪽 빈 수면 위에 제목, 제목 쪽에 그라데이션 스크림 | adaptive | ai | Generated | 수면 높이에서 본 넓은 바다. 오른쪽 1/3에 주황 테왁을 붙잡고 막 떠오른 해녀 한 명(뒷모습 실루엣, 얼굴 식별 불가). 왼쪽 60%는 잔잔한 수면과 하늘만 있는 조용한 영역 | none | hero_page |
| cover_surface_dim.jpg | 2752×1536 | 16:9 | 마무리 쪽의 표지 회상 띠 | Illustration | 쪽 한쪽의 좁은 세로 띠로 표지 장면을 다시 부름 | adaptive | ai | Generated | Derived from cover_surface.jpg; treatment=grayscale+brightness; | none | local |
| dive_column.jpg | 1792×2400 | 3:4 | 물질의 수직 단면: 수면에서 바닥까지 | Illustration | 오른쪽 세로 창(윗단 아치), 수심 눈금과 겹쳐 수심을 읽게 함; 다음 쪽에서 같은 장면이 이동(Morph) | adaptive | ai | Generated | 수면(상단 12%)부터 현무암 바닥(하단 15%)까지 한 화면의 수직 수중 단면. 머리를 아래로 두고 내려가는 해녀 한 명(실루엣), 위에서 내려오는 빛줄기, 바닥의 전복·소라·미역, 수면에 뜬 주황 테왁 | none | local |
| bulteok_ring.png | 2048×2048 | 1:1 | 불턱 원본 | Source | 원본은 쪽에 놓지 않고 파생본만 사용 | adaptive | ai | Generated | 위에서 내려다본 둥근 현무암 돌담 불턱. 가운데 작은 모닥불, 둘러앉은 해녀 네다섯 명(정수리와 어깨만, 얼굴 없음), 둘레의 검은 바위 해안 | none | local |
| bulteok_ring_duo.jpg | 2048×2048 | 1:1 | 불턱: 공동체 공간 | Illustration | 원형 창으로 잘라 둘레에 기능 세 가지를 배치 | adaptive | ai | Generated | Derived from bulteok_ring.png; treatment=duotone; | none | local |
| sea_field.jpg | 2752×1536 | 16:9 | 바다밭: 함께 가꾸는 공유지 | Illustration | 쪽 아래 절반을 채우는 넓은 해저 띠, 위쪽 조용한 물빛 위에 글 | adaptive | ai | Generated | 사람이 없는 얕은 해저 바다밭. 현무암 바위, 미역·감태 숲, 전복·소라·성게. 위쪽 40%는 물빛만 있는 조용한 영역 | none | local |
| two_divers.jpg | 2752×1536 | 16:9 | 전승: 나이 든 해녀와 젊은 해녀 | Illustration | 쪽 왼쪽 절반을 채우는 편집 크롭, 오른쪽에 글 단 | adaptive | ai | Generated | 현무암 해안에서 바다로 걸어 들어가는 두 해녀의 뒷모습. 한 명은 등이 굽은 노년, 한 명은 곧은 자세의 젊은 해녀, 둘 다 테왁을 듦. 얼굴은 보이지 않음 | none | local |

## IX. Content Outline

### Part 1: 여는 질문

#### Slide 01 - 표지

- **Audience move**: 해녀를 '관광 사진 속 풍경'으로 알던 청중 → 맨몸과 숨으로 일하는 직업인의 이야기가 시작된다고 느낌
- **Relationships**: none
- **Cover impact**: 훅 — "산소통 없이, 숨 한 번에 1~2분" (binding). 구성 Reference: 전면 판화 바다 위, 왼쪽 빈 수면에 제목
- **Title**: 제주 해녀
- **Core message**: 숨 하나로 바다를 가꾸어 온 공동체
- **Content**: 부제 — 숨 하나로 바다를 가꾸어 온 공동체 · 훅 — 산소통 없이, 숨 한 번에 1~2분 · 표기 — 일반 시민 공개 강연 · 2026
- **Images**: cover_surface.jpg
- **Fact IDs**: F009, F010

#### Slide 02 - 세 가지 질문

- **Audience move**: 막연한 호기심 → 강연이 답할 세 질문과 순서를 앎
- **Relationships**: order — 질문 1(조직) → 질문 2(유산의 이유) → 질문 3(전승)
- **Composition**: 세 질문이 수면선 아래로 차례로 내려가는 수심 순서; 자체 틀이므로 「정리」 표시
- **Title**: 오늘은 세 가지 질문을 따라갑니다
- **Core message**: 물질의 조직 → 유산의 이유 → 전승의 과제
- **Content**: 1 물질은 어떻게 조직되는가 · 2 왜 인류의 유산이 되었나 · 3 누가 이 바다를 잇는가 · 표시 — 정리: 강연 구성

### Part 2: 물질은 어떻게 조직되는가

#### Slide 03 - 물질의 정의

- **Audience move**: '잠수'라는 막연한 인상 → 장비 없는 맨몸·호흡 조절·수심 10m 이내·1~2분이라는 구체적 조건을 앎
- **Relationships**: order — 수면 → 잠수(1~2분) → 수면 위 숨비소리
- **Composition**: 왼쪽 글 단, 오른쪽 세로 창의 수중 단면과 0·5·10m 수심 눈금
- **Title**: 물질은 장비 없이 맨몸과 숨만으로 하는 일이다
- **Core message**: 기계 장치 없이 호흡 조절로 바다에 들어가 해산물을 채취하는 직업
- **Content**: 정의 문장(해녀박물관) · 수심 10m 이내 연안 어장 · 한 번 잠수 약 1~2분 · 숨비소리 — 떠올라 '호오이' 하고 몸속 이산화탄소를 내뿜는 소리 · 출처 줄
- **Images**: dive_column.jpg
- **Motion suggestion**: 다음 쪽과 같은 수중 장면을 유지한 채 시점만 옮겨 '한 번의 잠수'에서 '하루의 작업'으로 넘어감 (P03 → P04 연속 상태)
- **Fact IDs**: F009, F010, F016

#### Slide 04 - 하루의 물질

- **Audience move**: 한 번의 잠수 → 하루·한 해 단위의 노동과 무리 작업을 앎
- **Relationships**: membership — 시간(하루 최대 7시간·연 90일), 무리(보통 15명 정도), 도구(빗창·테왁·망시리)가 한 작업 체계에 속함
- **Composition**: 앞 쪽의 수중 장면이 왼쪽으로 옮겨 가고, 오른쪽에 숫자 둘(7시간·90일)과 도구 설명
- **Title**: 하루 최대 7시간, 한 해 90일 — 물질은 무리 지어 한다
- **Core message**: 물질은 개인 기술이지만 작업은 무리 단위로 이루어진다
- **Content**: 하루 최대 7시간 · 연 90일 (유네스코) · 보통 15명 정도가 무리지어 조업 (제주특별자치도) · 빗창 — 전복 등을 채취하는 도구 / 테왁 — 물 위에서 몸을 싣고 쉬는 부력 도구 / 망시리 — 테왁에 달린 그물주머니 · 채취물: 소라·전복·성게·해조류 · 출처 줄
- **Images**: dive_column.jpg
- **Motion suggestion**: 앞 쪽 장면의 연속 상태 — 수중 창과 수면선이 제자리를 옮기고 숫자가 드러남
- **Fact IDs**: F002, F016, F031

#### Slide 05 - 상군·중군·하군

- **Audience move**: 해녀를 균질한 집단으로 보던 인식 → 기량 위계와 순환이 있는 조직임을 앎
- **Relationships**: order — 하군 → 중군 → 상군 → 다시 하군(순환); parent — 상군이 다른 해녀를 지도; membership — 상군 중 특출한 해녀는 대상군
- **Composition**: 기량 사다리가 한 바퀴 도는 순환 구조; 상군의 지도 역할을 한 줄 강조
- **Title**: 기량은 하군에서 상군으로, 다시 하군으로 돈다
- **Core message**: 기량 위계는 평생 한 바퀴 도는 순환이며 상군이 나머지를 이끈다
- **Content**: 상군 — 작업 기량이 뛰어난 해녀 (특출하면 대상군) / 중군 — 보통 기량 / 하군 — 기량이 떨어지는 해녀 · 하군에서 출발해 상군이 되었다가 다시 하군으로 돌아옴 · 유네스코: 상군이 다른 해녀들을 지도 · 출처 줄
- **Fact IDs**: F003, F015

#### Slide 06 - 불턱

- **Audience move**: 돌담 쉼터로만 보이던 불턱 → 지식 전수와 의사결정이 일어나는 공동체 공간임을 앎
- **Relationships**: membership — 불턱의 세 기능(옷을 갈아입고 불 쬐는 곳 / 지식·요령·바다밭 위치 전수 / 상호협조와 의사결정); order — 1985년 전후 현대식 탈의장이 역할을 대신
- **Composition**: 원형 창의 불턱 이미지를 중심에 두고 둘레에 세 기능
- **Title**: 불턱은 탈의실이자 학교이자 회의장이었다
- **Core message**: 불턱은 해녀 공동체의 지식과 합의가 오가던 자리다
- **Content**: 세 기능 · 현재 70여 개가 남음 · 1985년 전후 현대식 탈의장이 불턱의 역할을 대신 · 출처 줄
- **Images**: bulteok_ring_duo.jpg
- **Fact IDs**: F011

#### Slide 07 - 바다밭

- **Audience move**: 바다를 누구나 따는 곳으로 여기던 인식 → 어촌계의 어업권과 공동체 규칙 아래 함께 가꾸는 공유지임을 앎
- **Relationships**: membership — 어업권을 가진 지역 어촌계, 해녀회, 잠수굿, 바다밭 가꾸기가 한 공동체 관리에 속함; link — 가꾸어 공존하는 방식 → 공유지의 지속적 이용과 분배
- **Composition**: 아래 절반의 넓은 해저 띠 위에 판단 문장과 세 요소
- **Title**: 바다밭은 함께 가꾸는 공유지다
- **Core message**: 해녀는 바다밭을 채취 대상이 아니라 함께 가꾸는 밭으로 다룬다
- **Content**: 바다밭을 끊임없이 가꾸어 공존 (해녀박물관) · 어업권을 가진 지역 어촌계와 해녀회 (유네스코) · 잠수굿 — 물질 전 바다의 여신에게 안전과 풍어를 빎 · 국가유산청: 공유지의 지속적 이용과 분배에 관한 지혜 · 출처 줄
- **Images**: sea_field.jpg
- **Fact IDs**: F004, F005, F008, F009

### Part 3: 왜 인류의 유산인가

#### Slide 08 - 여섯 번의 지정

- **Audience move**: '유네스코 유산'이라는 한 줄만 알던 청중 → 노래·도구·어업·문화·종목·어업체계로 반세기에 걸친 여섯 번의 지정을 앎
- **Relationships**: order — 1971 → 2008 → 2015 → 2016 → 2017 → 2023; membership — 도 지정 / 국가 지정 / 세계 지정
- **Title**: 노래에서 어업 체계까지, 반세기 동안 여섯 번 지정되었다
- **Core message**: 지정 대상이 노래·도구에서 문화와 어업 체계 전체로 넓어졌다
- **Content**: 1971 해녀노래 — 도 무형문화재 제1호 · 2008 제주해녀의 물옷과 물질도구 — 도 민속문화재 제10호 · 2015 제주해녀어업 — 국가중요어업유산 제1호 · 2016 제주해녀문화 — 유네스코 인류무형문화유산 · 2017 해녀 — 국가무형유산(당시 국가무형문화재 제132호) · 2023 제주 해녀어업시스템 — FAO 세계중요농업유산 · 출처 줄
- **Visualization**: heritage-timeline — table/record_table, 열: 연도 · 대상 · 지정 · 범위
- **Native-ready**: heritage-timeline=yes
- **Fact IDs**: F001, F007, F012, F026

#### Slide 09 - 지정의 이유

- **Audience move**: 지정 사실 → 평가 기관이 무엇을 높이 샀는지(공동체·여성·지속가능성) 설명할 수 있음
- **Relationships**: membership — 유네스코의 세 평가(여성 지위 향상 / 친환경 방법과 공동체 어업 관리 / 세대 간 전승), 국가유산청의 공동체 종목 지정, FAO 2023 지정
- **Composition**: 세 평가를 나란히 두고, 국가유산청의 '보유자 없는 공동체 종목'을 한 줄 인용처럼 강조
- **Title**: 유네스코와 FAO가 본 것은 기술보다 공동체다
- **Core message**: 유산 지정은 한 사람의 기술이 아니라 공동체가 바다를 다루는 방식에 대한 평가다
- **Content**: 유네스코 — 공동체 안 여성의 지위 향상에 기여 / 친환경 방법과 공동체 어업 관리로 지속가능성 증진 / 가족·학교·어촌계·해녀회·해녀학교·해녀박물관으로 전승 · 국가유산청 — 특정 보유자·보유단체를 인정하지 않는 공동체 종목 · FAO — 2023년 세계중요농업유산 · 출처 줄
- **Fact IDs**: F005, F006, F007, F026

### Part 4: 누가 바다를 잇는가

#### Slide 10 - 해녀 수

- **Audience move**: 해녀가 '줄고 있다'는 막연한 인상 → 55년 사이 여섯 명 중 한 명만 남았다는 크기를 앎
- **Relationships**: order — 1970 → 1980 → 1990 → 2000 → 2010 → 2020 → 2025 연도순 감소
- **Composition**: 넓은 막대 차트 한 개와 끝값 2,371명 강조
- **Title**: 55년 사이, 여섯 명 중 한 명만 바다에 남았다
- **Core message**: 1970년 14,143명 → 2025년 2,371명(16.8%, 계산)
- **Content**: 연도별 현직 해녀 수(명): 1970 14,143 · 1980 7,804 · 1990 6,827 · 2000 5,789 · 2010 4,995 · 2020 3,613 · 2025 2,371 · 주: 2025년만 5년 간격 · 계산: 2,371 ÷ 14,143 = 16.8% · 출처 줄(도의회 심사보고서 참고자료 2023, 해녀박물관 해녀 현황 2025년말)
- **Visualization**: haenyeo-count — chart/column_chart, 세로축 제목 「명」
- **Native-ready**: haenyeo-count=yes
- **Motion suggestion**: 끝값 2,371명 표지가 다음 쪽 머리로 이어져 '줄어든 사람들'에서 '남은 사람들의 나이'로 넘어감 (P10 → P11 연속 상태)
- **Fact IDs**: F018, F024

#### Slide 11 - 연령 구성

- **Audience move**: 인원 감소 → 남은 해녀 대부분이 60세 이상이라는 구조 변화를 앎
- **Relationships**: contrast — 1970년 연령 구성 대 2025년 연령 구성
- **Composition**: 두 개의 100% 누적 가로 막대(1970·2025)와 60세 이상 구간 강조
- **Title**: 1970년 4.6%였던 60세 이상이 2025년에는 90.1%다
- **Core message**: 남은 해녀 열 명 중 아홉이 60세 이상이다
- **Content**: 1970(%) — 30세 미만 31.3 · 30~49세 54.9 · 50~59세 9.2 · 60세 이상 4.6 · 2025(%, 계산) — 30세 미만 0.2 · 30~49세 4.3 · 50~59세 5.4 · 60세 이상 90.1 · 2025년 70세 이상 1,502명(63.3%, 계산) · 40세 미만 30명 · 기준: 2025년말 현직 해녀 2,371명 · 출처 줄
- **Visualization**: age-shift — chart/stacked_bar_chart, 값 축 제목 「%」
- **Native-ready**: age-shift=yes
- **Motion suggestion**: 앞 쪽에서 넘어온 2,371명 표지가 기준값으로 자리 잡음
- **Fact IDs**: F017, F025, F030

#### Slide 12 - 들어오는 사람과 떠나는 사람

- **Audience move**: 고령화 사실 → 신규 유입이 자연 감소를 메우지 못하는 흐름을 앎
- **Relationships**: contrast — 신규 가입 연 30여 명 대 자연 감소 연 100여 명; link — 신규 유입이 없다고 가정한 전망 2050년 169명
- **Composition**: 신규 가입 막대 차트 옆에 자연 감소 연 100여 명 기준 표시와 FAO의 '10명 중 1명' 인용
- **Title**: 들어오는 사람은 한 해 30여 명, 떠나는 사람은 100여 명이다
- **Core message**: 지금의 유입 속도로는 감소를 멈출 수 없다
- **Content**: 신규 해녀 어촌계 가입(명): 2015 17 · 2016 24 · 2017 17 · 2018 29 · 2019 49 · 2020 36 · 2021 38 · 2022 28 (합계 238) · 자연 감소 연 100여 명 대비 신규 연 30여 명 (제주특별자치도) · FAO: 10명이 떠날 때 1명이 들어옴 · 전망: 신규 유입이 없다고 가정하면 2050년 169명(2020년 대비 5.2%, 사업부서 전망) · 출처 줄
- **Visualization**: new-entrants — chart/column_chart, 세로축 제목 「명」
- **Native-ready**: new-entrants=yes
- **Fact IDs**: F020, F021, F027

#### Slide 13 - 전승 장치

- **Audience move**: 위기 인식 → 이미 작동 중인 전승 장치와 그 성과를 앎
- **Relationships**: membership — 해녀학교, 어촌계 가입비 지원, 정착지원금, 전승 경로(가족·학교·어촌계·해녀회·해녀박물관); link — 해녀학교 졸업생 → 어촌계 가입의 44%
- **Composition**: 왼쪽 절반 전승 이미지, 오른쪽 글 단에 강조 숫자 44%와 지원 두 가지
- **Title**: 해녀학교가 새 해녀의 절반 가까이를 길러 냈다
- **Core message**: 2016~2023년 어촌계 가입 217명 중 95명(44%)이 해녀학교 졸업생이다
- **Content**: 해녀학교 졸업생 95명 / 어촌계 가입 217명 = 44% (2016~2023) · 어촌계 가입비 1인 100만 원 지원 · 초기 정착지원금 월 50만 원 × 3년 (2022.12.30 조례 개정) · 전승 경로: 가족·학교·어촌계·해녀회·해녀학교·해녀박물관 · 출처 줄
- **Images**: two_divers.jpg
- **Fact IDs**: F005, F022, F023

### Part 5: 정리

#### Slide 14 - 정리

- **Audience move**: 흩어진 사실들 → 한 문장으로 기억할 결론을 가짐
- **Relationships**: link — 조직(개인 기량 + 공동체 규칙) → 평가(공동체 방식에 대한 유산 지정) → 과제(다음 세대의 합류)
- **Composition**: 한 문장 결론과 세 줄 요약; 「정리」 표시
- **Title**: 해녀를 잇는다는 것은 숨의 기술과 바다의 규칙을 함께 잇는 일이다
- **Core message**: 기술만이 아니라 공동체의 규칙과 사람을 함께 이어야 한다
- **Content**: 1 물질은 개인의 숨을 공동체의 규칙이 묶는 체계 · 2 여섯 번의 지정은 그 공동체 방식에 대한 평가 · 3 2025년 2,371명, 70세 이상 63.3% — 다음 세대의 합류가 관건 · 표시 — 정리
- **Fact IDs**: F024, F025

#### Slide 15 - 출처와 더 읽을거리

- **Audience move**: 강연을 들은 청중 → 원자료를 직접 찾아볼 수 있는 경로를 가짐
- **Relationships**: membership — 국제기구(유네스코·FAO) / 국가(국가유산청) / 제주(해녀박물관·도 누리집·도의회)
- **Closing impact**: 마무리 문장 "바다밭은 사람이 있어야 밭이 됩니다"(정리) + 주요 출처로 가는 링크 목록 (binding). 구성 Reference: 표지 장면을 흑백 띠로 다시 부름
- **Title**: 더 알고 싶다면, 원자료로
- **Core message**: 모든 수치는 공식 자료에서 왔고, 직접 확인할 수 있다
- **Content**: 마무리 문장(정리) · 링크 목록 — 유네스코 「Culture of Jeju Haenyeo (women divers)」 https://ich.unesco.org/en/RL/culture-of-jeju-haenyeo-women-divers-01068 · FAO 「HAENYEO – WOMEN OF THE SEA」 https://digital-media.fao.org/archive/HAENYEO---WOMEN-OF-THE-SEA-2A6XC5LG8V9J.html · 국가유산청 국가유산포털 「해녀」 https://www.heritage.go.kr/heri/cul/culSelectDetail.do?ccbaCpno=127ZZ01320000 · 제주해녀박물관 「제주해녀 현황」 https://www.jeju.go.kr/haenyeo/haenyeo/statistics.htm · 제주해녀박물관 「해녀소개」 https://www.jeju.go.kr/haenyeo/haenyeo/haenyeo.htm · 제주특별자치도 「물질하는 여성」 https://www.jeju.go.kr/culture/folklore/samda/women/diverWomen.htm · 제주특별자치도의회 「해녀의전당 건립사업 심사보고서」 https://record.council.jeju.kr/CLRecords/Files/FileAppendix/a12/A042087.pdf · 유엔 UNifeed 「FAO / HAENYEO WOMEN OF THE SEA」 https://media.un.org/unifeed/en/asset/d348/d3486310
- **Images**: cover_surface_dim.jpg

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 쪽마다 화면의 판단 문장을 먼저 말하고, 화면의 수치는 출처 기관과 연도를 함께 말한다. 조사 자료(`sources/jeju_haenyeo_ko_research.md`)에 없는 사실은 추가하지 않는다. 계산값은 "계산하면"으로 밝힌다
- **Total duration**: 약 35분 (쪽당 2~3분)
- **Notes style**: 대화체 — 청중에게 질문을 던지고 앞 쪽과 다리를 놓는 강연 말투
- **Presentation purpose**: 물질의 조직을 설명하고, 유산 지정의 이유를 보여 준 뒤, 인원·연령 변화로 전승 과제를 드러낸다

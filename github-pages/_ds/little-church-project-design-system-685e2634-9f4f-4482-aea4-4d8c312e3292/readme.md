# 리틀처치 프로젝트 — Design System

**리틀처치 프로젝트 / The Little Church Project**
슬로건: **예배가 있는 집, 교회가 되는 가정**

가정에서 부모와 아이가 함께 드리는 짧은 예배를 돕는 프로젝트입니다. 가정예배지, 주간 큐티, 절기 자료 같은 인쇄물과, 그 자료를 배포·안내하는 온라인 화면이 주요 산출물입니다. 톤은 "작은 교회가 된 집" — 따뜻하고 친근하며, 부모에게 부담을 주지 않는 목소리입니다.

## 제공된 소스

브랜드 설명과 슬로건, 그리고 "따뜻하고 친근한 로고, 가정 안에 작은 교회 느낌"이라는 방향성만 텍스트로 전달받았습니다. **코드베이스·Figma·기존 로고 파일·폰트 바이너리는 제공되지 않았습니다.** 따라서 이 시스템의 시각 요소는 브랜드 설명에서 도출한 제안이며, 원본 자료가 확보되면 교체를 전제로 합니다.

대체 항목(사용자 확인 필요):
- **폰트**: 브랜드에서 실제 폰트 파일을 받아 `assets/fonts/`에 포함했습니다. 제목 **펴진고딕(Pyeojin Gothic, 7웨이트)**, 본문·UI **Paperlogy(5웨이트)**, 어린이용 라벨 **에이투지체(A2G, Medium/Bold)**. 숫자·토큰 라벨만 **IBM Plex Mono**(Google Fonts)를 씁니다.
- **로고**: 원본 미제공 → 사용자 요청에 따라 "집 안의 십자가" 선 마크를 제작 (`assets/logo-mark.svg`, `assets/logo.svg`). 확정 전 시안입니다.
- **아이콘**: 자체 아이콘 세트 미제공 → **Lucide 0.470.0** (CDN, 1.75px stroke) 사용.

## CONTENT FUNDAMENTALS

**목소리** — 교회가 신자에게 말하는 톤이 아니라, 먼저 해 본 부모가 옆에서 알려주는 톤입니다. 우리는 "저희"보다 **"우리"**, 독자는 **"부모님"** 또는 생략된 2인칭입니다. 명령형 대신 청유형: "읽으세요" 대신 **"함께 읽어요"**, "실천하십시오" 대신 **"이번 주엔 이렇게 해볼까요"**.

**문장 길이** — 짧게. 한 문장 25자 내외, 한 문단 3문장 이내. 부모가 아이 옆에서 소리 내어 읽을 수 있는 길이여야 합니다.

**부담 낮추기** — 시간·분량을 항상 먼저 밝혀 진입장벽을 낮춥니다. 예: "**주일 저녁 15분**", "**성경 한 구절, 질문 두 개**", "준비물은 성경책 하나면 충분합니다."

**케이싱** — 한글은 문장형(sentence case)만. 전체 대문자는 라틴 소문 라벨(eyebrow)에서만 사용하고 자간을 넓힙니다: `THE LITTLE CHURCH PROJECT`, `WEEK 03`. 한글 자간 넓히기(공 백 넣 기)는 금지.

**성경 인용** — 본문과 출처를 분리하고 출처는 브랜드 색으로 작게. 예: "너희 자녀에게 부지런히 가르치며" / **신명기 6:7**. 개역개정 표기를 기본으로 하며, 인용문은 절대 고쳐 쓰지 않습니다.

**숫자·용어** — 주차는 "3주차", 연령은 "만 4–6세", 소요시간은 "15분". 신학 용어는 아이가 알아듣는 말로 풀어 씁니다("성화" → "닮아가는 것").

**이모지** — 사용하지 않습니다. 강조는 색과 크기로만.

**쓰지 않는 표현** — "지금 바로 신청하세요" 같은 마케팅 명령형, "○○ 해야 합니다" 식 의무 부과, 느낌표 연속, 죄책감을 자극하는 문구("이것도 안 하면").

## VISUAL FOUNDATIONS

**색** — 파스텔 계열의 밝은 따뜻함. 종이색(`--paper-*`, 거의 흰색에 가까운 크림)이 모든 화면의 바닥이고, 그 위에 복숭아빛 **코랄(`--brick-*`)**이 브랜드 기본색으로 얹힙니다. 민트 세이지(`--olive-*`)는 성장·절기·달력, 버터 옐로(`--honey-*`)는 강조(아주 소량), 연하늘(`--sky-*`)은 정보성 표시에, 라일락(`--lilac-*`)은 어린이용 자료의 놀이 액센트에만 씁니다(성인용 화면에는 사용하지 않음). 검정은 쓰지 않고 잉크는 항상 따뜻한 갈색(`--ink-0` = `#3A2B23`). 한 화면에 배경색은 2개까지.

**타입** — 전부 고딕입니다. 제목은 `--font-display`(펴진고딕) **700 + 음수 자간(-0.03em)**으로 로고와 같은 좁고 단단한 인상을, 본문은 `--font-body`(Paperlogy) 400에 **줄간 1.75**로 넉넉하게 둡니다. `--font-display`(펴진고딕)는 워드마크·슬로건·큰 디스플레이 조판에만 쓰고, 컴포넌트 제목(Card·Dialog·SectionHeading)과 성경 인용은 Paperlogy Bold/Medium으로 둡니다. `--font-round`(에이투지체)는 어린이용 자료의 라벨·말풍선·활동 카드에만 쓰고 본문에는 쓰지 않습니다. 한글 본문은 작은 크기에서 자간을 0으로 두고, 디스플레이에서만 좁힙니다. 스케일은 56/42/32 → 26/21/18 → 18/16/14 → 13/11px.

**여백·레이아웃** — 4px 배수 스케일(`--space-1`~`--space-32`). 본문 폭은 `--measure-prose`(62ch)를 넘기지 않고, 페이지 최대 폭은 1120px, 페이지 인셋은 모바일 24px / 데스크톱 56px. 섹션 간 수직 여백은 96px로 크게. 고정 요소는 헤더 하나뿐이며, 스크롤 시 `--surface-page`에 `--shadow-1`만 얹습니다(블러 없음).

**배경** — 이미지 없이 색면 위주. 전면 사진(full-bleed)은 히어로 한 곳에만 허용하고, 그 위 텍스트는 보호 그라디언트 대신 **캡슐(반투명 종이색 카드)**을 얹습니다. 그라디언트, 특히 보라-파랑 계열은 사용하지 않습니다. 텍스처는 필요할 때 아주 약한 종이 결 하나까지만.

**이미지 색감** — 따뜻하고 밝게, 노출을 살짝 올리고 채도는 낮춤. 집 안의 실제 장면(식탁, 스탠드 조명, 아이 손, 성경책)을 가까이 찍은 것을 선호. 차가운 청색 조명, 스톡 사진 특유의 과장된 미소, 흑백은 피합니다.

**모서리** — 4 / 8 / 14 / 22px + pill. 태그 4, 인풋·버튼 8, 카드 14, 시트·피처 패널 22.

**카드** — 종이색 배경(`--surface-card`) + 1px 헤어라인(`--line-hairline`) + `--shadow-1`. 강조 카드만 `--shadow-2`. 컬러 좌측 보더 액센트는 사용하지 않습니다. 카드 내부 패딩은 `--card-pad`(24px).

**그림자** — 모두 갈색 틴트(중성 회색 금지)이며 매우 옅음. `--shadow-1`~`--shadow-4`, 인풋 상단 하이라이트용 `--shadow-inset`, 포커스 링 `--ring-focus`(코랄 28%). "유리가 떠 있는" 느낌이 아니라 "종이 위의 종이"로 읽히게 합니다.

**보더** — 1px 헤어라인이 기본, 2px는 선택·활성 상태에만. 점선은 빈 상태(empty state)에서만.

**투명도·블러** — 블러는 모달 오버레이(잉크 24% + 2px 블러)에만. 반투명 표면은 사진 위 캡슐에만 허용하고, 일반 UI에서는 불투명 색면을 씁니다.

**모션** — 짧고 부드럽게. `--dur-fast:120ms`(호버), `--dur-base:200ms`(대부분), `--dur-slow:340ms`(시트·모달). 이징은 `--ease-soft`(`cubic-bezier(.22,.61,.36,1)`). 페이드 + 4–8px 상승만 사용하고, 바운스·스프링·회전은 쓰지 않습니다. `prefers-reduced-motion`에서는 페이드만 남깁니다.

**호버/프레스** — 채워진 표면은 호버 시 한 단계 어둡게(`--brick-500` → `--brick-600`), 프레스 시 한 단계 더 어둡게 + `translateY(1px)`. 투명 표면은 호버 시 `--surface-brand-soft`가 깔립니다. 스케일 축소나 opacity 변경은 쓰지 않습니다(텍스트 링크만 색 변경: `--text-link` → `--text-link-hover`).

## ICONOGRAPHY

- **Lucide 0.470.0**을 CDN에서 로드해 사용합니다(`https://unpkg.com/lucide@0.470.0/dist/umd/lucide.js`). 브랜드 자체 아이콘 세트가 없어 선택한 **대체 세트**이며, 선 굵기와 라운드 캡이 로고 마크와 일치해 채택했습니다. 원본 아이콘이 있으면 교체하세요.
- 규격: **1.75px stroke, round cap/join, 20px 기본**(16 / 20 / 24px). 색은 `currentColor` — 아이콘 단독 색상 지정은 금지.
- `Icon` 컴포넌트로만 렌더합니다: `<Icon name="home" />`. 자주 쓰는 이름: `home`, `book-open`, `calendar`, `users`, `heart-handshake`, `download`, `printer`, `chevron-right`, `check`.
- 아이콘은 라벨을 보조할 때만 쓰고, 아이콘 단독 버튼은 `IconButton` + `aria-label` 필수.
- **이모지는 UI·인쇄물 어디에도 사용하지 않습니다.** 유니코드 기호도 쓰지 않으며(불릿은 CSS로), 아이콘을 직접 그리지 마세요.
- 브랜드 마크(`assets/logo-mark.svg`)는 지붕 + 십자가 선 도형으로, 아이콘과 같은 선 언어를 공유합니다. 최소 크기 24px, 최소 여백은 지붕 높이의 1/2.

## Components

`components/` 아래 4개 그룹, 19개 컴포넌트. 각 디렉터리에 `.jsx` + `.d.ts` + `.prompt.md` + 카드 HTML이 있습니다.

- **core** (`components/core/`) — `Button`, `IconButton`, `Icon`, `Card`, `Badge`, `Tag`
- **forms** (`components/forms/`) — `Field`, `Input`, `Textarea`, `Select`, `Checkbox`, `Radio`, `Switch`
- **feedback** (`components/feedback/`) — `Dialog`, `Toast`, `Tooltip`
- **navigation** (`components/navigation/`) — `Tabs`
- **brand** (`components/brand/`) — `SectionHeading`, `VerseBlock`

**Intentional additions** — 소스가 컴포넌트 인벤토리를 정의하지 않아 표준 세트를 저작했습니다. 브랜드 고유 추가는 두 개입니다: `VerseBlock`(모든 표면에 반복되는 성경 인용 블록), `SectionHeading`(eyebrow + 제목 + 설명 조합), 그리고 Lucide 글리프 래퍼인 `Icon`.

## Index

- `styles.css` — 소비 프로젝트가 링크하는 단일 진입점 (`@import`만).
- `tokens/` — `fonts.css`, `colors.css`, `typography.css`, `spacing.css`, `radius.css`, `elevation.css`, `motion.css`
- `guidelines/` — Design System 탭에 표시되는 specimen 카드: 색(`color-coral.html`, `color-sky.html`, `color-olive-honey.html`, `color-lilac.html`, `color-paper.html`, `color-ink.html`, `color-pairs.html`, `color-semantic.html`), 타입(`type-*.html`), 여백(`spacing-*.html`, `layout-measures.html`), `radius.html`, `elevation.html`, `motion.html`, 브랜드(`logo.html`, `wordmark.html`, `slogan.html`)
- `assets/` — `logo-mark.svg`(심볼), `logo.svg`(마크 + 워드마크), `fonts/`(펴진고딕·Paperlogy·에이투지체 원본 파일)
- `components/` — 위 Components 목록
- `SKILL.md` — Claude Code 등에서 스킬로 사용할 때의 진입 문서
- `thumbnail.html` — 홈 화면 타일

**아직 없는 것**: UI 킷(제품 화면 재현)과 슬라이드 템플릿. 실제 제품 화면이나 인쇄물 원본이 제공되면 추가합니다.

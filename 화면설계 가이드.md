# 검진서비스 화면설계 및 프로토타입 작성규칙

> v1 | 2026-06-10 | 최초 작성
> 피그마용 HTML(화면설계서)과 인터랙티브 프로토타입(HTML) 모두에 공통 적용.
> 디자인 시스템 기준: 검진서비스_화면설계및프로토타입가이드_v1_20260610.md

---

## 1. 디바이스 기준 (공통)

| 항목 | 값 |
|---|---|
| 기준 기기 | 스마트폰 (모바일 앱) |
| 프레임 사이즈 | 393 × 852px |
| 프레임 border-radius | 40px |
| Dynamic Island | 없음 |
| Status Bar 높이 | 44px |
| Status Bar 내용 | 와이파이·배터리 아이콘만 (시간 표시 없음) |
| Home Indicator | width 134px, height 5px, color #222222, 하단 10px margin |
| 네비게이션 바 높이 | 56px |
| 탭바 높이 | 82px (padding-bottom 24px 포함) |

---

## 2. 컬러 시스템 (공통)

```css
:root {
  /* Primary */
  --p:   #0066CC;   /* 버튼, 활성 상태, 포커스 테두리 */
  --pd:  #004FA3;   /* hover, 헤더 강조 */
  --pdd: #003380;   /* pressed */
  --pl:  #E8F2FF;   /* 배경 강조, 배너, 힌트박스, 선택 칩 */
  --plm: #D0E6FF;   /* 아바타 배경, 카드 선택 배경 */
  --acc: #00A3E0;   /* 포인트 하늘색, step 화살표 */

  /* Text */
  --t1: #1A1A1A;   /* 본문, 제목 */
  --t2: #444444;   /* 라벨, 서브 텍스트 */
  --t3: #888888;   /* 설명, placeholder, 캡션 */
  --t4: #BBBBBB;   /* disabled, 비활성 */

  /* Semantic */
  --success: #00B86E;
  --sbg:     #E8F7F0;   /* 예약확정 배경 */
  --st:      #006B40;   /* 예약확정 텍스트 */
  --warn:    #FF8C00;
  --wbg:     #FFF3E0;   /* 신청완료 배경 */
  --wt:      #8A4D00;   /* 신청완료 텍스트 */
  --danger:  #CC2200;
  --dbg:     #FFF0EE;   /* 에러·필수 배경 */

  /* Background & Border */
  --bg:     #E8EDF5;   /* 앱 전체 배경 */
  --white:  #FFFFFF;
  --border: #DDE3EE;   /* 인풋 테두리, 구분선 */
}
```

---

## 3. 타이포그래피 (공통)

- 폰트: `Noto Sans KR`
- CDN: `https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;500;600;700`

| 용도 | Size | Weight |
|---|---|---|
| 페이지 대제목 | 24px | 700 |
| 섹션 타이틀 | 22px | 700 |
| 화면 타이틀 | 20px | 700 |
| 네비게이션 타이틀 | 17px | 600 |
| 블록 타이틀 | 15px | 600 |
| 본문 / 인풋 텍스트 | 15px | 400 |
| 라벨 | 13px | 500 |
| 서브 텍스트 | 13px | 400 |
| 힌트·캡션 | 12px | 400 |
| 뱃지·칩 텍스트 | 11px | 600 |
| 탭바 텍스트 | 10px | 400(비활성) / 600(활성) |

---

## 4. 컴포넌트 규격 (공통)

### 버튼
| 종류 | Height | Radius | 색상 |
|---|---|---|---|
| Primary | 52px | 14px | bg #0066CC, text #FFFFFF, 16px/600 |
| Secondary | 52px | 14px | bg #FFFFFF, border 1.5px #0066CC, text #0066CC, 15px/600 |
| Ghost/Dashed | 48px | 14px | border 1.5px dashed #0066CC, text #0066CC, 14px/500 |
| 뒤로가기 | - | - | ‹ 유니코드 32px/300 — 아이콘 사용 금지 |

- 필수 입력 항목 모두 입력 시 Primary 버튼 활성화

### 입력 필드
| 항목 | 값 |
|---|---|
| Height / Radius | 50px / 10px |
| 기본 테두리 | 1px solid #DDE3EE |
| 포커스 테두리 | 1.5px solid #0066CC |
| 에러 테두리 | 1.5px solid #CC2200 |
| 패딩 | 0 16px |
| Placeholder | 13px / #BBBBBB |
| 에러 처리 | 하단 서포팅 텍스트 12px / #CC2200 |

### 카드
| 항목 | 값 |
|---|---|
| Radius / 테두리 | 14px / 1px solid #DDE3EE |
| 배경 / 패딩 | #FFFFFF / 14px 16px |
| hover 테두리 | 1px solid #0066CC |

### 뱃지 / 칩
| 종류 | Radius | Padding |
|---|---|---|
| 상태 뱃지 | 20px | 4px 10px |
| 선택 칩 / 필터 칩 | 20px | 8px 16px |

### 모달
| 항목 | 값 |
|---|---|
| Radius / 패딩 | 20px / 24px |
| 오버레이 | rgba(0,0,0,0.55) |
| 버튼 | height 46px / radius 12px |

### 힌트박스
| 항목 | 값 |
|---|---|
| Radius / 배경 | 10px / #E8F2FF |
| 텍스트 | 12px / #004FA3 / 패딩 12px 14px |

### 네비게이션 바
- 높이 56px
- 좌측: ‹ (유니코드 32px/300) — 아이콘 사용 금지
- 타이틀: 17px/600/#1A1A1A, position absolute 중앙 고정
- [내비] 없는 화면: 로그인(진입점) / 메인 홈(탭바) / 예약 완료

### 탭바
- 높이 82px, padding-bottom 24px
- 상단 구분선 1px solid #DDE3EE
- 아이콘 22px, 활성 #0066CC / 비활성 #BBBBBB

---

## 5. 번호 뱃지 규칙 (공통)

| 항목 | 값 |
|---|---|
| 모양 / 크기 | 원형 22×22px |
| 기본 색상 | #CC2200 |
| 미확정 항목 | #FF8C00 |
| 서브 항목(X-2 등) | #CC2200 opacity 0.75 |
| 테두리 / 위치 | 2px solid #FFFFFF / 좌측 상단 (top -10px, left -8px) |
| 폰트 | 10px / 700 / #FFFFFF |

---

## 6. 아이콘 & 외부 리소스 (공통)

| 항목 | 값 |
|---|---|
| 아이콘 라이브러리 | Tabler Icons |
| CDN 버전 | **@2.44.0 고정** (`@latest` 사용 금지) |
| CDN URL | `https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.44.0/dist/tabler-icons.min.css` |
| 엑박 발생 시 | 유니코드 문자로 대체 (← `‹`, → `›`) |

```css
i[class^="ti"] {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  line-height: 1;
}
```

---

## 7. scroll-body 기본 설정 (공통)

```css
.scroll-body {
  flex: 1;
  overflow-y: auto;
  overflow-x: visible;
  padding: 16px 24px 80px 32px;
  /* 상단 16px: 첫 번째 번호 뱃지 클리핑 방지 */
  /* 하단 80px: 탭바·플로팅 버튼에 가려지는 콘텐츠 방지 */
  /* 좌측 32px: 번호 뱃지 클리핑 방지 */
}
```

---

## 8. 피그마용 HTML 생성 규칙

> 산출물: 모든 화면을 가로로 나열한 HTML 단일 파일 (HTML to Figma 플러그인 임포트용)

### 레이아웃 구조
```
.figma-canvas
  └── .figma-screen-wrap [data-figma-layer-name="screen/{화면ID}"]
        ├── .figma-screen-col
        │     ├── .figma-label  (화면 ID)
        │     ├── .figma-sublabel (화면명)
        │     └── .phone-frame [data-figma-layer-name="frame/{화면명}"]
        │           ├── .status-bar
        │           ├── .nav-bar (해당 화면에 [내비] 있는 경우)
        │           ├── .scroll-body
        │           └── .home-indicator
        └── .annotation-panel (우측 어노테이션)
```

### data-figma-layer-name 규칙
- 최상위: `EAP/화면설계`
- 화면: `screen/{화면ID}` (예: `screen/eap-login-01`)
- 프레임: `frame/{화면명}` (예: `frame/로그인`)
- 컴포넌트: `{번호}/{컴포넌트명}` (예: `1/field-name`, `3/cta-btn`)
- 조건부: `{번호}/{컴포넌트명} [조건부: 조건내용]`
- 미확정: `{번호}/{컴포넌트명} [미확정]`

### 레이아웃 원칙
- `display: flex` 우선 (`position: absolute` 지양)
- Dynamic Island 없음
- 화면 간 간격: `gap: 60px`

---

## 9. 프로토타입 생성 규칙

> 산출물: 좌측 사이드바 + 중앙 폰 프레임 + 우측 어노테이션 패널 구조의 HTML 단일 파일

### 레이아웃 구조
```
.layout
  ├── .sidebar (좌측 — 화면 목록)
  │     ├── .sidebar-header (서비스명)
  │     ├── .sidebar-section (섹션별 화면 버튼)
  │     └── .sidebar-footer
  ├── .main-area (중앙)
  │     ├── topbar (뒤로가기 / 처음으로 버튼)
  │     ├── .canvas
  │     │     └── .phone-frame (393×852px)
  │     └── .flow-info (현재 화면 정보)
  └── annotation-panel (우측 — 컴포넌트 description)
```

### 화면 전환 패턴
```javascript
// 전역 상태로 현재 화면 관리
let currentScreen = 'login01';

function showScreen(id) {
  document.querySelectorAll('.screen').forEach(s => s.style.display = 'none');
  document.getElementById(id).style.display = 'flex';
  updateAnnotation(id);  // 우측 어노테이션 자동 업데이트
  currentScreen = id;
}
```

### 어노테이션 패널 규칙
- 화면 전환 시 해당 화면의 컴포넌트 description 자동 업데이트
- 번호 뱃지 스타일 통일 (섹션 5 기준)
- [조건부] 항목은 주황색 번호 뱃지 (#FF8C00)

### 인터랙션 구현 기준
| 기능정의서 내용 | 구현 방법 |
|---|---|
| 버튼 탭 → 화면 이동 | `showScreen('화면ID')` 호출 |
| 조건 분기 | 분기 조건별 버튼/탭 각각 구현 |
| 모달/바텀시트 | `display: none/flex` 토글 |
| 탭 전환 | 탭 클릭 시 콘텐츠 영역 교체 |
| 토글 ON/OFF | 클래스 토글 |
| 플로팅 바 | `position: sticky; bottom: 0` |

---

## 10. 금지 사항 (공통)

- `@latest` CDN 사용 금지 → 버전 고정 (@2.44.0)
- `position: absolute` 남용 금지 → `display: flex` 우선
- Dynamic Island 추가 금지 (디바이스 기준 없음)
- 외부 이미지 URL 직접 삽입 금지 → placeholder 처리

# Training365

Star Truck Korea 본사와 Sales Agent(판매대리인)가 자료 · 공지 · 교육을 주고받는 Training365 — https://training365.startruckkorea.com

- **게시판 7개**: CRM · 제품 & 경쟁사 정보 · 고객대응 가이드 · 세일즈 트레이닝 · 필수 교육자료 · 마케팅 · 일반게시판
- **인트라넷 게시판 화면**: Overview 는 「게시판 홈」(모든 게시판 검색 · 공지 · 필수 · 게시판별 최근 글 상자), 목록은 위쪽 보기 탭(전체 · 안 읽은 글 · 공지 · 필수 · 확인 필요, 건수) · 검색어 강조 · 목록형/요약형 · 쪽당 15/30/50개(이 브라우저에 기억). 글은 목록 위 큰 창으로 엽니다.
- **카테고리 · 배너 관리**: 카테고리마다 아이콘(고르기 또는 30KB 이하 그림 올리기) · 색 · 문의 담당자(「문의하기」 · 게시판 머리에 보임), 게시판 홈 맨 위 그림 배너(`training365_Banners`, 선택 — 없으면 기본 배너).
- **조회확인**: Agent 만 보이는 버튼. 본사 · 작성자 · 관리자는 게시물마다 누가 · 언제 확인했는지, 미확인 Agent, 확인율(%)을 봅니다.
- **역할**: Agent(열람 · 조회확인) / 본사(열람 · 확인 현황) / 작성자(지정 카테고리 글쓰기) / 관리자(사용자 · 카테고리 · 게시물 · 접속 기록 관리). 등록되지 않은 계정은 「권한 없음」.
- **메뉴 권한(보기 · 편집)**: 역할이 기본값이고, 「사용자 · 권한 관리」 표에서 사람마다 메뉴별 보기 · 편집을 따로 줄 수 있습니다(`training365_Users.Permissions`).
- **접속 기록**: 계정별 로그인 · 로그아웃 시각, 활동 신호, 로그아웃 없이 끝난 세션은 「세션 종료(추정)」 + 마지막 활동 시각. 필터 · 검색 · Excel.
- **로그인**: Microsoft 365(MSAL). 외부 Agent 는 STK 테넌트 B2B 게스트 계정.

## 구성

- `index.html` 한 파일(React 18 · 브라우저 Babel · Tailwind CDN) — MKQR · ICS 와 같은 틀(남색 사이드바 · ←| 접기 · 휴대폰 서랍)
- 데이터: STK-DB SharePoint 목록 `training365_Posts` · `training365_Reads` · `training365_Users` · `training365_AccessLog` (+ 선택 `training365_Categories`), 첨부는 AttachedFiles 라이브러리 `Training365_Media-Files/{게시물 번호}/`, 관리 이력은 `Logging_data/Training365/`
- Worker 없음 · 빌드 없음 — main 에 push 하면 GitHub Pages 로 배포

## 처음 설정

[SETUP_KO.md](SETUP_KO.md) — 목록 · 열, 게스트 권한, Azure 리디렉션 URI, DNS CNAME, GitHub Pages, 설정 키, 첫 실행 순서.

문의: stk_it@hyosung.com · 담당: Sales 박종헌 매니저

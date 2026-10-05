# 체중 달력 (PWA)

체중·식단·스탬프를 기록하고 목표 달성 현황을 보는 체중 달력 앱입니다.
GitHub Pages로 배포한 뒤 아이폰/안드로이드 홈 화면에 앱처럼 설치할 수 있어요.

## 파일 구성
- `index.html` : 앱 본체
- `manifest.json` : 앱 이름·아이콘·전체화면 설정
- `sw.js` : 오프라인 실행용 서비스 워커
- `icons/` : 앱 아이콘 (192, 512, maskable, apple-touch-icon)

## 1. GitHub에 올리기
1. github.com 로그인 → 우측 상단 **+ → New repository**
2. 이름 입력(예: `weight-calendar`), **Public** 선택 → **Create repository**
3. **uploading an existing file** 클릭 → 이 폴더의 파일 전부(`index.html`, `manifest.json`, `sw.js`, `README.md`, `icons` 폴더)를 드래그
   - 폴더 구조 그대로 올라가야 해요. 안 되면 `icons` 폴더 안 파일은 **Add file → Create new file**에서 `icons/파일명` 형태로 따로 올려주세요.
4. **Commit changes**

## 2. GitHub Pages 켜기
1. 저장소 **Settings → Pages**
2. Source: **Deploy from a branch**, Branch: **main** / **(root)** → **Save**
3. 1~2분 뒤 `https://내아이디.github.io/weight-calendar/` 주소가 생겨요.

## 3. 폰에 설치하기
- **아이폰(Safari)**: 주소 접속 → 공유 버튼 → **홈 화면에 추가**
  (반드시 Safari에서 해야 해요. 크롬에서는 안 됩니다)
- **갤럭시(Chrome)**: 주소 접속 → 오른쪽 위 메뉴(⋮) → **앱 설치**(또는 **홈 화면에 추가**) → 설치. 앱 설정 탭에 뜨는 **📲 앱으로 설치하기** 버튼을 눌러도 돼요.
- **갤럭시(삼성 인터넷)**: 주소 접속 → 하단 메뉴(≡) → **현재 페이지 추가 → 홈 화면** (주소창 옆에 설치 아이콘이 보이면 그걸 눌러도 돼요)
  - 설치 후 앱 서랍과 홈 화면에 아이콘이 생기고, 주소창 없이 전체화면으로 열립니다.

## 참고
- 기록은 폰 브라우저의 저장소(localStorage)에 보관돼요. 서버로 전송되지 않습니다.
- 아이폰은 Safari에서 입력한 데이터와 홈 화면 앱의 데이터가 서로 분리돼요. **설치 후에는 홈 화면 앱으로만 기록**하세요.
- Safari 방문기록·웹사이트 데이터를 지우면 기록도 사라집니다.
- 코드를 수정해 다시 올릴 때는 `sw.js`의 `CACHE` 버전(`weight-cal-v1` → `v2`)을 올려야 변경사항이 반영돼요.

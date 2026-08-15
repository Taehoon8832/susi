# 2027 수시 일정 대시보드

Google Apps Script 웹앱을 GitHub Pages 정적 사이트로 옮긴 프로젝트입니다.

원본과 동일하게 **클라이언트 전용**으로 동작합니다. `code.gs`의 `doGet`은 HTML을 서빙만 했고, 일정 데이터·필터·검색·KPI는 모두 브라우저에서 처리됩니다.

## 구성

| 파일 | 역할 |
|------|------|
| `index.html` | UI, 스타일, 필터/검색/렌더 로직 |
| `data.js` | 일정 RAW 데이터 (`var RAW = [...]`) |
| `.nojekyll` | GitHub Pages에서 Jekyll 처리 생략 |

## 로컬에서 보기

`index.html`을 더블클릭해도 되지만, 브라우저 정책에 따라 `file://`에서 스크립트 로드가 막힐 수 있습니다. 그 경우:

```bash
npx --yes serve .
```

브라우저에서 안내된 주소(보통 `http://localhost:3000`)로 엽니다.

## GitHub Pages로 공개하기

1. 이 저장소에 커밋·푸시합니다.
2. GitHub → **Settings** → **Pages**
3. **Source**: Deploy from a branch
4. **Branch**: `main` / `/ (root)` 저장

공개 URL 예: `https://taehoon8832.github.io/susi/`

## 원본과의 차이

- Apps Script `HtmlService` 래퍼(`code.gs`)는 불필요해 제거했습니다.
- 대용량 일정 배열만 `data.js`로 분리했습니다. 디자인·기능은 동일합니다.

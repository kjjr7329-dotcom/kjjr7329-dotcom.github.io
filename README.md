# 라이더 개러지 🏍️

바이크 라이더를 위한 **정비 교체 알림 + 라이딩 일지** 웹앱(PWA).
설치 무료, 로그인 없음, 모든 기록은 사용자 폰에만 저장됩니다.

---

## 📂 폴더 구성
```
rider-garage-pwa/
├─ index.html              ← 앱 본체
├─ manifest.webmanifest    ← 앱 설치 정보(이름·아이콘)
├─ sw.js                   ← 오프라인 캐시(서비스워커)
├─ favicon.ico
└─ icons/                  ← 앱 아이콘들
```
**이 안의 파일을 폴더 구조 그대로** 올려야 합니다. (icons 폴더 포함)

---

## 🚀 깃허브 페이지(GitHub Pages)로 배포하기

1. GitHub에서 **New repository** → 이름 예: `rider-garage`, **Public** 선택 → Create.
2. **Add file → Upload files** 클릭.
3. 압축을 푼 뒤 **index.html, manifest.webmanifest, sw.js, favicon.ico 와 icons 폴더**를 함께 끌어다 놓기.
   - icons 폴더째로 드래그하면 `icons/아이콘...` 경로가 유지됩니다.
4. **Commit changes**.
5. 저장소 **Settings → Pages** → Branch를 `main` / `/ (root)` 선택 → **Save**.
6. 1~2분 뒤 아래 주소로 열립니다.
   ```
   https://<GitHub아이디>.github.io/rider-garage/
   ```
   (예: https://kjjr7329-dotcom.github.io/rider-garage/)

> 폰 브라우저에서 이 주소를 열고 **‘홈 화면에 추가’** 하면 일반 앱처럼 아이콘으로 실행됩니다.

---

## 🔄 앱을 수정해서 다시 올릴 때 (중요)
내용을 고쳐 다시 올렸는데 사용자 폰에서 옛날 화면이 보이면,
**`sw.js` 파일 맨 위의 캐시 버전 숫자만 올려주세요.**
```js
const CACHE = "rider-garage-v1";   // → "rider-garage-v2" 로 변경
```
이러면 다음 접속 때 새 버전을 자동으로 받습니다.

---

## 📣 배포(전파) 팁
- 앱 안 **설정 → 친구에게 공유** 또는 헤더의 📤 버튼으로 링크를 바로 퍼뜨릴 수 있어요.
- 나중에 `rider-garage` 대신 **내 도메인**을 연결하면 더 전문적으로 보입니다.
- 지금은 **완전 무료 · 폰 저장** 구조라 서버비가 0원입니다. 사용자가 늘어도 비용이 늘지 않아요.

---

## 💡 나중에 확장하려면 (참고)
- **계정/클라우드 동기화**가 필요해지면 그때 무료 백엔드(Supabase/Firebase 무료 티어)를 붙일 수 있습니다.
- **구글 플레이/앱스토어 등록**도 이 웹앱을 그대로 감싸서(TWA/PWABuilder) 가능합니다.

made with Claude · v1.0

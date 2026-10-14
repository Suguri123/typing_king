# 내가 우리반 타자왕

동홍초등학교 5학년 쉬는시간용 한글 타자 연습 페이지입니다. 파일 하나(`index.html`)로 동작하며, 순위는 Firebase(Firestore, 프로젝트 `typingking`)에 저장되어 모든 기기에서 같은 순위판을 봅니다.

## 깃허브에 올려서 공유하기 (GitHub Pages)

1. GitHub에서 새 저장소(repository)를 만듭니다. 예: `typing-king`
2. 이 폴더의 `index.html`과 `README.md`를 저장소에 업로드합니다. (Add file → Upload files)
3. 저장소의 **Settings → Pages**로 들어가서 Branch를 `main`, 폴더를 `/ (root)`로 고르고 Save를 누릅니다.
4. 1~2분 뒤 `https://<깃허브아이디>.github.io/typing-king/` 주소로 접속할 수 있습니다. 이 주소를 교실 컴퓨터 즐겨찾기에 넣어 두세요.

## 사용 방법

- 이름을 쓰고 30초/60초를 고른 뒤 **시작!**을 누릅니다. 문장 입력칸을 누르거나 이름 칸에서 Enter를 눌러도 시작할 수 있습니다. 첫 글자를 입력하면 시간이 줄어듭니다.
- 화면의 문장을 똑같이 치면 맞은 글자는 초록, 틀린 글자는 빨강으로 표시되고, 다 치면 다음 문장이 자동으로 나옵니다.
- 점수 = 타/분 × 정확도. 끝나면 순위판에 자동으로 올라갑니다. 1위가 타자왕!

## 알아두기

- 순위는 **Firebase Firestore**(`scores` 컬렉션)에 저장됩니다. 어느 컴퓨터·태블릿에서 해도 같은 순위판이 실시간으로 보입니다. 같은 이름은 같은 사람으로 보고 가장 좋은 기록만 남습니다.
- 순위 초기화: 순위판 아래 "선생님용: 순위 초기화" → 선생님 비밀번호 입력 → 확인. 비밀번호는 페이지가 아니라 `firestore.rules`(서버)에서 확인합니다.
- 비밀번호를 바꾸려면 `firestore.rules`의 `'0815'`를 고친 뒤 `npx firebase-tools deploy --only firestore:rules`로 배포하세요.
- 연습 문장은 `index.html` 안의 `SENTENCES` 목록에서 바꿀 수 있습니다.

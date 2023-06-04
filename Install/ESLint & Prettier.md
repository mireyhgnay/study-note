# <div align="center">✨ ESLint & Prettier</div>

<br>

매번 ESLint / Prettier 관련해서 환경 세팅을 하면 어쩔땐 잘되다가 어쩔땐 안되다가……

이걸 지금 몇개월째 하다말다 하다말다 나 자신이 어이가없다 🙂

아무 생각 없이 블로그 그대로 뭐 설치해라 이렇게 설정해라 따라만 하니까 이해도 명확히 안됐던 것 같다.

완벽하게 개념 + 세팅 잡고 가자!!!

<br>

## ESLint

자바스크립트 문법에서 에러를 표시해줍니다.

코드 퀄리티를 보장하도록 도와줍니다.

<br>

## Prettier

코드 스타일을 설정해주는 대로 자동 포맷팅 해줍니다.

코드 스타일을 깔끔하게 혹은 통일되도록 도와줍니다.

대부분 eslint만 사용하지 않고 prettier 를 함께 사용합니다.

<br>

## ESLint 세팅하기

해당 저장소 root 로 들어가서 eslint 설치하기

```jsx
npm install -D eslint
```

VSCode 마켓플레이스에서 eslint extension 설치하기

- ESLint Extension은 해당 워크스페이스(프로젝트)에서 eslint가 설치되어 있는지 확인 후, 없으면 글로벌 eslint를 참조한다고 나와있습니다.
- 필요에 따라 .eslintrc 파일이 필요할 수도 있다고 설명되어 있습니다.

즉 eslint가 프로젝트 코드 단에서 사용하는 것이 아니라, 해당 VSCode라는 에디터에 적용해서 사용하는 것!

eslint를 사용하려면 eslint extension과 eslint library 두개 모두 설치가 되어있어야 한다. 꼭!

두가지를 모두 설치해주었다면, .eslintrc 파일을 통해서 lint rule을 세팅해주어야 합니다.

<br>

---

<br>

@Reference https://helloinyong.tistory.com/325

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

---

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

## .eslintrc.json 룰 세팅하기

🔗 공식문서 : https://eslint.org/docs/latest/use/configure/configuration-files

```json
{
    "root": true,
    "plugins": [
        "@typescript-eslint"
    ],
    "extends": [
        "eslint:recommended",
        "plugin:@typescript-eslint/recommended"
    ],
    "parser": "@typescript-eslint/parser",
    "rules": {
        "@typescript-eslint/strict-boolean-expressions": [
            2,
            {
                "allowString" : false,
                "allowNumber" : false
            }
        ]
    }
```

- root : default 는 true, 만약 true 가 아닐경우 eslintrc 파일을 찾을 때, 해당 프로젝트 디렉토리 뿐만 아니라 내 PC root 파일 디렉토리까지 eslint를 찾는다. ⇒ true로 둬라

- plugins
  아래 종류 외에도 훨씬 많다. npm / yarn 으로 설치하면 됩니다.

  - **eslint-config-airbnb-base: 에어비엔비 린트 플러그인**
  - **eslint-config-next: Next.js 전용 린트 플러그인**
  - **eslint-plugin-react: 리액트 전용 플러그인**
  - **eslint-plugin-prettier: 린트 위에 사용할 프리티어 플러그인**
  - **eslint-config-prettier: 요건 린트 설정과 중복되는 부분이 있으면 프리티어 룰에서 제외하는 플러그인**
  - **@typescript-eslint/eslint-plugin: : 타입스크립트 전용 린트**

- extends : eslint rule 설정이 저장되어 있는 외부 file을 extends 하는 부분이다.

- rules : 직접 lint rule을 적용하는 부분입니다. extends에서 자동으로 설정된 rules 중에 특정 룰을 끄거나 error를 warning 으로 나오도록 변경하는 등 설정을 바꿀 수 있다.

<br>

## VSCode :: format on save 체크해주기

MacOS 의 경우

**`command + ,`** 단축키로 설정 열고, Format on Save 검색하여 체크해주면 됩니다.

<br>

---

<br>

## Prettier 설치하기

패키지 설치하기

```bash
npm install prettier --save-dev
```

<br>

## VSCode 마켓플레이스에서 prettier extension 설치하기

- eslint 와 마찬가지로 vscode 에서 설치해주기

<br>

## eslint 와 prettier를 함게 사용하기 위해서 추가적인 설치

```jsx
npm install eslint-config-prettier --save-dev
npm install eslint-plugin-prettier --save-dev
```

그리고나서 eslint의 설정 파일의 extends에 prettier plugin을 추가해야합니다.

<br>

**`.eslintrc.json`**

예시)

```json
...
"extends": [
        "airbnb-base",
        "plugin:prettier/recommended"
    ],
...
```

<br>

`**.prettierrc.json**`

프로젝트 root 경로에 prettierrc.json 생성해서 prettier의 규칙 커스텀하기

공식문서 : https://prettier.io/docs/en/configuration.html

예시)

```json
{
  "printWidth": 120,
  "tabWidth": 4,
  "singleQuote": true,
  "trailingComma": "all",
  "semi": false
}
```

---

<br>

@Reference https://helloinyong.tistory.com/325

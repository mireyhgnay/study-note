# <div align="center">📖 [CI/CD] npm install 과 npm ci</div>

두가지 명령어의 차이점을 알아보려고 합니다.

두 명령어 모두 의존성 목록을 설치하는 것이지만 각자 목적이 다릅니다.

<br>

## **`npm install`**

npm install 명령어는 `package.json` 과 `package-lock.json` 두 가지 파일과 밀접한 관계가 있습니다.

`package.json` 은 우리가 설치하고자 하는 모듈에 대한 의존성 목록이 존재합니다.

각자 서로 다른 node_modules 를 생성할 수 있다는 것입니다.

```jsx
"react": "^17.0.2",
```

<br>

예를들어, 하나의 프로젝트에 여러명의 개발자가 협업을 할 경우

각자의 로컬 환경에서 node, npm 버전등이 서로 다를 수있는데

이런 상황에서 각자 npm i 을 실행한다면, 서로 다른 버전을 가지는 모듈을 가지는 경우가 생길 수 있습니다.

<br>

그래서 package-lock.json 이 존재합니다.

package-lock.json 은 정확한 버전이 명시되어있습니다.

```jsx
react@^17.0.2:
  version "17.0.2"
```

결국 모두 같은 버전의 의존성을 가지게 되므로 package-lock.json 을 같이 커밋해서 사용하고 있는 것입니다.

<br>

### npm install 의 본질은 한마디로, package.json 을 읽어 의존성 목록을 만들고 package-lock.json을 통해 설치할 의존성의 버전을 알려주는 것이다!

<br>

npm install 모듈 을 실행하면 package.json에 의존성 목록에 추가될 것이고,

package-lock.json 도 업데이트 될 것입니다.

이것이 의미하는 것은 npm install 는 package.json, package-lock.json 에 모두 쓰기 권한을 가집니다.

<br>
<br>

## **`npm ci`**

반면에 npm ci 는 쓰기 권한이 없습니다.

- package-lock.json 이 무조건 존재해야하만 하고, 만약 없으면 에러를 낸다.
- package-lock.json 파일을 기반으로 의존성을 설치하고, package.json 은 버전 매칭 밸리데이션 용도로 사용한다.
- npm ci 실행하면 먼저 node_modules 삭제한 후, 의존성을 한번에 설치한다.

<br>

npm install과는 달리 파일에 손대는 일이 없어 쓰기 권한이 없다고 하는 것입니다.

오직 package-lock.json 을 읽고 의존성 목록을 설치하게 됩니다.

<br>

그리고 npm install에 비해 npm ci 는 특정 케이스에서는 훨씬 빠릅니다.

이미 버전이 정확하게 명시된 package-lock.json 을 기반으로 설치하기 떄문에 설치할 버전을 알아내야하는 npm install 보다는 빠를 수 밖에 없습니다.

<br>

반대로 npm ci 는 node_modules를 우선 삭제하는 과정이 필요하기 때문에 삭제해야하는 연산이 길어진다면 npm i 보다는 느려질 수 있습니다.

# <div align="center">📌 React 개발 환경 설정 : Create React App 프로젝트 만들기</div>

## CRA

많은 개발자들이 공통적으로 사용하는 툴들과 기본적인 셋팅들을 한번에 할 수 있는 것이 CRA 이다.

이것만 셋팅해도 babel, webpack 와 같은 애들도 다 설치가 되어있다.

[🔗 Getting Started | Create React App](https://create-react-app.dev/docs/getting-started/)

<br>

## CRA Install

```bash
cd [작업 폴더 경로로 이동]
# npx create-react-app [프로젝트 이름]
npx create-react-app react-app
```

👉 Happy hacking! 뜨면 설치 성공

<br>

설치가 완료된 후, 여러 실행 종류들이 나온다.

- **`yarn start`** : Starts the development server
  - 개발용 모드로 실행한다
- **`yarn build`** : Bundles the app into static files for production
  - 배포, 빌드할 때 실행한다
- **`yarn test`** : Starts the test runner
  - 우리가 작성한 유닛 코드들이나 테스트 코드들이 실행 된다
- **`yarn eject`** : Removes this tool and coies build dependencies, configuration files and scripts into the app directory. If you do this, you can’t go back!
  - 기본적으로 설정 되어 있는 코드들을 다 꺼내서 설정을 바꿔줄 수 있다. ex. dependencies, configuration files, scripts 등
  - 단, 한번 eject를 실행해서 코드들을 꺼내면 다시 복구할 수 없다.
  - 그래서 정말 필요한 경우에만 eject를 실행해서 바꿔주면 된다.
  - 개인프로젝트를 할 떄는 거의 할 일이없다.

<br>

## npm start

```bash
cd react-app
npm start
```

app 실행되면 성공🥳

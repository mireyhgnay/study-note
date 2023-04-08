# <div align="center">🚨 Netlify 배포 - 빌드 에러 해결방법</div>

나의 경우 Netlify 배포시 계속 빌드 에러가 났었다..^^;

<br>

**에러 내용**

```bash
Deploy failed - Failed during stage 'building site': Build script returned non-zero exit code: 2
```

<br>

이유는 처음에 배포 셋팅할 때 Base directory을 프로젝트의 최상단 루트로 설정을 했어야 했는데

빈채로 놔뒀기 때문에 에러가 났던 것이였다.

<br>

나의 폴더 트리

```
ㄴ react-study
    ㄴ css-all (여기서 cra 설치)
```

<br>

css-all 이라는 폴더 안에서 CRA를 설치해서 프로젝트를 생성했는데
Base directory 을 빈칸으로 두어서 react-study 에서 빌드되도록 해서 에러가 났던 것이였다!!

- base directory: css-all
- build command: npm run build
- publish directory: css-all/build

이렇게 적어줬어야 했다!

react-study 에서 리액트 앱을 만들었다면, 빈칸으로 둬도 되지만 프로젝트의 루트를 꼭 적어줘야한다.

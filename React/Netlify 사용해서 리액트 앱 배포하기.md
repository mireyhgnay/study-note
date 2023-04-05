# <div align="center">Netlify 사용해서 리액트 앱 배포하기</div>

<br>

## React 배포하기

주로 Vercel 과 Netlify를 사용하여 배포한다.

<br>

## Netlify 사용하여 배포하기

[React 공식문서 - Deployment 보러가기 👉](https://create-react-app.dev/docs/deployment/)

[React 공식문서 - Netlify 보러가기 👉](https://create-react-app.dev/docs/deployment/#netlify)

<br>

### 1. To do a manual deploy to Netlify’s CDN:

> 수동으로 직접 설치하여 배포하는 방법

ex. 사이드프로젝트 하나를 딱 만들어서 한번에 배포하는 경우

```bash
npm install netlify-cli -g
netlify deploy
```

<br>

### 2. To setup continuous delivery:

> 깃허브와 연결하여 배포하기

ex. 지속적으로 배포하고 작업 할 것이라면 연결하여 배포하기

```
📌 With this setup Netlify will build and deploy when you push to git or open a pull request:

= 셋업만 해두면  메인브랜치 master(main)이나 풀리퀘를 만들거나 푸시를 하기만 해도 자동으로 배포가 된다
```

### 3. 깃허브와 연결하여 배포하기

1. [Start a new netlify project](https://app.netlify.com/signup) 깃허브 계정으로 로그인
2. 깃허브 계정과 netlify 연동되어 대시보드가 생성되어있음  
   [🔗 Netlify DashBoard](https://app.netlify.com/teams/mireyhgnay/overview)
3. 배포할 레포 선택하여 deploy 해주면 된다.

# <div align="center">🔥 React : Netlify로 배포하기</div>

<br>

[🔗 CRA Deployment Netlify 공식문서](https://create-react-app.dev/docs/deployment/#netlify)

[🔗 참고하기 좋은 블로그](https://velog.io/@ksmfou98/React-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-Netlify%EC%97%90-%EB%B0%B0%ED%8F%AC%ED%95%98%EA%B8%B0)

<br>

# 🔥 Netlify 사용하여 리액트 앱 배포해보기

공식 문서 내용을 확인해보자면,

### 1. **To do a manual deploy to Netlify’s CDN:**

> 수동으로 직접 설치하여 배포하는 방법입니다.  
> ex. 사이드프로젝트 하나를 딱 만들어서 한번에 배포하는 경우

```bash
npm install netlify-cli -g
netlify deploy
```

<br>

### 2. **To setup continuous delivery:**

> 깃허브와 연결하여 배포하는 방법입니다.  
> ex. 지속적으로 배포하고 작업 할 경우 깃헙 저장소 연결하여 배포하기

```
📌 With this setup Netlify will build and deploy when you push to git or open a pull request:

= 셋업만 해두면 메인브랜치 master(main)이나 풀리퀘를 만들거나 푸시를 하기만 해도 자동으로 배포가 된다
```

<br>
<br>

# 🔥 깃허브와 연결하여 배포하기

**✅ 배포 전 체크해봐야 할 것**

- [ ] Netlify의 계정이 있어야 한다.
- [ ] 배포하고자 하는 프로젝트가 Github Repository 에 올라와 있어야 한다.

<br>

1. [Netlify](https://www.netlify.com/) 사이트 로그인하기
2. New site from Git 버튼 클릭
3. Github 버튼 클릭하여 개인 계정과 연동
4. 배포할 프로젝트의 Repo 선택
5. 배포 셋팅 후 Deploy site 버튼 클릭

   - Owner : 본인
   - Branch to deploy : 배포할 깃허브 Branch 선택
   - Base directory : (repository가 프론트 하나로 되어있는 레포일 경우) 배포 할 Root 경로 작성
     - 결론은 배포해야 될 react 프로젝트의 루트 경로를 입력하면 된다.
   - Build command : 빌드 명령어 입력 (npm run build)
   - Publish directory : 빌드가 완료된 후 생성된 폴더 이름 (build)
     - Base directory 루트의 폴더명이 있다면 project-name/build 이런식으로 작성될 것이다.

6. 2분정도 지나면 배포 완료!
7. Published 가 나오면 위에 화면 클릭시 배포된 사이트 등장! 끝!!

**추가 선택 사항**

추가로 홈페이지의 도메인 주소를 변경하고 싶을 경우,

Site settings > General > Change site name 버튼 클릭하여 수정할 수 있습니다.

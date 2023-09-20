# <div align="center">📖 MAS와 BFF(Backend For Frontend)</div>

<br>

## MAS란,

[http://clipsoft.co.kr/wp/blog/마이크로서비스-아키텍처msa-개념/](http://clipsoft.co.kr/wp/blog/%EB%A7%88%EC%9D%B4%ED%81%AC%EB%A1%9C%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98msa-%EA%B0%9C%EB%85%90/)

MSA란 마이크로 서비스 아키텍처(Micro Service Architecture)의 약자로 단일 프로그램을 각 컴포넌트 별로 나누어 작은 서비스의 조합으로 구축하는 방법입니다.

<br>

### **모노리틱 아키텍처**

기존에 우리가 사용하던 개발 방식은 **모노리틱 아키텍처** 스타일이라고 합니다.

![스크린샷 2023-09-20 오후 9 31 40](https://github.com/mireyhgnay/study-note/assets/111990266/037708df-803d-419d-b399-a9435dcd2fc1)

<br>

- 전체 애플리케이션이 하나로 되어있어서 보통 동일한 개발 툴을 사용
- 배포 및 테스트도 하나의 애플리케이션만 수행
- 그래서 개발 및 환경설정이 간단하다.

하지만! 점점 시스템이 커지면

- 빌드/테스트 시간이 길어집니다.
- 선택적 확장이 불가능해집니다.
- 하나의 서비스가 모~든 서비스에 영향을 줍니다.

<br>

### MAS

![스크린샷 2023-09-20 오후 9 31 45](https://github.com/mireyhgnay/study-note/assets/111990266/8a46a8a5-d8ad-4073-ab37-242eafd1c1a0)

- 각 컴포넌트는 서비스 형태로 구현되고 API를 이용하여 타 서비스와 통신
- 각 서비스는 독립된 서버로 타 컴포넌트와 의존성이 없기 때문에 독립된 배포
- 독립된 서비스로 개발되어있기 때문에 부분적인 확장이 가능

예전 방식보다 훨~ 좋다는게 글만봐도 느껴지지만..? 단점으로는,

- MSA의 경우 서비스간 호출을 API통신을 이용하기 때문에 속도가 느리다.
- 통신에 사용하기 위해 값을 데이터 모델로 변환시켜주는 오버헤드가 발생하기도 합니다.

<br>

### 정리하자면!

MSA는 복잡한 웹 시스템에 맞춰 개발된 API기반의 서비스 지향적 아키텍처 스타일입니다.

MSA가 유행을 하고 있지만 꼭 정답은 아니고, 업무나 비즈니스 특징에 따라 적절한 아키텍처가 선택됩니다.

<br>
<br>

## BFF

https://fe-developers.kakaoent.com/2022/220310-kakaopage-bff/

<br>

### 그림으로 한방에 이해해보기

`일반적인 API 구조`

![스크린샷 2023-09-20 오후 9 40 38](https://github.com/mireyhgnay/study-note/assets/111990266/1e21c68d-8048-45d9-ba5b-2ad496e0ec6e)

<br>

`BFF 구조`

![스크린샷 2023-09-20 오후 9 40 43](https://github.com/mireyhgnay/study-note/assets/111990266/706e0eb5-418e-4c2d-a048-06dc37abe509)

<br>

**`Backend For Frontend`**라는 말 그대로 프론트엔드를 위한 중간 서버를 구현하는 것이라고 생각하면 됩니다.

- MSA 환경에서 API 엔드포인트가 분리될 때 팔로업
- 브라우저의 숙명인 CORS 처리
- API 입장에서 여러 플랫폼과 스펙을 맞출 때의 커뮤니케이션 비용 감소
- 플랫폼별로 다를 수 밖에 없는 인증 방식 처리
- 클라이언트의 꿈인 ‘화면에 필요한 데이터만 받는’ partial response

# <div align="center">🖥️ Service Discovery</div>

<br>

https://catsbi.oopy.io/c95e714b-0d28-49d0-aff5-10acd5d0dce5

<br>

서로 다른 서비스들의 IP와 Port 정보에 대해서 저장하고 관리할 필요가 있는데 이것을 Service Discovery 라고 한다.

<br>

### 등장 배경

서비스 인스턴스의 수가 동적으로 가감하는 상황에서 가감되는 서비스의 IP를 감지하고

서비스의 헬스체크를 하여 이용이 불가능한 서비스를 삭제하는 등 서비스 인스턴스를 발견하고 관리하는 역할이 필요해졌다.

대표적으로 Eureka 서비스는 MSA의 핵심요소인 서비스 디스커버리를 지원하는 서비스이다.

<br>

### 구현 두 가지 방법

- Client-Side Discovery Pattern
- Server-Side Discovery Pattern

<br>

### Client-Side Discovery Pattern

클라이언트에서 서버(Service Registry)에서 서비스의 위치를 찾아 호출하는 방식이다.

- 비교적 사용이 간단하다
- 클라이언트는 사용 가능한 서비스 주소를 알고 있기 때문에 서비스에 맞게 로드 밸런싱 방법을 선택할 수 있다
- 클라이언트와 서버간에 종속성

<img width="446" alt="sd1" src="https://github.com/mireyhgnay/study-note/assets/111990266/49aab0f1-0997-4d2d-9740-6b0cd4608a9b">

<br>

### Server-Side Discovery Pattern

호출되는 서비스 앞에 로드 밸런서를 넣는 방식이다.

- 로드 밸런서가 서버(Service Registry)로부터 등록된 서비스의 위치를 전달한다
- 클라이언트는 로드밸런서에 요청만 하면 되기에 서버에 맞는 검색 로직을 구현할 필욘 없다.

<img width="470" alt="sd2" src="https://github.com/mireyhgnay/study-note/assets/111990266/b2206be1-8533-4945-b1ae-86dc02a0a6d5">

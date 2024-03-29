# <div align="center">👩🏻‍💻 Git Commit Convention</div>

버전 관리 시스템에서 여러명의 개발자와 함께 코드를 구현하고 여러 작업물들을 관리 할 떄 각 팀원들 끼리 커밋 내역을 명시적으로 확인할 수 있고 쉽게 관리 될 수 있도록 지켜지는 메세지 규약이다.   


규칙은 [여기](https://www.conventionalcommits.org/en/v1.0.0/)서 참고할 수 있다.    

위 사이트에서는 커밋 메세지를 구성하는 방법을 아래와 같이 요약하고 있다.
```
<type>[optional scope]: <description> | header
[optional body]                       | body 
[optional footer]                  | footer
```
- 제목은 어떤 것을 했는지 명확한 단어가 들어가야 하고, 너무 길게 작성하지 않는다.
- 내용은 선택사항이나 자세한 커밋 메세지를 작성하고자 할 때, 제목에 이어 부가적인 설명을 붙인다. 이 커밋을 한 이유와 변경 내용 등을 작성한다.
- 푸터는 선택사항이고 관련 이슈 번호를 참조시킬 때 주로 사용한다.     

### ⭐️ type
* feat : 새로운 기능 추가    
* fix : 버그 수정    
* docs : 문서 작성    
* style : 코드 포매팅, 스펠링 오류, 세미콜론 추가 등    
* refactor : 리팩토링    
* test : 테스트 관련 코드      
* build : 빌드 관련 파일 수정      
* ci : CI 설정 파일 수정    
* perf : 성능 개선    

### scope
> 변경된 위치를 작성 하는 구간
* 추가된 클래스 명이나 추가 및 변경된 메소드 명을 적는 공간
* scope은 생략 가능

### description
> 변경 내용을 간략하게 작성하는 구간
* 명령문, 현재 시제로 작성
* 대문자를 사용하지 않음
* 마침표로 끝내지 않음

### 메시지 내용 (body)
* 명령문, 현재 시제 작성
* 변경한 이유와 변경 전과의 차이점을 설명한다.

### 메시지 하단 (Message Footer)
* 주요 변경 내역들 (Breaking Changes)
* 모든 주요 변경 내역들은 다음과 함께 하단에 언급


## 작성방법
커밋 제목 밑에 추가 부연설명을 달기 위해서는, **제목에 엔터(줄바꿈) 2번** 한 이후 설명을 적으면 된다
```bash
$ git commit -m "커밋 제목

부가 설명"
```    

**Terminal**     
<img width="729" alt="터미널" src="https://user-images.githubusercontent.com/111990266/210247826-809c7cf9-c2f0-4adf-96dc-99f1c7ab944a.png">


**Commit 내역**    
<img width="301" alt="커밋 내역" src="https://user-images.githubusercontent.com/111990266/210247783-712eddc9-fa9e-4d19-bb8e-55cabcea8809.png">

<br>

### (20230117 추가 기록) 내 커밋 컨벤션 재정립!
```
Docs : README 문서 수정
Style : 세미콜론 추가
```
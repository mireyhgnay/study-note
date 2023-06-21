# <div align="center">👩🏻‍💻 git cherry-pick</div>

<br>

## git cherry-pick 이란?

필요한 커밋만 골라서 가져오는 명령어이다.

쉽게 말해 다른 브랜치에 있는 commit 들 중에서 원하는, 필요한 커밋을 지금 현재 작업 브랜치로 가져와 커밋하는 것이다.

브랜치명을 바꾸거나 옮기는 것이 아니라,

동일한 commit 을 다른 branch 에 복사하는 걸로 이해하면 된다. (실제로 커밋이 추가됨)

<br>

## 사용하는 경우

커밋이 중복되거나 그 외 여러가지 문제가 발생할 수 있기 때문에 꼭 필요한 상황에서만 사용하는 것을 권장한다.

- 팀으로 협업할 때
  - 다른 동료가 만들고 있는 기능이 필요한 순간이 있다.
    동료가 맡은 모든 작업을 merge 할때까지 시간이 걸린다면 동료가 만들었다는 기능이 들어있는 commit 만 골라서 가져올 때 사용한다.
- 버그를 수정할 때
  - 새로운 기능을 개발하는 동안 기존에 있던 기능에서 버그가 발견되었을 때,
    개발자는 이 버그를 패치하기 위해 명시적 커밋을 만들고 해당 커밋들만 골라서 배포할 수 있다.
- 반영되지 않은 손실된 커밋 복원
  - 실수로 풀리퀘를 머지하기전에 닫아버렸을 때, cherry-pick 을 사용해서 해당 커밋을 가져옴으로써 살릴 수 있다.

<br>

## 체리픽 충돌나는 경우

체리픽 을 하고 충돌이 나는 경우도 있는데 그럴 경우,

**충돌 해결 후, 체리픽을 계속 진행하는 방법**

1. 충돌난 코드를 수정하고,
2. git add {충돌난 파일 경로} 로 충돌 해결한 코드를 추가
3. git cherry-pick --continue 로 cherry-pick을 다시 진행한다.

<br>

**체리픽 중단하기**

1. git cherry-pick --abort로 cherry-pick을 중단하고 이전 상태로 돌아간다.

<br>

## 체리픽을 사용한 나의 경험~!

신규 저장소에 모노레포 구축하여 기존 저장소에서 모노레포로 이관 작업 중,

dev 브랜치에서 `feature/branch-name` 형식으로 브랜치를 생성해서 작업하여 원격에 푸시까지 완료 한 상태였는데

팀 내 깃플로우 방식이 프로젝트 작업 시 `release/branch-name` 명칭으로 생성하여 작업하기로 하였다.

그래서 기존 `feature/branch-name` 의 커밋 내용을 `release/branch-name` 으로 복사해야 했다.

feature/branch-name 이전 작업 브랜치는 그대로 두고,

release/branch-name 에 두고 커밋 내역 3개를 모두 cherry-pick 하여 커밋내역을 그대로 복사해서

작업 브랜치를 release/branch-name 으로 변경하였고,

기존 feature/branch-name 은 로컬/원격 에서 모두 제거해주었다.

<br>

---

<br>

@Reference

https://brownbears.tistory.com/606

https://mine-it-record.tistory.com/650

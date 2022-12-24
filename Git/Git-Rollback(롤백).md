# <div align="center">Rollback (Reset VS Revert)</div>
나는 아직 롤백을 경험해본 적은 없지만… 알아두어야한다!!
> 프로젝트를 진행하는 중에 예기치 못한 변수 발생 시, 이력 되돌리기를 할 수 있는 상황 대비하여 공부해두어야 한다.    
하지만 롤백하는 경우는 거의 없어야한다~~    

## Reset VS Revert
둘 다 원하는 이전 커밋까지 롤백시키는 명령어로 동일하지만, 차이점이 있다.
- `reset`은 커밋 이력(History)를 남기지 않고 특정 커밋까지 되돌린다.
- `revert`는 커밋 이력을 남기고 특정 커밋까지 되돌린다.

> <Reset의 문제점>    
커밋 히스토리까지 깔끔하게 지우고 롤백시키는 기능이기에 편리하게 사용할 수 있지만, 1인 개발이 아니라 여러명이 협업을 할 경우 사용하기 전에 아래와 같은 사항을 고려해야한다.     


## Reset
```bash
# {헤시값} 바로 전(이전)까지 되돌린다.
$ git reset --hard {헤시값}

# 현재 HEAD에서 3개의 커밋을 롤백한다. (3개의 커밋을 롤백)
$ git reset --hard HEAD~3..

# 현재 HEAD에서 1개의 커밋(마지막 커밋)을 롤백한다.
$ git reset --hard HEAD^

# 위와 동일한 의미이며 N번까지 되돌릴 경우 ^를 N번 반복한다.
$ git reset --hard HEAD^^^

# 원격 저장소에 push는 다음과 같이 -f 또는 -force 옵션을 사용해야 한다.
$ git push -f origin master
```

## Revert
이전 커밋 히스토리로 돌아가자~

```bash
# 마지막 커밋내역부터 3개
$ git revert -no--commit HEAD~3..
$ git commit -m "Revert Commit 3,2,1"
$ git push origin master
```

**Revert 를 이용한 병합 취소**     
완전히 병합된 commit이 있는 경우(merge) revert를 이용해 쉽게 병합을 취소할 수 있다.     
이때 --mainline 옵션으로 어느 브랜치를 남길지 결정할 수 있다.     


```bash
$ git log --oneline --graph
```
로 그래프 확인하여 어느 커밋이 merge 커밋인지 알 수 있게 해준다.    

```bash
# git revert --mainline [남길 line] [병합 commit]
git revert --mainline 1 cb70c2d
```

![gitgraph](https://user-images.githubusercontent.com/111990266/209423434-60fd6cc9-8776-451e-9dd3-ec24f8ed13ef.png)

--graph 에서 왼쪽 직선 그래프가 1번 라인, 오른쪽 그래프가 2번 라인이 됩니다.    
revert 하면서 1번 라인을 남길지 2번 라인을 남길지 결정하면 됩니다.
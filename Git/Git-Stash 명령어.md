# <div align="center">👩🏻‍💻 git stash(임시 저장)</div>
아직 마무리하지 않은 작업을 스택에 잠시 저장할 수 있도록 하는 명령어이다.    
commit 하기에는 애매하고, 그렇다고 작업하던 내용을 날릴수도 없고 할때,    
`stash` 기능을 사용하면된다!    
이를 통해 아직 완료하지 않은 일을 commit하지 않고 나중에 다시 꺼내와 마무리할 수 있다.

## stash 간단 명령어들
지금 작업하던 내용을 잠깐 stash 에 저장한다.    
이때, tracking 되고 있는 파일만 stash 에 저장된다.
```bash
git stash
```    

stash 에 저장된 리스트를 확인 할 수있다.    
```bash
git stash list
```

stash 에 있던 내용을 가져온다
```bash
git stash apply
```

stash 에 있는 내용을 지운다
```bash
git stash drop
```

stash 에 있던 내용을 가져오고, 지운다
```bash
git stash pop
```

---
@reference https://gmlwjd9405.github.io/2018/05/18/git-stash.html
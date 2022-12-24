# <div align="center">👩🏻‍💻 자주 사용하는 Git 명령어</div>

## 로컬(Local) & 원격(Remote) 브랜치 삭제하기
삭제 해야할 브랜치 말고 **다른 브랜치에다가 checkout 해두고** 삭제해야한다

* 로컬 브랜치 삭제
    ```bash
    $ git branch -d BranchName
    # 강제 삭제
    $ git branch -D BranchName
    ```

* 원격 브랜치 삭제 
    ```bash
    $ git push origin --delete BranchName
    ```

## 로컬(Local) & 원격(Remote) 브랜치 이름 변경하기
```bash
# 변경할 branch로 checkout 
$ git checkout <변경할 branch name>

# 새로운 이름으로 local branch의 이름을 바꿈
$ git branch -m <새로운 branch name>

# 새로운 이름으로 된 branch 를 remote에 push 
$ git push origin -u <새로운 branch name>

# 변경 전 branch 를 remote에서 삭제
$ git push origin --delete <이전 branch name>
```    

## Branch 확인하기
현재 위치하고 있는 브랜치가 무엇인지 확인할 수 있다
```bash
$ git branch
    * main 
    feature/branch-name
```

## Checkout
내가 사용할 브랜치를 지정하는 것을 의미한다
* `checkout` : 기존에 있던 브랜치를 선택하는 것
* `checkout -b` : 브랜치 생성 + 지정    

## Pull
git pull 명령은 원격 저장소에 있는 프로젝트 내용을 가져오는 역할을 한다.    
단, git clone 과는 다르다.    
* `git clone` :     
    먼저, git clone명령을 사용하면 로컬 저장소의 내용이 원격 저장소의 내용과 일치해진다.     
    즉, git clone은 프로젝트에 처음 투입될 때 사용되어야 하는 명령인 것이다.
* `git pull` :    
    반면 git pull명령은 원격 저장소의 내용을 가져와서 현재 브랜치와 병합(merge)까지 해주기 때문에 기존에 작업했던 내용은 유지하면서 최신 코드로 업데이트할 수 있는 것이다.


## Status
현재 레포 상태에 대해서 아래에 나타난 것 처럼 현재 브랜치 / 업데이트 된 내용 등을 알려준다
```bash
현재 브랜치 main
브랜치가 'origin/main'에 맞게 업데이트된 상태입니다.

커밋하도록 정하지 않은 변경 사항:
	삭제함:        "Git.md"
	수정함:        README.md

추적하지 않는 파일:
	"Git.md"

이하생략...
```


## add & commit & push
작업브랜치에서 작업 후, Add + Commit + Push! 해서 원격저장소에 업로드한다
```bash
# 작업 내용 전체 포함
$ git add .
# 커밋메세지 입력하여 커밋
$ git commit -m "commit message"
# 작업 브랜치로 푸시(원격저장소 업데이트)
$ git push origin BranchName
```

## 세트로 붙어댕기는 애들👇
* **처음으로 저장소 클론받았을 때**
    ```bash
    $ cd documents # 경로 이동
    $ git clone <repository url> # 레포 클론받아오기
    $ git branch # 현재 브랜치 확인
        * main
    $ git checkout -b <NewBranchName> # 새브랜치  생성 및 지정
    $ git branch 
        main
        * NewBranchName
    ```

* **작업 한 후 원격저장소로 푸시하기**
    ```bash
    $ git branch
        main
        * NewBranchName
    $ git status # 상태 및 변경사항 확인하기
    $ git add . # 변경내용 모두 선택
    $ git commit -m "코드리뷰 반영"
    $ git push origin NewBranchName 
    ```

* **기존에 있던 브랜치 땡겨서 이어 작업하기(최신화 후 작업)**
    ```bash
    $ git branch
        * main
        NewBranchName
        AnotherBranchName
    $ git checkout <AnotherBranchName> # 브랜치 변경
    $ git branch
        main
        NewBranchName
        * AnotherBranchName
    $ git pull # AnotherBranchName 내용 땡겨오기
    
    ... AnotherBranchName 에서 작업 완료!

    $ git add .
    $ git commit -m "추가 작업"
    $ git push origin AnotherBranchName
   ```
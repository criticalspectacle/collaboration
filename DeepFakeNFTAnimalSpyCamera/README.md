## Quick Start
DFNASPC.md 를 열어 공동 집필하세요

## 공동 글쓰기
1. git branch로 현재 내가 있는 branch가 main 인걸 확인하기 (아니면 checkout 해서 main으로)
2. 리모트를 fetch 하고 merge 할것 (git fetch / git merge origin/main)
3. 자기 branch 만들기
4. 자기 branch 로 checkout
5. DFNASPC.md를 열어 내용 추가하기
6. git add / git commit
7. 다시한번 리모트를 fetch & merge  (혹시 바뀐 내용이 있을까봐) (git fetch / git merge origin/main)
8. 내 branch를 push (git push origin 내브랜치이름)

* 다음에 작업할때는 자기 브랜치가 만들어진 상태일것이다. 
* 그때는 자기브랜치로 checkout 에서 (git fetch / git merge origin/main) 하고 시작하고 push 하기전에 또 한다.

## 머징 하기
머징은 하루가 끝날때 한명이 하게된다. (순서를 돌아가면서)

1. branch를 main으로 바꾼다.
2. 이상적으로는 가장 마지막으로 바뀐 branch 의 commit을 보고 그것만 merge 한다. 
3. 어떻게 하면 잘 merge할지 찾아본다.
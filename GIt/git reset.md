# git reset
커밋 기록 삭제(이전 상태로 되돌림)하고 싶을 때는 'git reset'과 'git push --force' 사용한다.

<br>

## 방법

1 돌아가려는 지점 찾기

    $ git log

2 리셋하기

    $ git reset --hard '돌아가려는 지점의 commit id'

3 force로 원격저장소 강제 푸쉬

    $ git push -f origin master

<br>

## 주의사항!
지정된 commit 이후의 기록과 파일들을 모두 삭제된다.  
삭제된 파일은 복구가 안되니 웬만하면 안 쓰는게 좋다.  
<br>

git init 실수로 생긴 커밋 이력 지우려다 하루종일 만든 클론파일 날아갈 뻔했다... 다행히 reflog로 복구시킴ㅜ 웬만하면 쓰지않기😨

출처 : https://fierycoding.tistory.com/40
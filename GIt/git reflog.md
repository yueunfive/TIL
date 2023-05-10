# git reflog
git reset --hard로 지워진 커밋 복구할 때 사용한다.  
보관되어 있는 git 이력을 볼 수 있는 명령어.

## 방법
1. reflog 명령어 입력
```
$ git reflog
```
2. 아래와 같이 git 이력, 삭제된 commit id가 뜬다.
```
d2323a4 HEAD@{0}: header design
d42524e HEAD@{1}: git reset --hard 43fsfs14adwe16776f0d0f1ee2933ffeafa47dwdef390e5rw1 HEAD@{2}: 05/10
[...]
```
3. 이동하고자 하는 HEAD로 이동
```
$ git reset --hard HEAD@{2}
```
4. 파일 복구 확인 후 원격 저장소 푸쉬
```
$ git push origin main
```
<br>
출처 : https://88240.tistory.com/284
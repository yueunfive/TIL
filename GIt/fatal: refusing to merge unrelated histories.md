# Git 오류 ‘fatal: refusing to merge unrelated histories’ 

```jsx
git pull origin main // pull할 때 발생했음
...
- branch          main     -> FETCH_HEAD
- [new branch]    main     -> origin/main
fatal: refusing to merge unrelated histories
``` 
<br>

## 원인 
원격저장소와 로컬의 커밋이력이 다른데 로컬에서 pull/push를 할 경우, git에서는 이를 이질적인 두 프로젝트로 판단하여 병합을 거부한다.

<br>

## 해결방법  
  ```jsx
  git pull origin 브런치명 --allow-unrelated-histories
  ```

  ```jsx
  // 위 명령 실행하면 밑에 이런 식으로 나올거임
  Please enter a commit message to explain why this merge is necessary, 
  especially if it merges an updated upstream into a topic branch
  ...
  ```
1. i를 누른다 (commit message를 입력하기 위해)
2. merge에 대한 message를 입력한다.
3. esc를 누른다.
4. wq를 입력한다.
5. enter를 누른다.
  
    
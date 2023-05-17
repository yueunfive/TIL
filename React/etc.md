# etc(기타)

## Install Error(설치 오류)

```
Installing react, react-dom, and react-scripts with cra-template...

npm ERR! code EACCES
npm ERR! syscall mkdir
npm ERR! path /Users/yueun-oh/.npm/_cacache/content-v2/sha512/68/76
npm ERR! errno EACCES
npm ERR! 
npm ERR! Your cache folder contains root-owned files, due to a bug in
npm ERR! previous versions of npm which has since been addressed.
npm ERR! 
**npm ERR! To permanently fix this problem, please run: //해결방법
npm ERR!   sudo chown -R 501:20 "/Users/yueun-oh/.npm"**

npm ERR! A complete log of this run can be found in:
npm ERR!     /Users/yueun-oh/.npm/_logs/2023-05-16T01_18_01_445Z-debug-0.log

Aborting installation.
  npm install --no-audit --save --save-exact --loglevel error react react-dom react-scripts cra-template has failed.
```

```
$ sudo chown -R 501:20 "/Users/yueun-oh/.npm
..
password //맥북 비번 입력
..
$ npx create-react-app . // 설치('.'은 현재 디텍토리를 의미)
```

오류 발생시 바로 검색하지말고 일단 오류 메세지부터 정독하는 습관 들이자. 

<br>

## Distribute(배포)

```
$ npm run build
..
// build 폴더 -> index.html
$ npx serve -s build
```
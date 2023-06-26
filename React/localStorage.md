# localStorage

## 개념

- 유저의 브라우저에 정보를 저장할 수 있는 공간
- 사이트마다 5MB 정도의 문자 데이터를 저장
- object 자료랑 비슷하게 key/value 형태로 저장

```jsx
localStorage.setItem("데이터이름", "데이터"); // 추가
localStorage.getItem("데이터이름"); // 읽기
localStorage.removeItem("데이터이름"); // 삭제
```

<br>

## localStorage에 array/object 자료를 저장하기

- localStorage는 문자만 저장할 수 있는 공간
- array/object -> JSON 이렇게 변환해서 저장
- JSON은 따옴표친 array/object 자료로 문자 취급 받음

```jsx
// JSON.stringify() : array/object -> JSON 변환
// JSON.parse() : JSON -> array/object 변환

localStorage.setItem("obj", JSON.stringify({ name: "kim" }));
var a = localStorage.getItem("obj"); // "{"name":"kim"}"
var b = JSON.parse(a); // {name:'kim'}
```

<br>

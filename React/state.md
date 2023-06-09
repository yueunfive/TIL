# state

- 일반 변수 대신 state를 이용해서 자료를 저장할 수 있다.
- state 쓰는 이유
  - 변수 : 변수 내용이 바뀌면 그에 맞춰 html도 고쳐달라고 코드 짜야 함.
  - state : 변동사항이 생기면 html도 자동으로 재렌더링 해줌
  - 상품명, 글제목, 가격 이런것 처럼 자주 변할 것 같은 데이터들을 주로 state에 저장

```jsx
function App() {
  let [data1, data2] = useState("힘내세요");
  // data 1,2 모두 작명하면 됨
  // data1에는 useState에 쓴 자료가, data2에는 state 변경을 도와주는 함수기 들어감

  return (
    <h4>{data1}</h4> // 힘내세요
  );
}
```

출처 : 코딩애플 'React 리액트 기초부터 쇼핑몰 프로젝트까지!'

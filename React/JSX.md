# JSX

## 리액트에서 레이아웃 만들 때 쓰는 JSX 문법 3개

1. html에 class 넣을 때는 className

2. 변수를 html에 꽂아넣을 때는 {중괄호} 사용  
   a. 데이터바인딩 : 변수에 있던걸 html에 꽂아넣는 작업  
   b. id, className, href, src 등 온갖 html 속성에 사용 가능

3. html에 style 속성 넣기 : style = { {속성명 : '속성값' } }

```jsx
function App() {
  let post = "강남 우동 맛집";
  return (
    <div className="App">
      <div className="black-nav">
        <div style={{ color: "blue", fontSize: "30px" }}>블로그</div>
        <div>{post}</div>
      </div>
    </div>
  );
}
```

출처 : 코딩애플 'React 리액트 기초부터 쇼핑몰 프로젝트까지!'

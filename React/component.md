# Component(컴포넌트)

- 긴 HTML을 한 단어로 깔끔하게 치환해서 넣을 수 있는 문법
- 사용법(HTML 축약)

  1. function을 이용해서 함수를 하나 만들어주고 작명한다.

  2. 그 함수 안에 return () 안에 축약을 원하는 HTML을 담는다.

  3. 원하는 곳에서 <함수명></함수명>(or <함수명 /> 사용하면 아까 축약한 HTML이 등장한다.\

- 주의점

  1. component는 보통 영어대문자로 작명

  2. return () 안엔 html 태그들이 평행하게 여러개 들어갈 수 없다.

  3. function App(){} 내부에서 만들면 안된다.
     → function App(){}도 컴포넌트 생성문법이니까! component 안에 component 못 만듦..

```jsx
function App() {
  return (
    <div>
      (생략)
      <Modal></Modal> {/* == <Modal /> */}
    </div>
  );
}

function Modal() {
  return (
    <div className="modal">
      <h4>제목</h4>
      <p>날짜</p>
      <p>상세내용</p>
    </div>
  );
}

// 화살표 함수 사용 가능
const Modal = () => {
  return <div>...</div>;
};
```

출처 : 코딩애플 'React 리액트 기초부터 쇼핑몰 프로젝트까지!'

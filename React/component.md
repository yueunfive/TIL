# Component(컴포넌트)

React의 본질 : “사용자 정의 태그를 만드는 기술”

컴포넌트 = 사용자 정의 태그 = 복잡한 여러 태그들을 하나의 태그(독립된 부품)로 묶은 후 이름 붙힘

```javascript
// 사용자 정의 컴포넌트는 반드시 대문자로 시작해야 한다.
function Header() {
  return (
    <header>
      <h1>
        <a href="">React</a>
      </h1>
    </header>
  );
}

function Nav() {
  return (
    <nav>
      <ol>
        <li>
          <a href="">html</a>
        </li>
        <li>
          <a href="">css</a>
        </li>
        <li>
          <a href="">js</a>
        </li>
      </ol>
    </nav>
  );
}

function Article() {
  return (
    <article>
      <h2>Hello, React!</h2>
      Nice to meet you🙂
    </article>
  );
}

function App() {
  return (
    <div>
      <Header></Header>
      <Nav></Nav>
      <Article></Article>
    </div>
  );
}

// 컴포넌트명으로 코드의 취지를 쉽게 알 수 있다.
// 한 번에 코드 수정이 가능해져 유지보수가 편리하다.
```

<br>

## Component

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

<br>

## map

- 반복되는 컴포넌트를 렌더링하기 위하여 자바스크립트 배열의 내장 함수 (반복문)
- JSX 안에서 html을 반복생성하고 싶을 때, 많은 div들을 반복문으로 줄이고 싶을 때 사용
- 기능 1 : array에 들어있는 자료갯수만큼 그 안에 있는 코드를 반복실행
- 기능 2 : 콜백함수에 안에 작명한 파라미터(a)가 array 안에 있던 모든 자료를 하나씩 출력
  - 파라미터 2개까지 작명 가능 : map(function(a, i){})
  - 첫째 파라미터 a : array안에 있던 자료
  - 둘째 파라미터 i : 0부터 1씩 증가하는 정수
- 기능 3 : return 오른쪽에 뭐 적으면 array로 담아줌

```jsx
// 기능 1
var arr = [2, 3, 4];
arr.map(function () {
  console.log(1);
}); // console.log(1) 3번 실행됨

// 기능 2
var arr = [2, 3, 4];
arr.map(function (a) {
  console.log(a);
}); // 2, 3, 4 하나씩 출력됨

// 기능 3
var arr = [2, 3, 4];
var newArr = arr.map(function (a) {
  return a * 10;
});
console.log(newArr); // [20, 30, 40] 출력
```

<br>

출처

- 생활코딩 'React 2022 개정판'
- 코딩애플 'React 리액트 기초부터 쇼핑몰 프로젝트까지!'

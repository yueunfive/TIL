# etc

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

<br>

## onClick

- 어떤 html을 클릭시 원하는 코드를 실행하는 이벤트 핸들러 (버튼 기능)
- Click 대문자, {} 중괄호 사용, 중괄호 안에 함수를 넣어야 한다.

```jsx
function App(){

  function 함수(){
    console.log(1)
  }
  return (
     <div onClick={함수}>하하하</div>
  )
}

// 함수 따로 만드는게 귀찮으면 그 자리에서 바로 만들어도 됨
<div onClick={ function(){ ~ ~ } }>
<div onClick={ () => { ~ ~ } }>
```

<br>

## input

```jsx
// <input>에 유저가 입력할 때마다 안에 있는 코드를 실행
<input onChange={()=>{ console.log(1) }}/>

// 현재 <input>에 입력된 값 가져오기
// e.target : 현재 이벤트가 발생한 곳 (e는 작명)
<input onChange={(e)=>{ console.log(e.target.value) }}/>

// e.preventDefault() : 이벤트 기본 동작 막기
// e.stopPropagation() : 이벤트 버블링 막기

// state로 사용자가 input에 입력한 데이터 저장하기
function App (){

  let [input, setInput] = useState('');
  return (
    <input onChange={(e)=>{
      setInput(e.target.value)
      console.log(input)
    }} />
  )
}
```

<br>

## export default / import 문법

- 다른 파일에 보관된 변수, 함수, 자료형 등을 공유할 수 있음
- 파일마다 export default 키워드는 하나만 사용가능
- 파일경로는 ./ (현재경로) 부터 시작

```jsx
// data.js 파일
// 원하는 변수를 밖으로 내보내기
// export default 변수명;
let a = 10;
export default a;

// App.js 파일
// export 했던 변수를 다른 파일에서 사용하기
// import 작명 from './파일경로'
import a from "./data.js";
console.log(a);
```

```jsx
// 여러개의 변수 내보내기

// data.js 파일
var name1 = "yueun";
var name2 = "haeun";
export { name1, name2 };

// App.js 파일
import { name1, name2 } from "./data.js";

// export { } -> import { } 쓸 때 자유작명이 불가능.
// export 했던 변수명 그대로 적기.
```

출처 : 코딩애플 'React 리액트 기초부터 쇼핑몰 프로젝트까지!'

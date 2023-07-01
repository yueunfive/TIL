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

<br>

## 탭 UI 만들기

1. html css로 디자인 미리 완성하기
2. UI의 현재 상태를 저장할 state 하나 만들기
3. state에 따라서 UI가 어떻게 보일지 작성하기

```jsx
// step 2
let [tab, setTab] = useState(0);
..

// step 1(부트스트랩 활용)
<Nav variant="tabs"  defaultActiveKey="link0">
    <Nav.Item>
      <Nav.Link
				onClick={() => {setTab(0)}}
				eventKey="link0">버튼0
			</Nav.Link>
    </Nav.Item>
    <Nav.Item>
      <Nav.Link eventKey="link1">버튼1</Nav.Link>
    </Nav.Item>
    <Nav.Item>
      <Nav.Link eventKey="link2">버튼2</Nav.Link>
    </Nav.Item>
</Nav>
<TabContent tab={tab} />
...

// step 3
function TabContent(props) {
  if (props.tab === 0) {
    return <div>내용0</div>;
  }
  if (props.tab === 1) {
    return <div>내용1</div>;
  }
  if (props.tab === 2) {
    return <div>내용2</div>;
  }
}
```

<br>

## 컴포넌트 전환 애니메이션(transition)

1. 애니메이션 동작 전 스타일을 담을 className 만들기
2. 애니메이션 동작 후 스타일을 담을 className 만들기
3. transition 속성도 추가
4. 원할 때 2번 탈부착

```css
.start {
  opacity: 0;
}
.end {
  opacity: 1;
  transition: all 0.5s;
}
/* 원하는 <div> 요소에 start 넣어두고 end 탈부착할 때 마다 fade in 된다. */
```

```jsx
// "버튼을 누를 때 마다 end를 저기 부착해주세요"
// -> "tab이라는 state가 변할 때 end를 저기 (떼었다)부착해주세요"
// useEffect : 특정 state 아니면 props가 변할 때 마다 코드실행이 가능

function TabContent({ tab }) {
  let [fade, setFade] = useState("");

  useEffect(() => {
    setTImeout(() => {
      setFade("end");
    }, 100); // 타이머로 시간차 둬야됨
    return () => {
      // useEffect 실행 전에 실행
      setFade("");
    };
  }, [tab]); // tab이 변할 때 useEffect 안의 함수 실행

  return (
    <div className={"start " + fade}>
      {[<div>내용0</div>, <div>내용1</div>, <div>내용2</div>][tab]}
    </div>
  );
}
```

출처 : 코딩애플 'React 리액트 기초부터 쇼핑몰 프로젝트까지!'

<br>

# 새로 배운 점

## onClick 함수에서 함수 호출 방식

onClick 프로퍼티에 함수를 할당할 때 함수를 바로 전달해버리면, 그 함수가 렌더링 도중 호출되어 실행된다.

ex) 클릭을 안하고 input 창에 값을 입력하기만 해도 함수가 실행되는 오류 발생

→ 함수 자체를 `onClick` 프로퍼티에 전달하는 것이 아니라, 함수를 호출하기 위한 함수를 전달하는 것이 좋다. (화살표 함수 or 별도 함수 선언 후 호출)

```jsx
// Nope!
<button onClick={wordCondition() && handleOnClick()}>

// Yes!
<button onClick={() => wordCondition() && handleOnClick()}>

// Yes!
const doubleFunction = () => {
	wordCondition() && handleOnClick
}
..
<button onClick={doubleFunction}>
```

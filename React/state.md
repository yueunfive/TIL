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

<br>

## state 변경

- state 변경 함수 사용 (useState의 두 번째 변수)
- 사용법 : state변경함수(새로운 state)
- state변경함수는 ( ) 안에 입력한걸로 기존 state를 갈아치운다.

```jsx
let [thumb, thumbChange] = useState(0); // 두 번째 변수 : state 변경용 함수
.
.
<span onClick={() => {thumbChange(thumb + 1)}}>👍</span>{thumb}
```

<br>

## array, object state 변경

- 독립적인 카피본을 만들어서 수정 : [...기존state], {...기존state}
- ... : 괄호 벗기기 → [...변수] : 독립적인 array 복사본 생성
- state 변경함수 동작원리
  - 기존 state === 신규 state → state 변경 X
  - 독립적인 또 다른 배열이나 객체를 사용하지 않으면 결국 같은 걸로 보고 변경 X
- array/object 동작원리
  - let arr = [1,2,3] 이라고 하면 arr 변수에는 배열에 대한 화살표만 담겨있다.
  - 다른 변수로 카피본을 떠도 똑같은 값을 공유

```jsx
let [title, titleChange] = useState([
    "남자 코트 추천",
    "강남 우동 맛집",
    "리액트 독학",
  ]);
.
.
<button onClick={() => {
	let copy = [...title];
	copy[0] = "여자 코트 추천";
	titleChange(copy);
	}}> 👩 </button>
```

<br>

## 리액트 환경에서 동적인 UI 만드는 법

1. html css로 미리 UI 디자인을 다 해놓기

2. UI의 현재 상태를 state로 저장해두기

3. state에 따라서 UI가 어떻게 보일지 조건문 등으로 작성하기

```jsx
function App() {
	...
  let [modal, setModal] = useState(false); // step 2
	...
	return (
	...
		<div className="list">
		  <h4
		    onClick={() => { // step 3
		      if (modal == false) {
		        setModal(true);
		      } else setModal(false);
		    }}
		  >
		    {title[1]}
		  </h4>
		  <p>2월 17일 발행</p>
		</div>

		{
		  modal == true ? <Modal /> : null // 삼항연산자 : 조건식 ? true : false
		} // JSX 중괄호 안에서는 바로 if문 못씀.. 삼항연산자 쓰기!
	...
	)
}

function Modal() { // step 1
  return (
    <div className="modal">
      <h4>제목</h4>
      <p>날짜</p>
      <p>상세내용</p>
    </div>
  );
}
```

출처 : 코딩애플 'React 리액트 기초부터 쇼핑몰 프로젝트까지!'

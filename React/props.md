# props(속성)

- 부모 컴포넌트의 state를 자식 컴포넌트로 전송할 때 사용
- step 1 : 부모 안의 자식컴포넌트 사용하는 곳에 가서 <자식컴포넌트 작명={state이름} />
- step 2. 자식컴포넌트 만드는 function으로 가서 props라는 파라미터 등록 후 props.작명 사용

```jsx
function App() {
  let [title, setTitle] = useState(["UN village", "Candy", "Bambi"]);
  return (
    <div>
      <Modal title={title} color={"skyblue"}></Modal>
    </div>
  );
}

function Modal(props) {
  return (
    <div className="modal" style={{ background: props.color }}>
      <h4>{props.title[0]}</h4>
      <p>날짜</p>
      <p>상세내용</p>
    </div>
  );
}

// <Modal a={a}  b={b} ... > 무한히 전송 가능
// state 말고 style 등 이것저것 다 전송할 수 있다.
// <Modal 글제목={변수명}> 일반 변수, 함수 전송도 가능
// <Modal color="skyblue"> 일반 문자전송은 중괄호 없이 따옴표만 해도 된다.
// 자식 → 부모 방향 전송은 불가능(단방향). 자식이 아닌 다른 컴포넌트로의 전송도 불가능
// 파라미터 문법를 통해 함수 하나로 다양한 기능을 사용하는 것이 키포인트!
```

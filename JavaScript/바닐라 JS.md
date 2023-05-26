## 자바스크립트로 HTML에서 원하는 값 가져오기

- getElementById() : 해당 아이디 하나만 불러올 수 있다.

- getElementByClassName() : 해당 클래스네임을 배열 형태로 불러온다.

- getElementByTag() : 해당태그를 배열형태로 불러온다.

- queryselect() / querySelectAll() : element를 CSS selector방식으로 검색할 수 있다. 중복요소가 많을 시 queryselect는 첫번째 요소만, queryselectAll은 모든 조건들을 보여준다.

<br>

## 이벤트리스너
```jsx
// 이벤트리스너 : 이벤트가 발생했을 때 그 처리를 담당하는 함수
// addEventListener("event", function);
// 이때 function에 실행 하는 () 기호는 쓰지 않는다. 
// 이벤트 발생 시 함수가 실행 되는 것이기 때문에 ()를 임의로 쓰면 이벤트 발생 전에 실행됨.

const h1 = document.querySelector("div.hello:first-child h1")

function handleTitleClick() {
  h1.style.color = "blue";
}
function handleMouseEnter() {
  h1.innerText = "Mouse is here"
}
function handleMouseLeave() {
  h1.innerText = "Mouse is gone"
}
function handleWindowResize() {
  document.body.style.backgroundColor = "tomato"
}
// document의 head,title,body는 중요하기에 document.body.~로 가져올 수 있다. 반면 h1이나 div 같은 element들은 querySelcetor나 getElementByID로 불러와야 한다.
function handleWindowCopy() {
  alert("Copier!!!")
}

h1.addEventListener("click", handleTitleClick);
h1.addEventListener("mouseenter", handleMouseEnter); 
h1.addEventListener("mouseleave", handleMouseLeave);
window.addEventListener("resize", handleWindowResize);  
window.addEventListener("copy", handleWindowCopy);
```
<br>

## CSS in JS

```jsx
// 1. element 찾기
const h1 = document.querySelector("div.hello:first-child h1")

// 3. 그 event에 반응하기
function handleTitleClick() {
  const currentColor = h1.style.color;
  let newColor;
  if (currentColor === 'blue') {
    newColor = 'tomato';
  } else {
    newColor = 'blue';
  }
  h1.style.color = newColor;
}

// 2. event를 listen하기
h1.addEventListener("click", handleTitleClick);
```
<br>

## toggle

```jsx
function handleTitleClick() {
	h1.classList.toggle("clicked")
} 
// h1 클래스 중 clicked가 있으면 없애고, 없으면 추가시킨다.
// toggle : 토큰이 존재하면 토큰 제거, 토큰이 존재하지않으면 토큰 추가
```
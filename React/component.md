# Component(컴포넌트)

React의 본질 :  “사용자 정의 태그를 만드는 기술”

컴포넌트 = 사용자 정의 태그 = 복잡한 여러 태그들을 하나의 태그(독립된 부품)로 묶은 후 이름 붙힘

```jsx
// 사용자 정의 컴포넌트는 반드시 대문자로 시작해야 한다.
function Header() {  
  return <header>
    <h1><a href="">React</a></h1>
  </header>
}

function Nav() {
  return <nav>
    <ol>
      <li><a href="">html</a></li>
      <li><a href="">css</a></li>
      <li><a href="">js</a></li>
    </ol>
  </nav>
}

function Article() {
  return <article>
    <h2>Hello, React!</h2> 
    Nice to meet you🙂
    </article>
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
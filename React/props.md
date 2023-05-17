# props(속성)

props(property)란 상위 컴포넌트가 하위 컴포넌트에 값을 전달할 때 사용하는 속성이다,

상위 컴포넌트가 하위 컴포넌트에 값을 전달하기 때문에 단방향 데이터 흐름을 갖는다.

부모 컴포넌트는 수정 가능하지만, 자식 컴포넌트는 읽기만 가능하다.

출처 : [https://life-with-coding.tistory.com/509](https://life-with-coding.tistory.com/509)

필기 참고 : [https://bellsilver7.tistory.com/267](https://bellsilver7.tistory.com/267) 

```javascript
function Header(props) { 
  return <header> 
    <h1><a href="">{props.title}</a></h1> // {} 중괄호로 감싸주어야 한다.
  </header>
}

function Nav(props) {
  const lis = []
  for(let i=0; i<props.topics.length; i++){
    let t = props.topics[i]
    lis.push(<li key={t.id}><a href={'/read/'+t.id}>{t.title}</a></li>)
  }
  return <nav>
    <ol>
      {lis}  
    </ol>
  </nav>
}

function Article(props) {
  return <article>
    <h2>{props.title}</h2> 
      {props.body}
    </article>
}

function App() {
  const topics = [
    {id:1, title:'html', body:'html is ...'},
    {id:2, title:'css', body:'css is ...'},
    {id:3, title:'javascript', body:'javascript is ...'},
  ]
  return (
    <div>
      <Header title='React'></Header>
      <Nav topics={topics}></Nav>
      <Article title='Welcome' body='Hello, React!'></Article>
    </div>
  );
}
```
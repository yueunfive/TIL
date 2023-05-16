# event(이벤트)

: 웹페이지에서 마우스를 클릭했을 때, 키를 입력했을 때, 스크롤 했을 때 등 상호작용으로 인해 일어나는 어떤 사건

출처 및 필기 참고 : [https://bellsilver7.tistory.com/267](https://bellsilver7.tistory.com/267) 

<br>

## Header 컨포넌트에 이벤트 부여

```jsx
function Header(props) {
  return <header> 
    <h1><a href="" onClick={function(event){ // onClick={event=>{
      event.preventDefault(); // a 태그의 기본 동작 방지
      props.onChangeMode();
    }}>{props.title}</a></h1>
  </header>
}


...

function App() {
  ...
  return (
    <div>
      <Header title='React' onChangeMode={()=>{
        alert('Header');
      }}></Header>
	     ...
    </div>
  );
}
```
<br>

## Nav - 클릭시 각기 다른 값 출력

```jsx
function Nav(props) {
  const lis = []
  for(let i=0; i<props.topics.length; i++){
    let t = props.topics[i]
    lis.push(<li key={t.id}>
      <a id={t.id} href={'/read/'+t.id} onClick={event=>{
        event.preventDefault();
	        props.onChangeMode(event.target.id);
      }}>{t.title}</a></li>)
  }
  return <nav>
    <ol>
      {lis}  
    </ol>
  </nav>
}

...

function App() {
  const topics = [
    ...
  ]
  return (
    <div>
      ...
      <Nav topics={topics} onChangeMode={(id)=>{
        alert(id);
      }}></Nav>
      ...
    </div>
  );
}
```
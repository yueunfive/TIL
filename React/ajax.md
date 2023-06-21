# AJAX

- 서버에 GET, POST 요청을 할 때 새로고침 없이 데이터를 주고받을 수 있게 도와주는 간단한 브라우저 기능
- GET, POST 요청 방법 : fetch(자바스크립트 문법), axios(외부 라이브러리) 등

  → axios가 제일 편해서 보편적으로 사용

```jsx
import axios from 'axios'

function App(){
  return (
    <button onClick={()=>{
      axios.get('..url..')
			.then((결과)=>{
        console.log(결과.data)
      })
      .catch(()=>{ // 실패했을 때 실행할 코드
        console.log('실패함')
      })
    }}>버튼</button>
  )
}

// post 요청하는 법
axios.post('URL', {name : 'yueun'})
.then...

// 동시에 AJAX 요청 여러개 날리기
Promise.all( [axios.get('URL1'), axios.get('URL2')] )
.then...
```

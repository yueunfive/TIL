# Ajax

- 서버 : 데이터를 달라고 요청하면 데이터를 보내주는 간단한 프로그램
  - 데이터 요청시 어떤 데이터인지(url 기재), 어떤 방법으로 요청할지(GET/POST 등) 결정
  - GET 요청 : 서버에 있던 데이터를 읽고 싶을 때 사용
  - POST 요청 : 서버로 데이터를 보내고 싶을 때 사용
  - GET, POST 요청을 그냥 날리면 브라우저가 새로고침되는 단점이 있다.
- Ajax : 서버에 GET, POST 요청을 할 때 새로고침 없이 데이터를 주고받을 수 있게 도와주는 간단한 브라우저 기능 (ex. 더보기로 새로고침 없이 쇼핑물 상품 더 가져오기)

```jsx
// jQuery로 AJAX 요청하기

// get 요청
// ajax 요청 성공시 .done 안에 있는 코드 실행
// ajax 요청 실패시 .fail 안에 있는 코드 실행
$.get("https://codingapple1.github.io/price.json")
  .done(function (data) {
    // 가져온 데이터 -> 파라미터
    console.log(data);
  })
  .fail(function () {
    console.log("실패함");
  });

// post 요청
// url, 서버로 보낼 데이터
$.post("url~~", { name: "kim" });
```

출처 : 코딩애플 'JavaScript 입문과 웹 UI개발'

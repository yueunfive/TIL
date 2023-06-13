# map

- 반복되는 컴포넌트를 렌더링하기 위하여 자바스크립트 배열의 내장 함수 (반복문)
- JSX 안에서 html을 반복생성하고 싶을 때, 많은 div들을 반복문으로 줄이고 싶을 때 사용
- 기능 1 : array에 들어있는 자료갯수만큼 그 안에 있는 코드를 반복실행
- 기능 2 : 콜백함수에 안에 작명한 파라미터(a)가 array 안에 있던 모든 자료를 하나씩 출력
  - 파라미터 2개까지 작명 가능 : map(function(a, i){})
  - 첫째 파라미터 a : array안에 있던 자료
  - 둘째 파라미터 i : 0부터 1씩 증가하는 정수
- 기능 3 : return 오른쪽에 뭐 적으면 array로 담아줌

```jsx
// 기능 1
var arr = [2, 3, 4];
arr.map(function () {
  console.log(1);
}); // console.log(1) 3번 실행됨

// 기능 2
var arr = [2, 3, 4];
arr.map(function (a) {
  console.log(a);
}); // 2, 3, 4 하나씩 출력됨

// 기능 3
var arr = [2, 3, 4];
var newArr = arr.map(function (a) {
  return a * 10;
});
console.log(newArr); // [20, 30, 40] 출력
```

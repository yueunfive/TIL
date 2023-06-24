# Redux

- props 없이 state를 공유할 수 있게 도와주는 라이브러리
- js 파일 하나에 state들을 보관할 수 있으며 모든 컴포넌트에서 직접 꺼내쓸 수 있다.
  → 일일이 props 전송 X, 컴포넌트간 state 공유 편해짐

  <br>

## Redux store에 state 보관하는 법

- createSlice( ) 로 state 만들기 → { name : 'state 이름', initialState : 'state 값' }
- configureStore( ) 안에 등록하기 → { 작명 : createSlice만든거.reducer }

```jsx
store.js;

import { configureStore, createSlice } from "@reduxjs/toolkit";

let user = createSlice({
  name: "user",
  initialState: "kim",
});

export default configureStore({
  reducer: {
    user: user.reducer,
  },
});
```

<br>

## Redux store에 있던 state 가져다쓰는 법

```jsx
Cart.js;

import { useSelector } from "react-redux";

function Cart() {
  // Redux store에 있던 모든 state 남음
  let a = useSelector((state) => {
    return state;
  });
  console.log(a);

  return 생략;
}

// let a = useSelector((state) => state.user) -> user만 남음
```

<br>

## Redux store의 state 변경하는 법

1. store.js 안에 state 수정해주는 함수 만들기
2. export 하기
3. dispatch(state 변경함수())

```jsx
// step 1 - store.js 안에 state 수정해주는 함수 만들기
// slice 안에 reducers : { } 열고 거기 안에 함수 만들기
// 함수 작명 마음대로 해도 됨
// 파라미터 하나 작명하면 그건 기존 state(iniatialState)가 된다.
// return 우측에 새로운 state 입력하면 그걸로 기존 state를 갈아치워준다.

store.js;

let user = createSlice({
  name: "user",
  initialState: "Oh",
  // state 수정해주는 함수
  reducers: {
    changeName(state) {
      return "yueun" + state;
    },
  },
});
```

```jsx
// step 2 - export
// slice이름.actions : state 변경함수가 전부 그 자리에 출력

store.js;

export let { changeName } = user.actions;
```

```jsx
// step3 - import 후 dispatch로 감싸서 사용하기
// dispatch : store.js로 요청 보내주는 함수

(Cart.js)

import { useDispatch, useSelector } from "react-redux"
import { changeName } from "./store.js"
..
let dispatch = useDispatch()
..
<button onClick={()=>{
  dispatch(changeName())
}}>+</button>
```

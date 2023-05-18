# position
: 좌표속성을 적용할 기준점을 지정해주는 속성

top, left, bottom, right 라는 속성을 사용하면 기준점을 중심으로 요소의 상하좌우 위치를 변경할 수 있다.

```css
.button {
  position : absolute; 
  top : 20px;
  left : 30%;
}

/* position 속성 종류 */
.box {
  position : static; /* 기준이 엄서요 (좌표적용 불가) */
  position : relative; /* 기준이 내 원래 위치요 */
  position : absolute; /* 기준이 내 부모(relative)요 */
  position : fixed; /* 기준이 브라우저 창이요 (viewport) */
}
```

position : absolute는 position : relative를 가지고 있는 부모를 기준으로 찰싹 달라붙은 뒤에 좌표값을 적용하게 된다.

<br>

출처 : https://codingapple.com/course/html-basics/
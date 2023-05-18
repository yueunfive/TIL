# transition
: CSS 속성을 변경할 때, 속성 값의 변화가 일정 시간(duration)에 걸쳐 일어나도록 하는 것 (애니메이션)

```html
<div style="position: relative">
  <div class="overlay-wrap">
    <div class="overlay"></div>
  </div>
  <img src="../img/product1.jpg">
</div>    
```

```css
.overlay-wrap {
  position: absolute;
  width: 100%;
  height: 100%;
  overflow: hidden;
/* overflow : 박스의 폭이나 높이를 초과하는 내부요소를 처리하기 위한 속성
hidden : 넘치는 내부요소를 자동으로 잘라 없애준다. */
}
.overlay {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  margin-top: 100%;
  transition: all 1s;
  /* all : 모든 스타일이 변할 때 서서히 변경
	 1s : 1초에 걸쳐서 서서히 변경 */ 
}
.overlay-wrap:hover .overlay {    
  margin-top: 50%;
}
```
<br>

출처 : https://codingapple.com/course/html-basics/
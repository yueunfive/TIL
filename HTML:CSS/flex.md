# Flex

## Flexbox 레이아웃 사용법
: 박스들을 감싸는 부모 요소에게 display : flex를 사용

```html
<div class="flex-container">
  <div class="box"></div>
  <div class="box"></div>
  <div class="box"></div>
</div>
```

```css
.flex-container {
  display : flex;
}
.box {
  width : 100px;
  height : 100px;
  background : black;
  margin : 10px;
}
```
<br>

## Flexbox 세부속성

```css
.flex-container {
  display : flex;
  justify-content : center;  /* 좌우정렬 */
  align-items : center;  /* 상하정렬 */
  flex-direction : column; /* 세로정렬 */
  flex-wrap : wrap;  /* 폭이 넘치면 밑으로 내림 */
}
.box {
  flex-grow : 2;  /* 폭이 상대적으로 몇배인지 결정, 기본값 = 0 */
}
```
<br>

## 동시에 좌측 & 우측정렬

```html
<div class="flex-container">
  <div class="box"></div>
  <div class="box" style="flex-grow : 1"></div>
  <div class="box"></div>
</div>
```
<br>

출처 : https://codingapple.com/course/html-basics/
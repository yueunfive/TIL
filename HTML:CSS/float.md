# float
: 요소를 공중에 띄워 왼쪽/오른쪽 정렬하는 속성. 가로 정렬할 때 사용한다.

```html
<div>
  <div class="left-box"></div>
  <div class="right-box"></div>
  <div class="footer"></div>
</div>
```

```css
.left-box {
  width : 100px; 
  height : 100px;
  float : left;
}
.right-box {
  width : 100px; 
  height : 100px;
  float : left;
}
/* 박스 두개를 만들어 각각 왼쪽으로 정렬 */
.footer {
  clear : both
}
/* float를 쓰고 나면 항상 clear 속성이 필요 */
```
<br>

출처 : https://codingapple.com/course/html-basics/
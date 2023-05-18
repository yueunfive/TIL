# Pseudo-class 셀렉터

pseudo-class 셀렉터를 붙이면 여러 상태에 따른 스타일을 지정해줄 수 있다.

hover, focus, active 스타일 넣을 때 나열된 순서대로 선언해야 잘 동작한다.

hover 2. focus 3. active (hofa로 외우라는데… 음..)

```css
.btn:hover {
  background : blue; /*마우스를 올려놓을 때*/
}
.btn:focus {
  background : black; /*클릭 후 계속 포커스 상태일 때*/
}
.btn:active {
  background : grey; /*클릭 중일 때*/
}

input:focus {
  border : 2px solid blue;
}

a:link { 
  color : red; /*방문 전 링크*/ 
} 
a:visited { 
  color : black; /*방문 후 링크*/ 
}
```
<br>

출처 : https://codingapple.com/course/html-basics/

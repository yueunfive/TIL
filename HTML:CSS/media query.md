# media query
: 반응형 레이아웃 만들 때, CSS 파일 최하단에 사용한다.

```css
@media screen and (max-width : 1200px) { 
  .box { 
    font-size : 40px; 
  } 
} 
/* "현재 브라우저의 폭이 1200px 이하일 경우에 
안에 있는 class를 적용 */
@media screen and (max-width : 768px) { 
  .box { 
    font-size : 30px; 
  } 
}
/* "현재 브라우저의 폭이 768px 이하일 경우에 
안에 있는 class를 적용 */
```

Breakpoint : media query 문법 max-width 안에 넣는 브라우저 폭

권장 Breakpoint : 1200px / 992px / 768px / 576px

<br>

출처 : https://codingapple.com/course/html-basics/

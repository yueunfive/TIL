# class 작명법 (OOCSS, BEM)

## OOCSS 
: Object Oriented CSS, 뼈와 살을 각각의 class로 분리하는 CSS 작성방식

```html
<button class="main-btn bg-red">red-btn</button>
<button class="main-btn bg-blue">blue-btn</button>
```

```css
.main-btn {
  font-size : 20px;
  padding : 15px;
  border : none;
  cursor : pointer;
} /* 뼈대 */

.bg-red {
  background : red;
}
.bg-blue {
  background : blue;
}
```

<br>

## BEM 
: Block, Element, Modifier로 나누어서 클래스명을 기술하는 방법

```html
<div class="profile">
  <img class="profile__img">
  <h4 class="profile__h4">이름</h4>
  <p class="profile__content">소개글</p>
  <button class="profile__button--red">빨간버튼</button>
  <button class="profile__button--blue">파란버튼</button>
</div>
```
<br>

출처 : https://codingapple.com/course/html-basics/
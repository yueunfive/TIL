# Boostrap
:  웹페이지에 필요한 버튼, 메뉴, 탭, 모달, 카드 등 필수 요소들을 모아놓은 일종의 CSS 라이브러리이다. 

class 복붙식으로 빠르고 편하게 디자인할 수 있다.

[https://getbootstrap.com/](https://getbootstrap.com/) 홈페이지에 다 나와있으니까 쓰고 싶은 속성이나 효과 있으면 검색해서 사용하면 된다.

<br>

## Utility Class 

ex. CSS 에다가 padding-bottom 기록할 필요 없이 그냥 pb-5 이렇게 주면 끝

```html
<div class="container">여백 박스</div>
<div class="mt-5">margin-top</div>
<div class="pb-5">padding-botto</div>
<div class="fs-3">font-size</div>
<div class="text-center">text-align</div>
<div class="fw-bold">font-weight</div>
....
```
<br>

## Bootstrap grid 레이아웃
: Bootstrap은 웹디자인의 대 원칙 12 column 디자인을 사용한다.

<br>

## 박스 쪼개기

```html
<!-- 균일한 3등분 -->
<div class="row">
  <div class="col-4"> 안녕 </div>
  <div class="col-4"> 안녕 </div>
  <div class="col-4"> 안녕 </div>
</div>

<!-- 균일한 2등분 -->
<div class="row">
  <div class="col-6"> 안녕 </div>
  <div class="col-6"> 안녕 </div>
</div>

<!-- 불균일한 2등분 -->
<div class="row">
  <div class="col-4"> 안녕 </div>
  <div class="col-8"> 안녕 </div>
</div>
```
<br>

## 반응형 grid

```html
<div class="row">
  <div class="col-lg-3 col-md-6"> 안녕 </div>
  <div class="col-lg-3 col-md-6"> 안녕 </div>
  <div class="col-lg-3 col-md-6"> 안녕 </div>
  <div class="col-lg-3 col-md-6"> 안녕 </div>
</div>
<!-- md(720px) 사이즈 이상에서만 6컬럼(1/2) 차지 -->
<!-- lg(992px) 사이즈 이상에서만 3칼럼(1/4) 차지 -->
<!-- 그 미만은 세로 정렬 -->

<div class="row">
  <div class="col-4 order-md-2"> 안녕 </div>
  <div class="col-4 order-md-3"> 안녕 </div>
  <div class="col-4 order-md-1"> 안녕 </div>
</div>
<!-- order-숫자 부착해서 <div> 순서 재배치도 가능 -->
```

[https://getbootstrap.com/docs/4.0/layout/grid/](https://getbootstrap.com/docs/4.0/layout/grid/) grid options에서 사이즈 참고

<br>

출처 : https://codingapple.com/course/html-basics/
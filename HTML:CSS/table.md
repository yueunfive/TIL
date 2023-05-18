# Table

```html
<table>
  <thead></thead>
  <tbody>
    <tr>
      <td>내용</td>
      <td>내용</td>
    </tr>
  </tbody>
</table>
```
ttr은 row(행), td는 column(열)을 의미한다.  
tbody, thead는 헤드부분 영역구분을 위해 사용한다.  
td 대신 th 태그를 사용하면 굵게 표시된다.

<br>

## nth-child 셀렉터

```css
.cart-table td:nth-child(2) {
  color: red;
}
```

여러 요소를 찾은 다음 원하는 n번째 요소만 스타일을 주고 싶으면 :nth-child(n) 이걸 뒤에 붙여주면 된다.  
위의 코드는 그래서 .cart-table 안에 있는 모든 td를 찾은 다음 2번째 나오는 td에만 color를 준다.  
테이블에서 원하는 순서의 셀에 스타일줄 때 유용하게 사용한다.

<br>

## 셀 블록마다 width를 설정하기

```html
<table>
  <tr>
    <td class="student">이름</td>
    <td class="sId">학번</td>
    <td>전공</td>
  </tr>
</table>
```

```css
.student {
  width : 50%
}
.sId {
  width : 20%
}
```
하나의 td에 width를 주어도 전체 열의 width가 변한다.

<br>

## 열 병합 
: colspan에 원하는 숫자를 넣으면 그 숫자만큼 옆의 셀을 합쳐준다.
```html
<td colspan="4"></td>
```
tr 행 병합 : rowspan

참고 : https://www.w3schools.com/html/html_table_colspan_rowspan.asp

<br>

출처 : https://codingapple.com/course/html-basics/
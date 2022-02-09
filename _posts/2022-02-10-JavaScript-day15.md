---
layout: single
title : JavaScript day15
categories : coding
tag : JavaScript
toc : false
---

폼객체

<br>

### 폼객체

폼객체는 웹 문서내 여러 폼요소가 존재할 경우 특정 폼 요소를 다루기 위해 사용한다.

```html
<form name="myform" id="regform"> <!--0번 폼-->
    <input type="text" name="userid" id="id" value="apple">
</form>

<form name="myform" id="etcform"> <!--1번 폼-->
    <input type="text" name="comment" id="comment">
</form>
```

웹 문서 상에 이런 폼 요소가 있다고 가정해보자. 

먼저 폼에 접근하는 방법으로

```javascript
const frm = document.myform; // name를 통해 0,1번 동시 접근
const frm = document.getElementBtId('regform'); // id를 통해 0번 폼 접근
const frm = document.forms[0] // 0번 폼 접근
const frm = document.forms[1] // 1번 폼 접근
```

이렇게 form를 객체화 시켜 변수로서 사용가능하다.

다음으로 input 내에 입력된 apple에 접근하는 여러 방식을 보자.

```javascript
const id = document.myform.userid.value; // apple
const id = frm.userid.value; // frm내 name이 userid인 요소의 값 = apple
const id = frm.elements[0].value; // frm내 요소 중 인덱스 0번인 요소의 값 = apple
const id = frm.element['userid'].value; // frm내 요소 중 name이 userid인 요소의 값 = apple
const id = document.getElementBtId('id').value; // id가 id인 요소의 값 = apple
const id = document.forms[0][0].value; // apple
```

폼 객체를 활용하여 input내 value 값을 간단하게 접근하여 객체로서 사용할 수 있다.




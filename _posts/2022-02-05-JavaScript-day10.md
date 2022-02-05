---
layout: single
title : JavaScript day10
categories : coding
tag : JavaScript
toc : false
---

Date 객체 | 브라우저 관련 객체

<br>



#### Date 객체

날짜와 시간 정보를 나타내고 쉽게 다룰 수 있는 객체이다.

```javascript
const date = new Date(); // 현재 날짜 시간
const date = new Date(21, 11, 30); // 1921년 12월 30일
const date = new Date(2021, 11, 30); // 2021년 12월 30일
```

<br>

**Date 객체를 만드는 방법**

```javascript
const date = new Date(); // 현재 날짜 시간
const date = new Date(2021, 11, 30);
const date = new Date("2021-11-30");
const date = new Date("4234687234682");  // timestamp 1970년 1월1일부터 밀리세컨씩
const datetime = new Date(2021, 11, 10, 12, 30, 0, 0);
```

```javascript
const date = new Date();
console.log(`현재 년도 : ${date.getFullYear()}`);
console.log(`현재 월 : ${date.getMonth() + 1}`);
console.log(`현재 일 : ${date.getDate()}`);
console.log(`현재 시간 : ${date.getHours()}`);
console.log(`현재 분 : ${date.getMinutes()}`);
console.log(`현재 초 : ${date.getSeconds()}`);
/*
    현재 년도 : 2021
    현재 월 : 12
    현재 일 : 30
    현재 시간 : 10
    현재 분 : 11
    현재 초 : 37
*/
```



<hr>


### BOM(Brower Object Model)

\- 브라우저에 관련한 객체로 웹 브라우저에 관련한 여러가지 효과를 만들 수 있다. 

<br>

**window 객체**

브라우저 창이 열릴때 마다 하나씩 만들어진다. 브라우저 창 안의 요소 중에서 최상위에 위치한다.

|   종류    | 설명                                                         |
| :-------: | ------------------------------------------------------------ |
| document  | 웹 문서 마다 하나씩 있으며 \<body> 태그를 만나면 만들어 진다. HTML 문서의 정보가 담겨 있다. |
| navigator | 현재 사용하는 브라우저의 정보가 들어있다.                    |
|  history  | 현재 창에서 사용자의 방문 기록을 저장한다.                   |
| location  | 현재 페이지의 URL 정보가 담겨 있다.                          |
|  screen   | 현재 사용하는 화면 정보를 다룬다.                            |

<br>

**window 객체** 내부에 존재하는 메소드로 시간에 관련한 객체를 알아보자.

**setTimeout()** 일정 시간이 지난 후 매개변수로 제공된 함수를 실행<br>**clearTimeout()**  setTimeout()에서 실행된 함수를 취소

```javascript
function hello(){
	alert('안녕하세요 여러분!');
}
const st = window.setTimeout(hello, 2000);
// window.clearTimeout(st);  // 취소시키기
```

브라우저 실행 후 2초 뒤에 함수 **hello()**를 실행한다. 취소하고자하면 주석 처리된 window.clearTimeout(st);를 실행하면 된다.

<br>

**setInterval()** 일정시간 마다 매개변수로 제공된 함수를 실행

**clearInterval()** setInterval()에서 실행된 함수를 취소

```javascript
<script>

function hello(){
	console.log('안녕하세요 여러분!');
}

function stophello(){
    console.log('hello 함수가 중지되었어요!');
    clearInterval(si);
}

const si = window.setInterval(hello, 2000);

</script>
<button type="button" onclick="stophello()">중지</button>
```

브라우저 실행시 2초에 한번씩 함수 hello()를 실행하고 버튼을 누르면 stophello()를 실행하여 clearInterval(si);으로 setInterval()에 실행된 함수를 취소한다.




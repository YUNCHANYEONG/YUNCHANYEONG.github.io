---
layout: single
title : JavaScript day11
categories : coding
tag : JavaScript
toc : false
---

브라우저 관련 객체(location, history, navigator)

<br>



### 브라우저 관련 객체(계속)

#### location 객체

현재 브라우저에 표시된 HTML 문서의 주소를 얻거나, 브라우저에 새 문서를 불러 올 때 사용한다. window 객체의 location 프로퍼트와 documant 객체의 location 프로퍼티에 같이 연결한다. 

href : 전체 URL를 리턴<br>hostname : 호스트(ip, 도메인)<br>pathname : 파일명<br>port : 포트명

```javascript
<button type="button" onclick="sendit()">네이버로 이동</button>
<script>
    console.log(`현재 문서의 주소 : ${location.href}`); 
    // 현재 문서의 주소 : http://127.0.0.1:5500/location.html

    console.log(`현재 문서의 호스트 : ${location.hostname}`); // 현재 문서의 호스트 : 127.0.0.1
    console.log(`현재 문서의 파일명 : ${location.pathname}`); // 현재 문서의 파일명 : /location.html
    console.log(`현재 문서의 포트 : ${location.port}`); // 현재 문서의 포트 : 5500

    function sendit(){
        location.href = "https://www.naver.com";
    }
</script>
```

<br>

#### history 객체

브라우저의 히스토리 정보를 문서와 문서 상태 목록으로 저장하는 객체로서 사용자의 개인정보를 보호하기 위해 객체의 접근하는 방법을 일부 제한하고 있다.

back() : 브라우저에서 뒤로 버튼을 누른 효과<br>go() : 매개변수로 전달된 숫자만큼 히스토리에 적용된 페이지로 이동<br>goForward() : 브라우저에서 앞으로 버튼을 누른 효과

```javascript
const date = new Date(); // 현재 날짜 시간
const date = new Date(2021, 11, 30);
const date = new Date("2021-11-30");
const date = new Date("4234687234682");  // timestamp 1970년 1월1일부터 밀리세컨씩
const datetime = new Date(2021, 11, 10, 12, 30, 0, 0);
```

```javascript
<input type="button" value="뒤로" onclick="goBack()">
<input type="button" value="앞으로" onclick="goForwardk()">
<input type="button" value="뒤로 두페이지" onclick="goBack2()">
<input type="button" value="새로고침" onclick="goReload()">
<script>
    'use strict';
    function goBack(){
        history.back();
    }
    function goForwardk(){
        history.forward();
    }
    function goBack2(){
        history.back(-2);
    }
    function goReload(){
        history.go(0);
        // == location.reload();
    }
</script>
```

<br>

#### navigator 객체

브라우저 공급자 및 버전 정보 등을 포함한 브라우저에 대한 정보를 저장하는 객체

```javascript
const success = function(location){
    console.log(location.coords.latitude); // 내 현 위도
    console.log(location.coords.longitude); // 내 현 경도
}

const fail = function(msg){
    console.log(msg.code);
}

navigator.geolocation.getCurrentPosition(success, fail);
```

내 현재 위경도를 볼 수 있는 객체로서 사용된다.




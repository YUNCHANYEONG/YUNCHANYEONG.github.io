---
layout: single
title : JavaScript day16
categories : coding
tag : JavaScript
toc : false
---

이벤트 타입 | 이벤트 리스너

<br>

### 이벤트

대부분의 함수는 사용자가 화면에 버튼을 클릭하거나 항목을 선택했을 때 실행된다. 이처럼 버튼을 클릭하거나 항목을 선택하는것을 이벤트라고한다. 이벤트는 웹 브라우저가 알려주는 HTML 요소애 댜한 사건의 발생을 의미하며 웹 페이지에 사용된 자바스크립트는 발생한 이벤트에 반응하여 특정 동작을 수행한다. 이에 따라 자바 스크립트는 비동기식 이벤트 중심 프로그래밍 모델이라고한다.

<br>

#### 이벤트 타입

이벤트 타입은 발생한 이벤트의 종류로 이벤트 명이라고도한다. 주요 이벤트 타입으로는 마우스, 키보드, 문서로딩, 폼 이벤트가 있다.

**마우스 이벤트**

| 종류      | 설명                                                |
| --------- | --------------------------------------------------- |
| click     | 사용자가 HTML요소를 클릭했을때 발생                 |
| dbclick   | 사용자가 HTML요소를 더블클릭했을때 발생             |
| mousedown | 사용자가 요소위에서 마우스 버튼을 눌렀을 때 발생    |
| mouseover | 사용자가 요소위로 옮겨질 일 때 발생                 |
| mousemove | 사용자가 요소위에서 마우스 포인트을 움직일 때 발생  |
| mouseeout | 사용자가 요소에서 벗어날 때 발생                    |
| mouseup   | 사용자가 요소위에서 마우스 버튼에서 손을 뗄 때 발생 |

<br>

**키보드 이벤트**

| 종류      | 설명                           |
| --------- | ------------------------------ |
| keydown   | 사용자가 키를 누르는 동안 발생 |
| dbclick   | 사용자가 키를 눌렀을 때 발생   |
| mousedown | 사용자가 키에서 뗄 때 발생     |

<br>

**문서로딩 이벤트**

| 종류   | 설명                                                 |
| ------ | ---------------------------------------------------- |
| abort  | 문서가 완전히 로딩되기전에 불러오기를 멈췄을 때 발생 |
| error  | 문서가 완전히 로딩되지 않았을 때 발생                |
| load   | 문서 로딩이 끝나면 발생                              |
| resize | 문서 화면 크기가 바뀌었을 때 발생                    |
| scroll | 문서 화면이 스크롤되었을때 발생                      |
| unload | 문서에 벗어날 때 발생                                |

<br>

**폼 이벤트**

| 종류   | 설명                                 |
| ------ | ------------------------------------ |
| blur   | 몸 요소에 포커스를 잃었을 때 발생    |
| change | 목록이나 체크상태 등이 변경되면 발생 |
| focus  | 폼 요소에 포커스가 놓였을 때 발생    |
| reset  | 폼이 리셋되었을 때 발생              |
| submit | submit 버튼을 클릭했을 때 발생       |

<br>

#### 이벤트 타겟(Event Target)

이벤트가 일어날 객체

```javascript
    <input type="button" onclick="sendit()" value="가입">
                 ------  -------  --------
               이벤트타겟 이벤트명 이벤트리스너
```

<br>

#### 이벤트 리스너(Event Listener)

이벤트가 발생했을 때 그 처리를 담당하는 함수로 이벤트 핸들러라고도 한다. 이벤트 리스너는 지정된 타입의 이벤트가 특정 요소에서 발생하면 웹 브라우저는 그 요소에 등록된 이벤트 리스너를 실행하게된다. 

```javascript
    <input type="button" id="testbtn" value="테스트">
    const btn = document.getElementById('testbtn');
    btn.addEventListener('click', clickBtn);

    function clickBtn(){
        ...
    }
```

<br>

```javascript
<script>
    'use strict';
window.onload = function(){
    const btn = document.getElementById('eventBtn');
    btn.addEventListener('click', function(){
        document.getElementById('text').innerHTML = '<b>버튼을 클릭했어요</b>';
    });
    btn.addEventListener('mouseover', mouseOverBtn);
    btn.addEventListener('mouseout', mouseOutBtn);
}
function mouseOverBtn(){
    document.getElementById('text').innerHTML = '<b>버튼을 위에 마우스가 올라갔어요</b>';
}
function mouseOutBtn(){
    document.getElementById('text').innerHTML = '<b>버튼을 위에 마우스가 나갔어요</b>';
}
</script>

<p><button id="eventBtn">이벤트 버튼</button></p>
<p id="text"></p>
```

아무것도 누르지 않은 상태 ) <br>![js16_1](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js16_1.JPG?raw=true)

버튼 위로 마우스가 올라감 ) <br>![js16_2](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js16_2.JPG?raw=true)

버튼에서 마우스가 벗어남 ) <br>![js16_3](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js16_3.JPG?raw=true)


---
layout: single
title : JavaScript day13
categories : coding
tag : JavaScript
toc : false
---

노드 연결 | 노드 생성

<br>

### 노드 연결

|      종류      |                            설명                             |
| :------------: | :---------------------------------------------------------: |
| appendChild()  | 새로운 노드를 해당 노드의 자식 노드 리스트 맨 마지막에 추가 |
| insertBefore() |         새로운노드를 특정 자식 노드 바로 앞에 추가          |
|  insertData()  |     새로운 노드를 텍스트 데이터에 새로운 텍스트로 추가      |

```javascript
<p id="item1">JavaScript</p>
<p id="item2">TypeScript</p>
<hr>
<div id="list">
    <p id="backend">node.js</p>
    <p>HTML</p>
    <p>CSS</p>
</div>
<hr>
<p id="text">지금 시간은 오전 9시40분입니다.</p>
<button onclick="appendNode()">노드추가1</button>
<button onclick="insertNode()">노드추가2</button>
<button onclick="appendText()">텍스트 추가</button>

<script>
    'use strict';

function appendNode(){
    const parent = document.getElementById('list');
    const newItem = document.getElementById('item1')
    parent.appendChild(newItem); // list 자식으로 item1를 연결한다.
}
function insertNode(){
    const parent = document.getElementById('list');
    const backend = document.getElementById('backend');
    const newItem = document.getElementById('item2');
    parent.insertBefore(newItem, backend); // list 자식 중 backend 앞에 item2를 연결한다.
}
function appendText(){
    const text = document.getElementById('text').firstChild;
    text.insertData(7, "아주 피곤한 "); // text의 텍스트 중 7번째 자리에 해당 텍스트를 연결한다.
}
</script>
```

아무것도 누르지 않은 상태 ) <br>![js13_1](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js13_1.JPG?raw=true)

1번 버튼 누름 ) <br>![js13_2](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js13_2.JPG?raw=true)

2번 버튼 누름 ) <br>![js13_3](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js13_3.JPG?raw=true)

3번 버튼 누름 ) <br>![js13_4](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js13_4.JPG?raw=true)

<br>

### 노드 생성

|       종류        |           설명            |
| :---------------: | :-----------------------: |
|  createElement()  |  새로운 요소 노드를 생성  |
| createAttribute() |  새로운 속성 노드를 생성  |
| createTextNode()  | 새로운 텍스트 노드를 생성 |

```javascript
<p id="el">새로운 문장이 이 문장 앞에 추가됨</p>
<p id="attr">이 단락에 새로운 속성이 추가됨</p>
<p id="text"></p>
<button onclick="createNode()">요소 노드 생성</button>
<button onclick="createAttr()">속성 노드 생성</button>
<button onclick="createText()">텍스트 노드 생성</button>
<script>
    'use strict';
function createNode(){
    const elNode = document.getElementById('el');
    const newNode = document.createElement('p'); // p태그 요소 생성
    newNode.innerHTML = '<b>💛새로운 요소</b>'; // <p><b>💛새로운 요소</b></p>
    document.body.insertBefore(newNode, elNode);
}
function createAttr(){
    const attr = document.getElementById('attr');
    const newAttr = document.createAttribute('style'); // style 속성 생성
    newAttr.value = 'color:deepskyblue; background-color:gold;';
    //style="color:deepskyblue; background-color:gold;"
    attr.setAttributeNode(newAttr); // 요소에 속성을 세팅함
    // <p id="attr" style="color:deepskyblue; background-color:gold;">
    // 이 단락에 새로운 속성이 추가됨</p>
}
function createText(){
    const textNode = document.getElementById('text');
    const newText = document.createTextNode('❤🧡💛💚💙'); // Text노드 생성 , inline
    textNode.appendChild(newText); // <p id="text">❤🧡💛💚💙</p>
}
</script>
```

아무것도 누르지 않은 상태 ) <br>![js13_5](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js13_5.JPG?raw=true)

1번 버튼 누름 ) <br>![js13_6](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js13_6.JPG?raw=true)

2번 버튼 누름 ) <br>![js13_7](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js13_7.JPG?raw=true)

3번 버튼 누름 ) <br>![js13_8](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js13_8.JPG?raw=true)

<br>
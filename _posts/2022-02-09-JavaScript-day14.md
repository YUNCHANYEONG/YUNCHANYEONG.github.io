---
layout: single
title : JavaScript day13
categories : coding
tag : JavaScript
toc : false
---

노드 제거 | 노드 복제

<br>

### 노드 제거

특정 노드를 제거하기 위해서는 removeChild()를 사용한다. removeChild()는 자식 노드 리스트에서 특정 자식 노드를 제거하고 성공적으로 노드가 제거되면 제거된 노드를 반환할 수 있다. 노드가 제거 될 때 노드의 모든 자식들도 다 같이 제거한다. removeAttribute()는 노드의 속성을 제거할 때 사용된다.

```javascript
<div id="list">
    <p>HTML</p>
	<p id="item">CSS</p>
	<p id="js" style="background-color: gold; color: deeppink;">JavaScript</p>
	<p>TypeScript</p>
</div>
<button onclick="removeNode()">요소 노드 삭제</button>
<button onclick="removeAttr()">속성 노드 삭제</button>
<script>
    'use strict';
function removeNode(){
    const parent = document.getElementById('list');
    const removeItem = document.getElementById('item');
    const result = parent.removeChild(removeItem); // list에서 <p id="item">CSS</p> 제거

    console.log(result); // <p id="item">CSS</p> 반환
}
function removeAttr(){
    const js = document.getElementById('js');
    js.removeAttribute('style'); // js에서 style 속성을 제거
}
</script>
```

아무것도 누르지 않은 상태 ) <br>![js14_1](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js14_1.JPG?raw=true)

1번 버튼 누름 ) <br>![js14_2](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js14_2.JPG?raw=true)

2번 버튼 누름 ) <br>![js14_3](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js14_3.JPG?raw=true)

<br>

### 노드 복제

특정 노드를 복제하기 위해서는 cloneNode()를 사용한다. cloneNode()는 기본의 존재하는 노드와 동일한 새로운 노드를 생성하고 반환하게되는데 cloneNode(true)일 경우 복제되는 노드의 모든 속성과 자식 노드도 같이 복제하게되고 cloneNode(false)일 경우 속성 노드만 복제하고 자식 노드는 복제하기 않는다.

```javascript
<h3 id="item">복제된 아이템</h3>
<div id="list">
    <p>HTML</p>
    <p>CSS</p>
    <p>JavaScript</p>
    <p>node.js</p>
</div>
<button onclick="cloneElement()">노드 복제</button>
<script>
    'use strict';
function cloneElement(){
    const parent = document.getElementById('list');
    const originItem = document.getElementById('item');
    parent.appendChild(originItem.cloneNode(true)); // <h3 id="item">복제된 아이템</h3>를 복제하여 list의 자식요소에 추가한다.
}
</script>
```

아무것도 누르지 않은 상태 ) <br>![js14_4](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js14_4.JPG?raw=true)

버튼 누름 ) <br>![js14_5](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js14_5.JPG?raw=true)

F12키를 눌러 html 문서 구조 확인 ) <br>![js14_6](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js14_6.JPG?raw=true)


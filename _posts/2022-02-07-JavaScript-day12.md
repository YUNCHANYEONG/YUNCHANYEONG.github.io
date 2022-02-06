---
layout: single
title : JavaScript day12
categories : coding
tag : JavaScript
toc : false
---

DOM | 노드

<br>

### 문서 모델 객체(Document Object Model)

자바스크립트를 이용하여 웹 문서(HTML, XML 등)에 접근하고 제어할 수 있도록 객체를 이용해 웹 문서를 체계적으로 정리하는 방법으로, 문서 내의 모든 요소를 정의하고, 각각의 요소에 접근하는 방법을 제공한다.

<br>

#### DOM 트리

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title간단 문서</title>
    </head>
    <body>
        <h2>간단 문서</h2>
        <img src="images/me.jpg" alt="이미지설명">
    </body>
</html>
```

![js12_1](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js12_1.JPG?raw=true)

<br>

#### document 객체

웹페이지 자체를 의미하는 객체로 웹페이지에 존재하는 HTML 요소에 접근하고자 할 때 반드시 document 객체로 부터 시작한다.

|           종류           |                    설명                    |
| :----------------------: | :----------------------------------------: |
|  getElementsByTagName()  |     해당 태그 이름의 요소를 모두 선택      |
|     getElementById()     |           해당 Id의 요소를 선택            |
| getElementsByClassName() |    해당 클래스에 속한 요소를 모두 선택     |
|   getElementsByName()    | 해당 name 속성값을 가지는 요소를 모두 선택 |
|    querySelectorAll()    |  해당 선택자로 선택되는 요소를 모두 선택   |

```javascript
<ul>
    <li class="backend">Java</li>
    <li class="front">HTML</li>
    <li class="front">CSS</li>
    <li class="front">JavaScript</li>
    <li>JSP</li>
    <li class="backend">Spring</li>
    <li class="backend">Python</li>
    <li name="database">Mysql</li>
    <li name="database">Oracle</li>
    <li id="tool">Git</li>
</ul>

<script>
'use strict';

const tagName = document.getElementsByTagName("li");

for(let i = 0;i<tagName.length;i++){
	console.log(tagName[i]);
	tagName[i].style.color = "deeppink";
}

const id = document.getElementById("tool");
id.style.color = "gold";

const className = document.getElementsByClassName("front");
for(let i = 0;i<className.length;i++){
	console.log(className[i]);
	className[i].style.color = "deepskyblue";
}

const name = document.getElementsByName("database");
for(let i = 0;i<name.length;i++){
	console.log(name[i]);
	name[i].style.color = "yellowgreen";
}

const qs = document.querySelectorAll("li.backend");
for(let i = 0;i<qs.length;i++){
	console.log(qs[i]);
	qs[i].style.color = "black";
}
</script>
```

![js12_2](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js12_2.JPG?raw=true)

<br>

#### 노드

HTML DOM은 노드라고 불리는 계층적 단위에 정보를 저장하고 HTML 문서의 정보는 "노드트리"라고 불리는 계층적 구조에 저장한다. 노드트리는 노드들의 집합이며 최상위 레벨인 루트 노드로 부터 시작하고, 가장 낮은 텍스트 노드 까지 존재한다. 따라서 HTML DOM을 이용하여 노드트리에 포함된 모든 노드에 접근이 가능하다.

##### 노드 종류

| 종류        | 설명                                                         |
| ----------- | ------------------------------------------------------------ |
| 문서노드    | 문서 전체를 나타내는 노드                                    |
| 요소 노드   | HTML 요소를 나타내는 노드, 속성 노드를 가질 수 있는 유일한 노드 |
| 속성 노드   | HTML 요소의 속성을 나타내는 노드                             |
| 텍스트 노드 | HTML 문서의 모든 텍스트                                      |
| 주석 노드   | HTML 문서의 모든 주석                                        |

##### 노드간의 관계

|          종류          |         설명          |
| :--------------------: | :-------------------: |
|       parentNode       |       부모 노드       |
|        children        |       자식 노드       |
|       childNodes       |   자식 노드 리스트    |
|       firstChild       |   첫번째 자식 노드    |
|   firstElementChild    | 첫번째 자식 요소 노드 |
|       lastChild        |   마지막 자식 노드    |
|      nextSibling       |    다음 형제 노드     |
|   nextElementSibling   |  다음 형제 요소 노드  |
|    previousSibling     |    이전 형제 노드     |
| previousElementSibling |  이전 형제 요소 노드  |

```javascript
<div>
    <nav id="gnb">
        <ul>
            <li class="first">내용 - 1</li>
            <li>내용 - 2</li>
            <li>내용 - 3</li>
        </ul>
    </nav>
</div>
<script>
    window.onload = function(){  // html 문서가 모두 읽은 후에 실행하라.
    const gnb = document.getElementById('gnb');
    console.log(gnb);  // nav
    console.log(gnb.parentNode);  // div
    console.log(gnb.children[0]); // ul
    console.log(gnb.children[0].nextElementSibling); // null : ul 태크의 형제 요소는 없다.
    console.log(gnb.children[0].children[1]); // <li>내용 - 2</li>
    console.log(gnb.children[0].children[1].nextElementSibling); // <li>내용 - 3</li>
    console.log(gnb.children[0].firstChild); // #text : ul 옆으로 개행과 띄어쓰기가 포함됨.
    console.log(gnb.children[0].firstElementChild); // <li class="first">내용 - 1</li>
}
</script>
```


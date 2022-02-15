---
layout: single
title : JavaScript day16
categories : coding
tag : JavaScript
toc : false
---

이벤트 객체 | 이벤트 전파(Event Propagation)

<br>

### 이벤트 객체

특정 타입의 이벤트와 관련이 있는객체로 해당 타입의 이벤트에 대한 상세 정보는 저장한다. 모든 이벤트 객체는 이벤트의 타입을 나타내는 type 프로퍼티와 , 이벤트 대상을 나타내는 Target 프로퍼티를 가진다. 이벤트 객체는 이벤트 리스너가 호출 될 때 인수로 전달한다.

```javascript
<input type="button" id="btn" value="확인">

<script>
    'use strict';
    function clickBtn(e){
        console.log(e.target);     // <input type="button" id="btn" value="확인">
        console.log(e.target.id);  // btn
        console.log(e.target.value); // 확인
        console.log(e.type); // click
    }
    const btn = document.getElementById('btn');
    btn.addEventListener('click', clickBtn);
</script>
```

![js17_1](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js17_1.JPG?raw=true)

<br>

### 이벤트 전파(Event Propagation)

이벤트가 발생했을 때 브라우저가 이벤트 리스너를 실행시킬 대상 요소를 결정하는 과정으로 document 객체나 HTML 문서의 요소에서 이벤트가 발생하면 대상 요소를 결정하기 위해 이벤트 전파가 일어난다. 이벤트 전파 방식으로는 **버블링**, **캡처링** 두가지 방식이 있다.

**버블링**은 특정 요소에 이벤트가 발생하면 그 요소부터 가장 최상단의 조상 요소를 만날 때까지 상위 요소로 올라가면서 해당 이벤트가 전달되는 특성을 의미하고 그에 반해 **캡쳐링**은 이벤트 버블링과는 반대로 특정 요소에 이벤트가 발생하면 window 에서 시작해서 이벤트 타깃 요소를 만날 때까지 하위 요소로 내려가면서 해당 이벤트가 전달되는 특성을 의미한다.

먼저 버블링 방식을 예제를 통해 확인해보자.

```javascript
<div id="divBox">
        <p id="pBox">박스 안에 여러곳을 <span id="spanBox">클릭</span>하세요</p>
</div>
<p id="text"></p>

<script>
        'use strict';
    function clickDiv(e){
        document.getElementById('text').innerHTML += "<span style='color: red;'>div 요소를 클릭했어요</span><br>"
    }
    function clickP(e){
        document.getElementById('text').innerHTML += "<span style='color: blue;'>P 요소를 클릭했어요</span><br>"
    }
    function clickSpan(e){
        document.getElementById('text').innerHTML += "<span style='color: green;'>span 요소를 클릭했어요</span><br>"
    }
    document.getElementById('divBox').addEventListener('click', clickDiv);
    document.getElementById('pBox').addEventListener('click', clickP);
    document.getElementById('spanBox').addEventListener('click', clickSpan);
</script>
```

위 코드를 살펴보면 **divBox div박스** 안에 **pBox p태그**가 존재하고 그 안에 **spanBox span태그**가 존재한다. 이때 **span태그**를 누르게되면 하위요소부터 상위요소로 올라가면서  **p태그**와 **div박스** 순으로 이벤트가 전달된다. 

![js17_2](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js17_2.JPG?raw=true)

<br>

다음으로는 캡쳐링방식을 확인해보자.

```javascript
<div id="divBox">
        <p id="pBox">박스 안에 여러곳을 <span id="spanBox">클릭</span>하세요</p>
</div>
<p id="text"></p>

<script>
        'use strict';
    function clickDiv(e){
        document.getElementById('text').innerHTML += "<span style='color: red;'>div 요소를 클릭했어요</span><br>"
    }
    function clickP(e){
        document.getElementById('text').innerHTML += "<span style='color: blue;'>P 요소를 클릭했어요</span><br>"
    }
    function clickSpan(e){
        document.getElementById('text').innerHTML += "<span style='color: green;'>span 요소를 클릭했어요</span><br>"
    }
    document.getElementById('divBox').addEventListener('click', clickDiv, true);
    document.getElementById('pBox').addEventListener('click', clickP, true);
    document.getElementById('spanBox').addEventListener('click', clickSpan, true);
</script>
```

![js17_3](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js17_3.JPG?raw=true)

캡쳐링방식으로 이벤트를 실행해보면 상위 요소가 먼저 반응하고 그 하위 요소에게 순차적으로 전달되는 것이 확인 가능하다.

<br>

#### 이벤트 전파 방지

겹쳐있는 요소들간에 버블링과 캡쳐링 현상이 일어나는 것을 확인했다. 그럼 겹쳐있는 요소를 눌렀을 때 그 단일의 요소만 이벤트에 반응을 주고 싶을 땐 어떻게 할까

바로 전파를 방지해주는 메소드(**e.stopPropagation()**)를 사용하면된다.



```javascript
<div id="divBox">
    <p id="pBox">박스 안에 여러곳을 <span id="spanBox">클릭</span>하세요</p>
</div>
<p id="text"></p>

<script>
        'use strict';
    function clickDiv(e){
        e.stopPropagation();
        document.getElementById('text').innerHTML += "<span style='color: red;'>div 요소를 클릭했어요</span><br>"
    }
    function clickP(e){
        e.stopPropagation();
        document.getElementById('text').innerHTML += "<span style='color: blue;'>P 요소를 클릭했어요</span><br>"
    }
    function clickSpan(e){
        e.stopPropagation();
        document.getElementById('text').innerHTML += "<span style='color: green;'>span 요소를 클릭했어요</span><br>"
    }
    document.getElementById('divBox').addEventListener('click', clickDiv);
    document.getElementById('pBox').addEventListener('click', clickP);
    document.getElementById('spanBox').addEventListener('click', clickSpan);
</script>
```

![js17_4](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js17_4.JPG?raw=true)

위 처럼 span 태그를 누를 경우에 중첩되있기 때문에 버블링 현상이 일어나야하지만 부모요소로 이벤트 전파를 방지하였기 때문에 오로지 span 태그의 이벤트만 반응한다.


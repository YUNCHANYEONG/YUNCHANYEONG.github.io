---
layout: single
title : JavaScript day1
categories : coding
tag : JavaScript
toc : false
---

JavaScript란 \| 출력 \| 주석 \| 외부자바스크립트

<br>



### 자바스크립트(JavaScript)

자바 스크립트는 모질라 재단의 프로토타입 기반의 프로그래밍 언어로, 스크립트 언어에 해당된다. HTML은 웹 문서의 내용을 구성하고, CSS는 웹 문서의 레이아웃이나 색상, 스타일 등을 지정한다. 자바스크립트를 추가하면 웹 무서의 각 요소를 가져와 필요에 따라 스타일을 변경하거나 움직이게 할 수 있다. 웹 문서를 자동차에 비유하자면, HTML은 자동차의 뼈대, CSS는 자동차의 외관, JavaScript는 자동차의 동력이라고 볼 수 있다. 객체 기반의 스크립트 프로그래밍 언어로 웹 브라우저 내에서 주로 사용되며, 다른 응용 프로그램의 내장 객체에도 접근할 수 있는 기능을 가지고 있다. 

웹 문서에는 자바스크립트 소스를 읽고 처리하는 해석기가 있다. 자바스크립트 소스는 웹 문서에서 \<script> 태그를 이용해 자바 스크립트 소스가 짧은 경우 웹 문서에서 자바 스크리브를 실행할 위치에 바로 작성할 수 있다. 



#### 자바스크립트 출력

**HTML 문서에 출력**<br>document.write() 함수를 통해 출력

**console에 출력**<br>console.log() 함수를 통해 출력

#### 자바스크립트 주석

**한줄 주석** : //<br>**여러줄 주석** : /* ... */

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>자바스크립드의 출력</title>
</head>
<body>
    <h2>자바스크립드의 출력</h2>
    <script>
        /*
            날짜 : 2021-12-27
            작성자 : 윤OO
            비고 : 자바스크립트의 출력
        */
        document.write('<p>안녕하세요. 자바스크립트입니다.</p>');    // body에 출력
        console.log('안녕하세요. Javascript!');  				// console에 출력
    </script>
</body>
</html>
```

![js1_1](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js1_1.JPG?raw=true)<br>콘솔에 출력한 결과값을 확인하는 방법은 F12키를 누르고 console 칸에서 확인이 가능하다.<br>![js1_2](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js1_2.JPG?raw=true)



#### 외부 스크립트

자바 스크립트도 CSS 처럼 link를 통해 외부 스크립트를 연결할 수 있다. 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>외부 자바스크립트</title>
    <script src="./js/script.js"></script> <!--외부 링트 연결-->
</head>
<body>
    <h2>외부 자바스크립트</h2>
</body>
</html>
```

```javascript
console.log('외부에 연결된 스크립트입니다. 모두 화이팅 해봐요')
```

![js1_3](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js1_3.JPG?raw=true)



#### 대화상자

**alert()**<br>웹 브라우저에서 작은 알림창을 열어 사용자에게 메시지를 보여주고 확인을 기다리는 방법이다.

```javascript
alert('안녕하세요?');
```

![js1_4](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js1_4.JPG?raw=true)



**confirm()**<br>알림창은 단순히 메시지를 보여주는 기능만 하지만 확인차은 사용자가 **확인**이나 **취소** 버튼 중에서 직접 클릭할 수 있다. 확인을 누를 경우 **true**, 취소를 누를 경우 **false**를 반환한다.

```javascript
confirm('확인 또는 취소를 눌러주세요.');
```

![js1_5](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js1_5.JPG?raw=true)



**prompt()**<br>프롬프트 창은 텍스프 필드를 포함하고 있는 창이다. 텍스트 필드 안에 간단한 메시지를 입력후 결과를 반환한다.

```javascript
prompt('이름을 입력하세요');
```

![js1_6](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js1_6.JPG?raw=true)

![js1_7](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js1_7.JPG?raw=true)



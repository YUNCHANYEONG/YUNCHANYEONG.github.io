---
layout: single
title : ChartJS
categories : coding
tag : ChartJS
toc : false
---

Chart JS

<br>

### Chart JS

**chartJS**는 html 웹 문서를 작성하면서 차트를 만들어 넣고 싶을 때 사용되는 스크립트중 하나이다.

chartJS를 사용하기 사전 설치 작업이 필요하다.  설치하는 방법으론 여러방법이 있지만 가장 쉽고 편한 방법인 CDN 코드를 넣는 방법을 선택하여 설치를 해보면

https://cdnjs.com/libraries/Chart.js

위 링크를 들어가서 맨 위에있는 코드를 복사해온다. 현재 작성자의 최신 버전은 아래와 같다.

![chartJS1_1](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/chartJS1_1.JPG?raw=true)

```javascript
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/3.7.1/chart.min.js" integrity="sha512-QSkVNOCYLtj73J4hbmVoOV6KVZuMluZlioC+trLpewV8qMjsWqlIQvkn1KGX2StWvPMdWGBqim1xlC8krl1EKQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
```



<br>

이제 코드를  작성하보자.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ChartJS</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js" integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4=" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/3.7.1/chart.min.js" integrity="sha512-QSkVNOCYLtj73J4hbmVoOV6KVZuMluZlioC+trLpewV8qMjsWqlIQvkn1KGX2StWvPMdWGBqim1xlC8krl1EKQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
</head>
<body>
    <div class="container">  
        <canvas id="line-chart"></canvas>
      </div>
</body>
</html>
```

```css
.container{ /*차트 상위 블록을 만들어 블록을 이용하여 크기를 지정한다.*/
    width: 400px;
    height: 400px;
    border:1px solid #ebebeb;
    border-radius:10px;
    padding:20px;
}
```

```javascript
var target = $('#line-chart');

const labels = [ // key값 지정
  '3월',
  '5월',
  '6월',
  '9월',
  '10월',
  '수능',
];

const data = {
  labels: labels,
  datasets: [
    {
    label: 'STUDENT',
    pointRadius:5,
    pointHoverRadius:10,
    backgroundColor: 'rgba(255, 99, 132,0.5)',
    hoverBackgroundColor:'rgba(255, 99, 132,1)',
    borderColor: 'rgb(255, 99, 132)',
    borderDash:[20,5],
    data: [289, 278, 256, 278, 329, 293, 311], // 데이터(value) 넣어주는 장소
  }
  ]
};

const config = {
  type: 'line', // 타입은 차트의 모양을 선형(line) 차트로 할 것인지, 막대(bar)차트로 할 것인지 설정 가능하다. 
  data: data,
  options: {
    maintainAspectRatio:false
  }
};
var myChart = new Chart(
    target,
    config
  );
```

![chartJS1_2](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/chartJS1_2.JPG?raw=true)

이렇게 선형 차트가 만들어졌다.

<br>

선형 차트에 배경을 넣어보자.

```javascript
const data = {
  labels: labels,
  datasets: [
    {
    label: 'STUDENT',
    pointRadius:5,
    pointHoverRadius:10,
    backgroundColor: 'rgba(255, 99, 132,0.5)',
    hoverBackgroundColor:'rgba(255, 99, 132,1)',
    borderColor: 'rgb(255, 99, 132)',
    borderDash:[20,5],
    fill:true, // 배경 넣기
    data: [289, 278, 256, 278, 329, 293, 311],
  }
  ]
};
```

![chartJS1_3](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/chartJS1_3.JPG?raw=true)

<br>

막대 타입의 차트도 만들어 보자. 막대차트는 type에서 bar로 변경만 해주면된다.

```javascript
const config = {
  type: 'bar', // 변경 부분
  data: data,
  options: {
    maintainAspectRatio:false
  }
};
```

![chartJS1_4](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/chartJS1_4.JPG?raw=true)

<br>

만약 두개의 차트를 동시에 나타내고 싶다면

```javascript
const data = {
  labels: labels,
  datasets: [
    {
    label: 'STUDENT1',
    pointRadius:5,
    pointHoverRadius:10,
    backgroundColor: 'rgba(255, 99, 132,0.5)',
    hoverBackgroundColor:'rgba(255, 99, 132,1)',
    borderColor: 'rgb(255, 99, 132)',
    borderDash:[20,5],
    fill:true,
    data: [289, 278, 256, 278, 329, 293, 311],
  }
  ,{
    label: 'STUDENT2',
    pointRadius:5,
    pointHoverRadius:10,
    backgroundColor: 'rgba(0, 0, 255,0.5)',
    hoverBackgroundColor:'rgba(0, 0, 255,0.5)',
    borderColor: 'rgba(0, 0, 255,0.5)',
    borderDash:[20,5],
    data: [222, 333, 300, 280, 360, 211, 290],
  }
  ]
};
```

이런식으로 데이터를 연달아서 넣어주면된다.

![chartJS1_5](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/chartJS1_5.JPG?raw=true)


---
layout: single
title : JavaScript day9
categories : coding
tag : JavaScript
toc : false
---

자바스크립트 내장객체 \| Math 객체 | String 객체

<br>



### 자바스크립트 내장객체

자바스크립트의 내장 객체는 객체 생성없이 사용 가능한 객체를 의미한다.

<br>

#### Math 객체

수학에서 자주 사용하는 상수와 함수들을 다룰 수 있도록 하였다.

**min()**<br>\- 최소값을 반환<br>\- 매개변수가 전달되지 않으면 Infitiy를 반환<br>\- 비교할 수 없는 값이 포함되어 있으면 NaN을 반환

**max()**<br>\- 최대값을 반환<br>\- 매개변수가 전달되지 않으면 -Infitiy를 반환<br>\- 비교할 수 없는 값이 포함되어 있으면 NaN을 반환

**round()**<br>
\- 소수점 첫번째 자리에서 반올림하여 반환

**floor()**<br>\- 소수점 첫번째 자리에서 내림

**ceil()**<br>\- 소수점 첫번째 자리에서 올림

**random()**<br>\- 0보다 크거나 같고 1보다 작은 무작위 소수를 반환

```javascript
console.log(Math.min());  // Infinity
console.log(Math.min(1,10,-10,100,0));  // -10
console.log(Math.min(1,10,"-10",100,0));  // -10 : 자동형변환
console.log(Math.min(1,10,"마이너스십",100,0));  // NaN

console.log(Math.max());  // -Infinity
console.log(Math.max(1,10,-10,100,0));  // 100
console.log(Math.max(1,10,-10,"100",0));  // 100 : 자동형변환
console.log(Math.max(1,10,"마이너스십",100,0));  // NaN

console.log(Math.round(10.49));  // 10
console.log(Math.round(10.5));   // 11
console.log(Math.round(-10.5));  // -10
console.log(Math.round(-10.51));  // -11

console.log(Math.floor(10.49));  // 10
console.log(Math.floor(10.5));   // 10
console.log(Math.floor(-10.5));  // -11
console.log(Math.floor(-10.51));  // -11

console.log(Math.ceil(10.49));  // 11
console.log(Math.ceil(10.5));   // 11
console.log(Math.ceil(-10.5));  // -10
console.log(Math.ceil(-10.51));  // -10

const rand = Math.random();
console.log(rand);  // 0.5082535274834281
console.log(Math.floor(rand*10) +1); // 5 : 1~10사이의 자연수
```

<hr>


#### String 객체

문자열을 쉽게 만들고 다룰 수 있도록한다.



**length**<br>\- 문자열의 길이를 저장하는 프로퍼티

**indexOf()**<br>\- 매개변수로 전달된 문자열이 처음 등장하는 위치를 반환

**charAt()**<br>
\- 매개변수로 전달된 인덱스에 위치한 문자를 반환

**substring()**<br>\- 매개변수로 전달된 시작 인덱스부터 종료 인덱스 바로 앞까지 문자열을 추출<br>\- 매개변수가 1개인 경우 해당 인덱스 끝까지 문자열을 추출

**sudstr()**<br>\- 매개변수로 전달된 시작 인덱스부터 전달된 갯수만큼 문자열을 추출하여 반환

**split()**<br>\- 매개변수로 전달된 구분자를 기분으로 문자열을 나눈 후 하나의 배열에 저장

**replace()**<br>\- 원본 문자열을 매개변수로 전달된 문자열로 치환

**trim()**<br>\- 문자열의 앞뒤 공백을 제거

```javascript
rconst str1 = "안녕하세요. javascript";
console.log(str1);  // 안녕하세요. javascript
console.log(str1.length);  // 17
console.log(str1.indexOf('j'));  // 7
console.log(str1.indexOf('J'));  // -1 : 찾지못함
console.log(str1.indexOf('a'));  // 8
console.log(str1.lastIndexOf('a'));  // 10
console.log(str1.charAt('7'));  // j  -> 7
console.log(str1.includes('java'));  // true
console.log(str1.substring('7'));  // javascript, 인덱스 7번부터 끝까지
console.log(str1.substring('7,11'));  // java, 인덱스 7번부터 11번 앞까지

const str2 = '홍길동😍이순신😍장금이😍장영실';
const student = str2.split('😍');
console.log(student);  // (4) ['홍길동', '이순신', '장금이', '장영실'] -> 배열
for(let stu in student){
	console.log(stu, student[stu]); 
    /*
            0 홍길동
            1 이순신
            2 장금이
            3 장영실
    */
}

console.log(str1.replace('안녕하세요','Hello')); //Hello. javascript -> 영구적으로 바뀌는것은 아님
console.log(str1.replace('안녕하세요','Hello').charAt('1'));  // e

const str3 = '         javascript         ';
console.log(`🎃${str3}🎃`);  // 🎃         javascript         🎃
console.log(`🎃${str3.trim()}🎃`); // 🎃javascript🎃
```


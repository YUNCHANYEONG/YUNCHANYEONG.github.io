---
layout: single
title : JavaScript day4
categories : coding
tag : JavaScript
toc : false
---

if \| switch \| for \| while

<br>



### 조건문

프로그래밍 진행중에 특정 조건과 명령에 따라 실행 순서가 결정된다.

**if**<br>if문 괄호 안에 조건을 넣어 결과값이 참이면 if문을 실행하고 false면 if문을 실행하지않고 통과한다. else if는 처음 if문의 조건식에서 false가 나올 경우 else if의 조건식을 체크하여 true면 else if문을 실행하게된다. else if의 조건식도 false가 나올 경우 else문을 실행한다.

```javascript
const age = Number(prompt('나이를 입력하세요'));  // 15 입력
if(age>19){
    console.log('성인입니다');
}else if(age>14){
    console.log('청소년입니다')
}else if(age>6){
    console.log('어린이입니다')
}else{
    console.log('유아입니다')
}
//--------------------------------------------
// 콘솔 출력 : '청소년입니다'
```

<br>

**switch**<br>switch문은 조건을 확인하여 그에 맞는 case의 명령어를 실행하게된다.

```javascript
const select = prompt('유아, 어린이, 청소년, 성인 중 선택하세요'); // 청소년
let price = "";

switch(select){
    case '유아':
        price = "입장료 무료";
        break;
    case '어린이':
        price = "입장료 : 2000원";
        break;
    case '청소년': 				
        price = "입장료 : 5000원";
        break;
    case '성인':
        price = "입장료 : 10000원";
        break;
    default:
        alert('입력값을 확인하세요');
        price = '입력값 오류!';
}
console.log(price);
//--------------------------------------------
// 콘솔 출력 : '입장료 : 5000원'
```

<br>

### 반복문

반복되는 코드를 하나로 간단화하여 작성하는 방법이다.



**for**<br>for문은 **초기값**과 **조건식**, **증감식**으로 이루어져있다. **초기값**은 카운터 변수를 초기화해주고 **조건식**은 명령을 반복하기위해 조건을 확인해고 **증감식**은 명령을 반복할때마다 카운터 변수를 증감해준다.

```javascript
let sum = 0;
for(let i =1; i<= 100;i++){
    sum += i;
}
console.log(`1~100까지의 합 : ${sum}`);
//--------------------------------------------
// 콘솔 출력 : '1~100까지의 합 : 5050'
```

<br>

**while**<br>조건식이 ture인 경우 반복하게되고 조건식이 false일 경우에는 반복을 하지않는다. do~while은 조건식이 맨 아래 붙어 처음 한번은 반복하고 조건식을 확인한다. 조건식이 항상 true일 경우 무한 반복이 됨으로 유의해야한다.

```javascript
const dan = Number(prompt('원하는 단을 입력하세요.')); // 2
console.log(`${dan}단`);

let i =1;
while(i<=9){
    console.log(`${dan} * ${i} = ${dan * i}`);
    i++;
}
//--------------------------------------------
// 콘솔 출력 : 
            2 * 1 = 2
            2 * 2 = 4
            2 * 3 = 6
            2 * 4 = 8
            2 * 5 = 10
            2 * 6 = 12
            2 * 7 = 14
            2 * 8 = 16
            2 * 9 = 18
```


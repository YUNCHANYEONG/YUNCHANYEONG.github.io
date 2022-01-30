---
layout: single
title : JavaScript day6
categories : coding
tag : JavaScript
toc : false
---

함수 선언과 호출 \| 화살표 함수

<br>



### 함수

함수는 하나의 특별한 목적의 작업을 수행하도록 설계된 독릭적인 블록을 의미하고 필요할때 마다 호출하여 해당 작업을 반복해서 수행하기때문에 코드를 재활용할 수 있다. 함수는 먼저 선언하고 그 함수를 호출하는 방식으로 선언하는 방법으로는 **함수 선언식**과 **함수 표현식**이다.

```javascript
// 함수 선언식
function 함수명(매개변수1, 매개변수2 .. ){
    ...
    return 값;
}
```

```javascript
// 함수 표현식
const 함수명 = function(매개변수1, 매개변수2 .. ){
    ...
    return 값;
}
```

<br>

웹 브라우저에서 자바 스크립트 소스를 해석할 때에는 함수 선언 부분을 가장 먼저 하기 때문에 함수를 선언만 해놓으면 선언한 위치에 상관없이 함수 호출이 가능하다.

```javascript
addNember();

function addNumber(){
}
```

```javascript
function addNumber(){
}

addNember();
```

위 처럼 코드들은 함수 선언과 호출의 위치가 다르지만 동일하게 실행되는 코드로, 선언의 위치는 프로그램 흐름에 영향을 주지않는다.

 <br>

함수를 어떻게 사용하는지 예제를 통해 알아보자.

```javascript
function func1(){
	console.log('func1 함수 호출')
}
function func2(num){
	console.log(`전달 받은 매개변수의 값 : ${num}`)
}
function func3(start, end){
    let sum = 0;
    for(let i=start ; i<=end ; i++){
    	sum += i;
	}
	console.log(`${start}부터 ${end}까지의 총합은 ${sum}입니다`)
}

func1(); // func1 함수 호출
func2(10); // func2 함수 호출
func3(1, 100); // func3 함수 호출
```

![js6_1](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js6_1.JPG?raw=true)

위 처럼 함수는 자바처럼 함수 호출간 매개변수를 보내고 함수는 매개변수를 받아 사용할 수 있다. 

 <br>

함수는 활용하는 여러방법이 있는다. 함수를 호출할 때 매개변수를 정하지 않으면 대신 함수 선언시 입력한 기본값(디폴드값)을 변수에 저장하는 방법이 있고 생략 접두어를 선언시 사용하여 특정 위치의 인수부터 마지막 인수까지 한번에 지정하여 배열로 활용가능한 방법이 있다.

```javascript
function func1(name='무명'){	// 매개변수에 아무것도 들어있지 않는다면 기본값으로 '무명'을 집어넣겠다는 의미
    console.log(`당신의 이름은 ${name}입니다.`);
}

function func2(num1, ...num2){	// num1까지는 정상적으로 매개변수를 받고 그 외에 나머지는 배열로 처리하겠다는 의미
    console.log(`num1의 값 :  ${num1}`);
    console.log(`num2의 값 :  ${num2}`);
}

function func3(...jumsu){ // 모든 매개변수를 배열로 처리
    let total = 0;

    for(let i in jumsu){
        total += jumsu[i];
    }
    console.log(`총점 : ${total}`);
}

func1('김사과');
func1(); 

func2(10, 30, 20, 70, 100);
func3(80,90,70, 100, 20);
```

![js6_2](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js6_2.JPG?raw=true)

 <br>

 <br>

#### 화살표 함수

화살표 함수는 function 키워드를 사용하여 함수를 만드는 것 보다 간단히 표현한 함수 방식으로 항상 익명 함수의 모습니다.

```javascript
// 매개변수가 없는 경우
const func1 = () => 실행문;

// 매개변수가 있는 경우
const func2 = x => 실행문;
const func3 = (x, y) => 실행문;

// 리턴값이 있는 함수
const func4 = (x, y) => {
    실행문;
    return 값;
}
```

 <br>

화살표 함수의 예제를 살펴보자.

```javascript
const func1 = () => console.log('안녕하세요');
const func2 = (x, y) => console.log(`두 수의 합 : ${x + y}`);
const func3 = (x, y) => {
        let sum = 0;
        for(let i = x ; i <= y ; i++){
            sum += i;
        }
        return sum;
    }
  
func1();
func2(10, 5);
console.log(func3(1,10));
```

![js6_3](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js6_3.JPG?raw=true)
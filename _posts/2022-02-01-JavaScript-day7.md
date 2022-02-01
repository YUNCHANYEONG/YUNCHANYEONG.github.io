---
layout: single
title : JavaScript day7
categories : coding
tag : JavaScript
toc : false
---

변수의 범위 \| 호이스팅

<br>



### 변수의 범위

**지역변수**<br>함수 내에서 선언된 변수로 지연변수는 변수가 선언된 함수내에서 유효하고 함수가 종료되면 메모리에서 사라진다.

```javascript
function func1(x, y){
        let sum = 0; // 지역변수
        ...
        console.log(x, y, sum); // 값 출력
    }
console.log(x, y, sum); // undefined
```

이때 sum이 지역 변수임으로 함수밖에서는 sum을 사용할 수 없어 undefined가 출력된다.

<br>

**전역변수**<br>함수의 외부에서 선언된 변수로 전역변수는 프로그램의 어느 영역에서나 접근 할 수 있으며, 웹 페이지가 닫혀야만 메모리에서 사라진다.

```javascript
let global = 0; // 전역변수
function func1(x, y){
    console.log(global); // 값 출력
}
console.log(global); // 값 출력
```

이때는 변수 global은 함수밖에서 선언한 전역 변수임으로 함수 안 밖으로 사용 가능하다.

<br>

변수타입 var와 let의 차이를 알아보자.

```javascript
var num1 = 50;  // 전역변수
if(num1 == 50){ // var는 블록에서는 전역변수를 사용함. 함수에서는 전역, 지역변수를 사용함.
    var num1 = 100;                // 전역변수
    console.log(`num1 : ${num1}`); // 전역변수 100
    num1 = 200;                    // 전역변수 200
    console.log(`num1 : ${num1}`); // 전역변수 200
}
console.log(`num1 : ${num1}`);	 // 전역변수 200
```

위 코드들을 보면 var를 사용하면 함수 내에서 같은 이름의 변수를 선언하여도 지역변수가 아닌 전역변수로 선언되는 것을 확인 할 수있다. 따라서 함수 이전에 선언한 전역변수의 값을 계속 변경되어 나중되면 혼란을 빚을 수 있다. 

```javascript
let num2 = 50;  // 전역변수
if(num2 == 50){
    let num2 = 100;                // 지역변수
    console.log(`num2 : ${num2}`); // 지역변수 100
    num2 = 200;                    // 지역변수 200
    console.log(`num2 : ${num2}`); // 지역변수 200
}
console.log(`num2 : ${num2}`); // 전역변수 50
```

그러나 let를 사용하게 되면 함수내에서 같은 이름의 변수를 선언하면 앞서 선언한 전역변수와 별개로 지역변수를 선언함으로 함수 내에서 지역변수를 사용하고 전역변수에는 영향을 주지않는 차이점이 있다. 이처름 var를 사용한 변수를 재선한 할 수 있는 실수를 방지하고자 var보다는 let의 사용을 더 권장한다.

<br>

### 호이스팅

자바 스크립트에서 변수 사용간 또 조심해야할 개념이 **호이스팅**이다. 호이스팅은 코드가 실행되기 전 변수 선언/함수선언을 최상단으로 끌러올려지는 것 같은 현상을 얘기하며 **var타입 사용**, **함수 선언식**이 호이스팅이 일어난다.

```javascript
var x = 10;
function number(){
    console.log("x =" + x);  // x = 10
    console.log("y =" + y);  // y = undefined
    var y = 20;
}
number();
```

이처럼 이미 y의 값을 출력하기전에 프로그램은 y가 선언된 것과 같은 값(할당은 되지않은 자료형, undefiend)을 출력한다. 이러한 현상을 호이스팅이라한다. 그렇기에 var타입을 사용하기 위해서는 선언에 신중할 필요하가 있다.

 하지만 let 타입을 사용하게 된다면 호이스팅의 영향을 받지않는다. 

```javascript
let x = 10;
function number(){
    console.log("x =" + x);  // x = 10
    console.log("y =" + y);  // 오류발생
    let y = 20;
}
number();
```

이처럼 호이스팅 현상이 나타나지않고 프로그램은 혼돈을 막기 위해 오류를 출력한다. let를 사용한다면 프로그램 하는데 있어서 더욱 안전하게 변수를 사용할 수 있다.

<br>

함수 선언식에서도 호이스팅 현상을 볼 수 있다.

```javascript
func1(); // 함수 이전에 호출해도 미리 script는 함수의 존재를 알고있기때문에 호출이 가능하다.
function func1(){  // 함수 선언식, script를 만나면 미리 선언됨.
	alert('func1 호출되었음');
}
func1(); // 호출
```



그럼 함수 표현식을 보면

```javascript
// func2(); // 함수 이전에 호출해도 호출 되지않는다.
const func2 = function(){  // 함수 표현식, script를 만나도 미리 선언되지 않음.
	alert('func2 호출되었음');
}
func2(); // 호출
```

함수 표현식은 프로그램이 미리 함수의 존재에 대해 알지 못하기 때문에 함수보다 이전에 호출될 경우 오류를 출력하게 된다.
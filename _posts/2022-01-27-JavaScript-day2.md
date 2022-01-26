---
layout: single
title : JavaScript day2
categories : coding
tag : JavaScript
toc : false
---

변수 \| 상수 \| 테이터타입

<br>



### 변수

변수랑 데이터를 저장하여 담을 수 있는 메모리 공간을 의미한다. 변수를 사용하려면 변수에 이름을 붙여 주어야하는데 , 이것을 변수 선언이라고 하는데 자바 스크립트에서 변수를 선언할 때는 지켜야 할 몇가지 규칙이 있다. 변수 선언의 규칙을 알아보자.

1. 변수 이름은 영머 무낮와 언더바(\_), 숫자를 사용한다. 단 변수 이름 첫 글자는 영어 대소문자나 언더바(\_)만 쓸 수 있고 숫자, 기호 띄어쓰기는 허용하지 않는다.
2. 대소문자를 구별하고 예약어는 변수 이름으로 쓸 수 없다. var, let, const, while .. 등 예약어는 불가능하다.
3. 여러 단어를 연결한 변수 이름은 중간 글자 어미를 대문자로 적는다. 예로 currentYear, CurrentYear, current_Year, Current_Year 처럼 사용할 수 있다.
4. 변수 이름은 의미 있게 작성해야한다. 개발 코드를 누군가가 봤을 때 이 변수가 어떤 값을 담고 있는지 예측할 수 있는 이름이면 좋다. 숫자는 num, 나이는 age 처럼 사용하면 누구든 추측이 가능하다.

**변수 선언**

```javascript
let 변수명; // 변수 선언
변수명 = 값; // 변수 초기화
let 변수명 = 값; // 선언과 초기화 동시에 표현 가능 
```

```javascript
<script>
    'use strict' // strict mode를 사용한다는 의미로 변수 사용이 엄격해짐
    let num;
    num = 10;
    console.log(num); // 데이터를 담은 변수를 콘솔에 출력하는 방법
</script>
```

![js2_1](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js2_1.JPG?raw=true)



### 상수

상수는 한번 선언되면 다시 재정의 할 수 없고 값도 재할당 할 수 없는 것을 말한다. 자바스크립트는에서는 변수보다 상수를 더 많이 사용하게된다.

```javascript
const 상수명;
상수명 = 값; // 에러, 선언과 초기화를 동시에 해줘야된다.
-------------------------------
const 상수명 = 값; // 가능
```

```javascript
<script>
    const str = "일";
    console.log(str);

    const obj = {id:'apple', name:'김사과'}; // 키값 쌍으로 기입하면 객체 생성 가능
    console.log(obj);  // {id: 'apple', name: '김사과'}
    
    obj.id = 'banana';
    obj.name = '반하나';
    console.log(obj);  // {id: 'banana', name: '반하나'}
</script>
```

상수는 객체의 값을 바꾸지 못하는 것이 아닌 객체를 가르키는 주소를 바꾸지 못하게 하는 것임으로 위에서 주소를 바꾸는 것이 아닌 객체 내용을 바꾸는 것이기 때문에 가능하다.

![js2_2](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js2_2.JPG?raw=true)



### 데이터 타입

**숫자형(number)**<br>

정수와 실수를 따로 구분하지않고 모든 수를 실수 하나로만 표현 가능하다. typeof()는 타입을 반환해주는 함수로 타입 확인간 사용한다.

```javascript
<script>
    'use strict';
        const num1 = 10;
        const num2 = 11.11;
        const num3 = 10e6;
        console.log(num1);  // 10
        console.log(num2);  // 11.11
        console.log(num3);  // 10000000
        console.log(typeof(num1));  // number
        console.log(typeof(num2));  // number
        console.log(typeof(num3));  // number
</script>
```

![js2_3](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js2_3.JPG?raw=true)



**문자열형(string)**<br>따옴표로 둘러싸인 문자의 집합으로 작은 따옴표든 큰 따옴표든 상관하지 않는다. 

```javascript
<script>
    'use strict';
        let str1 = "홍길동 : '어려분 안녕하세요?'";
        let str2 = '홍길동 : "어려분 안녕하세요?"';
        let str3 = "홍길동 : \"어려분 안녕하세요?\"";
        let str4 = `여러분 안녕하세요?
        이번주도 화이팅해봐요!
        자바스크립트 화이팅~`;

        console.log(str1); // 홍길동 : '어려분 안녕하세요?'
        console.log(str2); // 홍길동 : "어려분 안녕하세요?" 
        console.log(str3); // 홍길동 : "어려분 안녕하세요?" 
        console.log(str4);
        /*
        여러분 안녕하세요?
        이번주도 화이팅해봐요!
        자바스크립트 화이팅~
        */
</script>
```

![js2_4](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js2_4.JPG?raw=true)



**불리언형(boolean)**<br>참 또는 거짓으로 표현되는 값이다.

```javascript
<script>
    'use strict';
        const b1 = true;
        const b2 = false; 

        console.log(b1); // true 
        console.log(b2); // false 
        console.log(typeof(b1)); // boolean

        const b3 = 10 > 5;
        console.log(b3); // true 
</script>
```

![js2_5](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js2_5.JPG?raw=true)



**undefined, null 형**<br>undefined은 자료형이 정의되지 않았을 때의 데이터 상태(변수에 값이 할당되지 않았은 상태)를 의미한다. null은 변수에 할당된 값이 유효하지 않음을 의미한다.

```javascript
<script>
    'use strict';
        let num;
        console.log(num); //undefined
        console.log(typeof(num)); //undefined

        let obj1 = null;
        console.log(obj1); //null
        console.log(typeof(obj1)); //object
</script>
```

![js2_6](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js2_6.JPG?raw=true)



**객체형**<br>여러 속성을 하나의 변수에 저장할 수 있도록 해주는 타입으로 키와 값의 구조로 저장한다.

```javascript
<script>
    'use strict';
        const dog = {"name":"ttotto", "age":12, "family":"퍼그"};
        console.log(dog);  

        console.log(dog.name);
        console.log(dog.age);
        console.log(dog.family);

        dog.age = 11;
        console.log(`또또의 2022년 나이는 ${dog.age}살 입니다.`);
</script>
```

![js2_7](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js2_7.JPG?raw=true)



**심볼형**<br>심볼형은 유일하고 변경 불가능한 기본값을 만들어 객체 속성의 key값으로 사용할 수 있다.

```javascript
<script>
    'use strict';
        const symbol1 = Symbol('apple');
        const symbol2 = Symbol('apple');
        console.log(symbol1 === symbol2);  // false
        console.log(typeof(symbol1));      // symbol1
        console.log(typeof(symbol2));      // symbol2

        const symbol3 = Symbol('banana');
        const symbol4 = symbol3;           // 주소값을 같은 곳으로함.
        console.log(symbol3 === symbol4);  // true
</script>
```

![js2_8](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/js2_8.JPG?raw=true)


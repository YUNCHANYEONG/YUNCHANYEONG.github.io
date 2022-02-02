---
layout: single
title : JavaScript day8
categories : coding
tag : JavaScript
toc : false
---

객체 생성 방법

<br>



### 객체

객체란 연관서이 있는 데이터들의 정의 할 수 있는 변수와 메소드들의 집합으로 자바스크립트의 객체는 데이터를 저장하고 처리하는 기본단위이다. 

객체의 구성으로는 **프로퍼티**와 **메서드**라는 개념이 있는데 쉽게 말해 프로퍼티는 객체의 특징이나 속성을 나타내고, 메서드는 객체에서 할 수 있는 동작을 표현한다. 객체 내의 변수를 프로퍼티라고 부르고 함수를 프로퍼티 메소드라 부른다.

<br>

#### 객체를 만드는 방법

\- **리터럴 표기법**

```javascript
const 객체명 = {}; // 빈 객체 생성
const 객체명 = {
    프로퍼티명1 : 값1,
    프로퍼티명2 : 값2,
    ...

    프로퍼티메소드명1:function(){
    ...
    }
}
```

```javascript
const dog = {
    name : '퍼그',
    age : 7,
    color : 'white',
    weight : 3.5
}
console.log(dog.name); //퍼그
console.log(dog.age); //7
console.log(dog.color); //white
console.log(dog.weight); //3.5
```

<br>

\- **생성자를 이용한 객체 생성**

new 연산자를 사용하여 객체를 생성하고 초기화 할 수 있다. 이때 생성자는 메소드이고 이 메소드는 새롭게 생성되는 객체를 초기화하는 역할을 한다.

```javascript
function 생성자명(매개변수1, 매개변수2 ..){
    this.프로퍼티명1 = 값1;
    this.프로퍼티명2 = 값2;
    ...
    this.프로퍼티메소드명1 = function(){
        ...
    }
}

const 객체명1 = new 생성자명(값1, 값2 ..);
const 객체명2 = new 생성자명(값1, 값2 ..);
```

```javascript
function Dog(name, color){
    this.name = name;
    this.color = color;
    this.sleep = function(){
        return `${this.name}이(가) 잠을 잡니다.`;
    }
}

const Rucy = new Dog('퍼그', '갈색');
console.log(Pug.name); // 퍼그
console.log(Pug.color); // 갈색
console.log(Pug.sleep); 
/*
ƒ (){
    return `${this.name}이(가) 잠을 잡니다.`;
}
*/
console.log(Pug.sleep()); // 퍼그가 잠을 잡니다.
```

<br>

\- **클래스를 이용한 객체 생성**

```javascript
const 클래스명 = class {
    constructor(매개변수1, 매개변수2 ..){
        this.프로퍼티명1 = 값1;
        this.프로퍼티명2 = 값2;
        ...
    }
    메소드명(매개변수1, 매개변수2 ..){

    }
    ...
}

const 객체명1 = new 클래스명(값1, 값2 ..);
const 객체명2 = new 클래스명(값1, 값2 ..);
```

```javascript
const Dog = class{
    constructor(name, age, color){
        this.naem = name;
        this.age = age;
        this.color = color;
    }
    play(){
        return `${this.name}가 즐겁게 놉니다.`;
    }
}

const Rucy = new Dog('퍼그', 10, '갈색');
console.log(pug.name); // 퍼그
console.log(pug.age); // 10
console.log(pug.color); // 갈색
console.log(pug.play()); // 퍼그가 즐겁게 놉니다.
```

<br>


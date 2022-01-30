---
layout: single
title : JavaScript day3
categories : coding
tag : JavaScript
toc : false
---

배열 \| Array 객체 \| 배열 반복

<br>



### 배열

자료형은 변수와 값을 하나씩 저장할 수 있었지만, 배열은 하나의 변수에 값을 여러개 저장할 수 있다. 대괄호 안에 있는 배열의 위치를 가리키는 숫자는 인덱스라고 부르고 그 인덱스와 이름으로 참조되는 정렬된 값의 집합이다. 

```javascript
타입 배열명 = ["값1", "값2", "값3", ....];
//---------------------------------
var arr = [1, 1.5, true, '홍길동']; // 자바스크립트는 타입이 고정되어있지 않기 때문에 여러 타입이 들어가도 괜찮음
var arr1 = []; // 배열의 길이를 정하지 않아도됨
```

```javascript
let arr = [1, 'phone', '홍길동', 20, '공부', '햄버거'];
console.log(arr[0]); 	// 1
console.log(arr[1]); 	// phone
console.log(arr[2]); 	// 홍길동
console.log(arr[3]); 	// 20
console.log(arr[4]); 	// 공부
console.log(arr[5]); 	// 햄버거

arr[5] = '먹기'
console.log(arr[5]); 	// 먹기
console.log(arr.length);  // 6

arr[7] = 'A형'
console.log(arr.length);  // 8

console.log(arr[6]);  // undefined

console.log('---------------------');

for(let i = 0 ; i < arr.length ; i++){
	console.log(arr[i]); // 1 phone 홍길동 20 공부 햄버거 먹기 undefined A형
}
```

length 프로퍼티는 현재 배열의 요소의 갯수를 저장한다.



### Array 객체

자바스크립트의 여러가지 내장객체 중에 배열을 활용한 Array 객체가 있다. Array 객체에는 여러 메소드들이 있다.

| 종류      | 설명                                                         |
| --------- | ------------------------------------------------------------ |
| push()    | 배열의 요소를 추가                                           |
| pop()     | 배열의 마지막 주소에 있는 값을 제거                          |
| shift()   | 배열의 첫번쨰 주소에 있는 값을 제거                          |
| concat()  | 기존 배열에 요소를 추가해 새로운 배열을 생성                 |
| join()    | 배열 요소 사이에 원하는 문자를 삽입                          |
| reverse() | 배열을 역순으로 재배치, 역순으로 재배치일뿐 내림차순과는 다름. |
| sort()    | 배열을 오름 차순으로 정렬                                    |

```javascript
let arr1 = [1, 'phone', '홍길동', 20, '공부', '햄버거'];
console.log(arr1); 
// (6) [1, 'phone', '홍길동', 20, '공부', '햄버거']

arr1.push('여자'); // 맨뒤 배열 추가
console.log(arr1);  
// (7) [1, 'phone', '홍길동', 20, '공부', '햄버거', '여자']

arr1.shift();   // 첫번째 배열 삭제
console.log(arr1);  
// (6) ['phone', '홍길동', 20, '공부', '햄버거', '여자']

let arr2 = [2, 'samsung', '이순신', 27, '운동'];
let arr = arr1.concat(arr2);  // 두 배열 합치기
console.log(arr);  
// (11) ['phone', '홍길동', 20, '공부', '햄버거', '여자', 2, 'samsung', '이순신', 27, '운동']

let joinArr = arr1.join('🍎'); // 뒤에 문자 삽입
console.log(joinArr);  
// phone🍎홍길동🍎20🍎공부🍎햄버거🍎여자

let arr3 = ['a', 'z', 'c', 'f', 'r'];
arr3.sort();
console.log(arr3);
// (5) ['a', 'c', 'f', 'r', 'z']

arr3.reverse();
console.log(arr3);
// (5) ['z', 'r', 'f', 'c', 'a']
```



### 배열 반복

```javascript
let arr = [1, 'phone', '홍길동', 20, '공부', '햄버거'];

for(let i in arr){
console.log(`i의 값 : ${i}`); // i에 인덱스 대입
console.log(`arr[i]의 값 : ${arr[i]}`); // arr[i]은 인덱스에 맞는 값
}
/*
i의 값 : 0
arr[i]의 값 : 1
i의 값 : 1
arr[i]의 값 : phone
i의 값 : 2
arr[i]의 값 : 홍길동
i의 값 : 3
arr[i]의 값 : 20
i의 값 : 4
arr[i]의 값 : 공부
i의 값 : 5
arr[i]의 값 : 햄버거
*/
//--------------------------------------------

for(let i of arr){
console.log(`i의 값 : ${i}`); // i에 값이 대입
}
/*
i의 값 : 1
i의 값 : phone
i의 값 : 홍길동
i의 값 : 20
i의 값 : 공부
i의 값 : 햄버거
*/
//--------------------------------------------

arr.forEach(function e(item,idx,arr){
console.log(item);  // 값 출력
console.log(idx);   // 키(인덱스) 출력
});
/*
1
0
phone
1
홍길동
2
20
3
공부
4
햄버거
5
*/
```


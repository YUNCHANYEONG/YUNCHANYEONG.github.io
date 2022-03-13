---
layout: single
title : "LocalDateTime 타입 변환"
categories : coding_tip
tag : java
toc : false
---

LocalDateTime 타입 변환

<br>

### LocalDateTime 타입 변환

String의 형태를 갖고있는 문자열을 LocalDateTime타입의 DB 컬럼에서 활용하기 위해서 String 타입을 LocalDateTime 타입으로 변환 해줘야한다.

LocalDateTime.parse() 사용

```java
String now = "2022-03-13T11:17:21";
LocalDateTime.parse(now)
```

now의 값은 반드시 날짜 형태여야한다.

<br>

나는 자바에서 현재시간을 받아서 원하는 크기만큼 자르고 그 값에 대해서 DB에서 활용하고 싶었다.

```java
LocalDateTime now = LocalDateTime.now(); // 현재시간 구하는 객체, 2022-03-13T11:17:21.211432100
String strNow = String.valueOf(now).substring(0,19); // 2022-03-13T11:17:21
LocalDateTime local = LocalDateTime.parse(strNow); // 타입변환

// JPA를 활용하여 DB에 
List<Table> table = tableRepository.findFirstByDateGreaterThan(local);
```




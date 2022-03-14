---
layout: single
title : "JPA OrderBy 구문"
categories : coding_tip
tag : JPA
toc : false
---

JPA OrderBy 구문 

<br>

### JPA OrderBy 구문

JPA로 OrderBy 구문 만드는 방법을 알아보자. 

**\* desc : 내림차순, asc : 오름차순**

<br>

##### 1. select * from ? order by score desc | asc

```java
Optional<User> findAllOrderByScoreDesc();
```



##### 2. select * from where name = ? order by score desc | asc

```java
Optional<User> findByNameOrderByScoreDesc(String name);
```



##### 3. select * from where name = ? order by score desc | asc 		//  그 중 첫번째 데이터 가져오기

```java
User findFirstByNameOrderByScoreDesc(String name);
```


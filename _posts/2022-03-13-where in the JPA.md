---
layout: single
title : "JPA where 구문"
categories : coding_tip
tag : JPA
toc : false
---

JPA where 구문

<br>

### JPA where 구문

JPA로 where 구문 만드는 방법을 알아보자.



##### 1. where username = 

```java
Optional<User> findByUsername(String username);
```



##### 2. where username <>				 // not

```java
Optional<User> findByUsernameNot(String username);
```



##### 3. where username = ?  and othername = ?

```java
Optional<User> findByUsernameAndothername(String username, String othername);
```



##### 4. where username = ?  or othername = ?

```java
Optional<User> findByUsernameOrothername(String username, String othername);
```



##### 5. where score between ? and ?

```java
Optional<User> findByScoreBetween(int score1, int score2);
```



##### 6. where username < ?

```java
Optional<User> findByScoreLessThan(int Score);
```



##### 7. where username > ?

```java
Optional<User> findByScoreGreaterThan(int Score);
```



##### 8. where username <= ?

```java
Optional<User> findByScoreLessThanEqual(int Score);
```



##### 9. where username >= ?

```java
Optional<User> findByScoreGreaterThanEqual(int Score);
```



##### 10. where username is null

```java
Optional<User> findByUsernameisNull();
```



##### 11. where username is not null

```java
Optional<User> findByUsernameisNotNull();
```


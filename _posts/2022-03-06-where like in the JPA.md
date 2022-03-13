---
layout: single
title : "JPA로 where %like% 구문"
categories : coding_tip
tag : "Spring Boot", "JPA"
toc : false
---

JPA로 where %like% 구문

<br>

### JPA로 where %like% 구문

JPA로 where like 구문만드는 방법을 알아보자.



##### 1. select ... like : username

```java
Optional<User> findByUsernameLike(String username);
```



##### 2. select ... like : username%

```java
Optional<User> findByUsernameStartingWith(String username);
```



##### 3. select ... like : %username

```java
Optional<User> findByUsernameEndingWith(String username);
```



##### 4. select ... like : %username%

```java
Optional<User> findByUsernameContaining(String username);
```


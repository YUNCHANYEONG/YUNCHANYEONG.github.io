---
layout: single
title : "Failed to configure a DataSource"
categories : coding_tip
tag : Spring Boot
toc : false
---

Failed to configure a DataSource: 'url' attribute is not specified and no embedded datasource could be configured

<br>

### Failed to configure a DataSource

```
***************************
APPLICATION FAILED TO START
***************************

Description:

Failed to configure a DataSource: 'url' attribute is not specified and no embedded datasource could be configured.

Reason: Failed to determine a suitable driver class


Action:

Consider the following:
	If you want an embedded database (H2, HSQL or Derby), please put it on the classpath.
	If you have database settings to be loaded from a particular profile you may need to activate it (no profiles are currently active).
```

String Boot 처음 프로젝트를 만들어 실행하였을 때 빈번히 볼 수 있는 에러이다.

이 에러를 해결하기 위해서는 resource폴더에서 application.properties안에 환경 요소를 설정해줘야한다.

```
spring.datasource.url=jdbc:oracle:thin:@[DB이름]_high?TNS_ADMIN=전자지갑위치
```

추가로 application.yml 파일을 추가해 JDBC를 추가해 줘야한다.

```
spring: 
	datasource: 
		driver-class-name: [JDBC 드라이버]
		url: jdbc:oracle:thin:@[DB이름]_high?TNS_ADMIN=전자지갑위치
		username: [DB 아이디] 
		password: [DB 비밀번호]
```


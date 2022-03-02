---
layout: single
title : "Port 8080 was already in use"
categories : coding_tip
tag : Spring Boot
toc : false
---

Web server failed to start. Port 8080 was already in use.

<br>

### Web server failed to start. Port 8080 was already in use

```
***************************
APPLICATION FAILED TO START
***************************

Description:

Web server failed to start. Port 8080 was already in use.

Action:

Identify and stop the process that's listening on port 8080 or configure this application to listen on another port.


Process finished with exit code 0
```

위 에러는 이미 컴퓨터 내에서 8080포트를 사용하고 있다는것을 의미한다.

에러는 해결하기 위해서는 포트를 변경해줄 필요가 있는데

그러기 위해서 application.properties에 들어가

```
server.port=9090 // 예시
```

이런 식으로 포트번호를 재설정해주면된다.
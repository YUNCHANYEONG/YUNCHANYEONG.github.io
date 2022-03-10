---
layout: single
title : "Content type 'application/octet-stream' not supported"
categories : coding_tip
tag : Spring Boot
toc : false
---

Content type 'application/octet-stream' not supported

<br>

### Content type 'application/octet-stream' not supported

```
This application has no explicit mapping for /error, so you are seeing this as a fallback.

Thu Mar 10 12:45:05 KST 2022
There was an unexpected error (type=Unsupported Media Type, status=415).
Content type 'application/octet-stream' not supported
org.springframework.web.HttpMediaTypeNotSupportedException: Content type 'application/octet-stream' not supported
```



MultipartFile를 이용하여 파일 업로드 코드를 진행하는 동안 위와 같은 에러가 발생 하였다.

```java
 public String uploadFile(@RequestPart(value = "id") Long id,
                          @RequestPart(value = "imgs") MultipartFile imgs,
                          @RequestPart(value = "answers") MultipartFile answers,
                          @RequestPart(value = "pdfs") MultipartFile pdfs
    ) throws IOException {
     // ...
     // 생략
     // ...
}
```

원인을 분석해본 결과 @RequestPart의 사용 범위가 String, MultipartFile에 한해서 사용된다는 것을 알았다. 따라서 id의 타입을 Long에서 String으로 바꿔 실행했을 때 정상 실행됨을 확인 할 수 있다.
---
layout: single
title : "form안에서 put, delete 사용하는 방법"
categories : coding_tip
tag : Spring Boot
toc : false
---

form안에서 put, delete 사용하는 방법

<br>

### form안에서 put, delete 사용하는 방법

일반적으로 form 태그는 get, post방식을 지원해주기 때문에 put, delete 방식은 사용할 수 없다. 그러나 몇가지 설정과 코드 추가로 put, delete방식을 가능하게 할 수 있다.

먼저 application.properties에 아래 코드를 추가한다.

```
spring.mvc.hiddenmethod.filter.enabled=true
```

그리고 코드로 돌아와서

```
<form th:action="@{'/detail/' + ${boardDTO.id} + '/modify'}" method="post">
        <input type="hidden" name="_method" value="PUT">
</form>
```

form 안은 post로 해주되 input:hidden를 넣고 위와 같이 코드를 작성해 준다면 정상적으로 put를 사용할 수 있다.

<br>

저는 추가적인 문제가 발생하였고

**Content type 'application/x-www-form-urlencoded;charset=UTF-8' not supported**

위와 같은 에러는 

**pagecontroller**에서 **@RequestBody**를 사용하고 있기 때문이였다. 

**@RequestBody**는 body에 있는 json 데이터를 파싱해주는 역할로 **@RequestBody**를 지워주던가 아니면 **@RequestParam 혹은 @ModelAttribute**를 사용하면 해결되었다.

@RequestParam, @ModelAttribute 어노테이션도 제 역할이 있기 때문에 잘 알아보고 사용해야한다.


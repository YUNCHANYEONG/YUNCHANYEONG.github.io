---
layout: single
title : "SpringBoot에서 iframe 사용하기"
categories : coding_tip
tag : Spring Boot
toc : false
---

### SpringBoot에서 iframe 사용하기

SpringBoot 내에서 iframe를 사용하고자 할때 어떻게 할까? 분명 vs code로 html를 돌렸을 때는 문제가 발생하지 않고 iframe이 제대로 출력이 되었는데 SpringBoot로 환경을 바꾸면서 iframe를 기존 src를 유지한체 서버를 돌려 실행하면 에러와 마주하거나 원래 떠야하는 자리에 아무것도 뜨지 않는 것을 볼 수 있다.

iframe을 사용하기 위해서는 iframe를 위한 url이 필요하다. 

pagecontroller에서 iframe를 호출할 수 있는 url를 생성해준다.

```java
@Controller
@RequestMapping("/pages")
public class PageController {

    @RequestMapping("/index") // iframe를 담는 부모파일
    public ModelAndView index() {
        return new ModelAndView("/pages/admin_index")
                .addObject("code", "admin_index");
    }

    @RequestMapping("/index/cal") // iframe 파일, /pages/index/cal
    public ModelAndView Cal() {
        return new ModelAndView("/pages/cal/cal")
                .addObject("code", "cal");
    }

}
```

iframe를 출력하기 위해서 url (/pages/index/cal) 를 얻어와서 이 url를 iframe src에 넣어주면된다.

```java
<iframe src="/pages/index/cal" frameborder="0" id="ifm"></iframe>
```

그럼 정상으로 iframe를 확인할 수 있다.




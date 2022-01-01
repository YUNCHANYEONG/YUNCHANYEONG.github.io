---
layout: single
title : "Markdown - Liquid Exception : Liquid syntax error"
categories : coding_tip
tag : markdown
toc : false
---

상황. 

md 파일 내에

![이미지](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/Liquid%20Exception1.PNG?raw=true
)
<br>
와 같이 {{ 와 }} 를 사용하게되면 아래와 같은 에러메시지가 출력되며 업로드가 되지않는다.
<br>
![이미지](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/Liquid%20Exception2.PNG?raw=true
)
<br>
<br>
<br>

해결방안

![이미지](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/master/assets/images/coding_img/Liquid%20Exception3.PNG?raw=true
)
<br>
위와 같이 괄호 양 끝에 태그를 붙여주면 해결된다.

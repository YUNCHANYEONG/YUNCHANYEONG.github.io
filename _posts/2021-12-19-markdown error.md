---
layout: single
title : "Markdown - Liquid Exception : Liquid syntax error"
categories : coding_tip
tag : markdown
toc : true
---

상황. 

md 파일 내에

![이미지](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/d145a3289c3efed33e3a2211674ada5882d3e8cb/assets/images/coding_img/Liquid%20Exception1.PNG
)

와 같이 {{ 와 }} 를 사용하게되면 아래와 같은 에러메시지가 출력되며 업로드가 되지않는다.

![이미지](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/d145a3289c3efed33e3a2211674ada5882d3e8cb/assets/images/coding_img/Liquid%20Exception2.PNG
)




해결방안

![이미지](https://github.com/YUNCHANYEONG/YUNCHANYEONG.github.io/blob/d145a3289c3efed33e3a2211674ada5882d3e8cb/assets/images/coding_img/Liquid%20Exception3.PNG
)

위와 같이 괄호 양 끝에 태그를 붙여주면 해결된다.

---
layout: post
title:  "TemplateAPi 사용해보기"
summary: "TemplateApi"
author: sezero
date: '2021-09-06 10:30:23 +0530'
category: spring
thumbnail: /assets/img/posts/boot.png
---

TemplateApi 를 사용해보자. 그러기 위해서 서버가 두개 필요하기에 Intelij  를 사용해 서버 두개를 만들었다. (하나는 Client 하나는 Server)

<br><br>

<img src="/assets/img/posts/서버두개.PNG" width="100%" height="100%">

<br><br>

그다음 client 쪽에 참조할 RestTemplateApi 를 지정해준다.

<br>

<br>

<img src="/assets/img/posts/TemplateApiEx.PNG" width="100%" height="100%">

<br><br>

서버 쪽에 내가 만든 URI 와 같은 주소를 갖도록 만들어주자.

<br><br>

<img src="/assets/img/posts/ServerEx.PNG" width="100%" height="100%">

<br><br>

서버 쪽 컨트롤러는 간단하게 만들어준다 .

<br>

클라이언트 서버 쪽 설정을 해주자.

<img src="/assets/img/posts/TemplateApiClientController.PNG" width="100%" height="100%">

<br><br>
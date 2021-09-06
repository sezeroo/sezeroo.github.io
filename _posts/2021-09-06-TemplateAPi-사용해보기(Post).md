---
layout: post
title:  "TemplateAPi 사용해보기(Post)"
summary: "TemplateApi post"
author: sezero
date: '2021-09-06 16:00:23 +0530'
category: spring
thumbnail: /assets/img/posts/boot.png
---



<p>Get 방식의 방법을 보았다면 Post 방식도 살펴 보자.
    
</p>

<br><br>

<img src="/assets/img/posts/TemplateApiPost.PNG" width="100%" height="100%">

<br><br>

방식은 Get 과 비슷하지만 주소에 PathVariable 을 사용해서 값을 전송해 주려 한다.

<br>

.expand 는 순서대로 pathVariable 에 매칭이된다.

<br>

<img src="/assets/img/posts/ServerPostApi.PNG" width="100%" height="100%">

<br><br>

Get과는 반대로 보내주는 데이터를 받아서 활용해야 하는 Server 쪽의 컨트롤러는 위와

<br>

같은 방식으로 받아서 사용해주면 된다.

<br><br>

Post 방식에는 Header 값을 받아 사용 할 수 있다.

<br><br>

<img src="/assets/img/posts/UseExchange.PNG" width="100%" height="100%">

<br><br>

기본 Post 방식과는 다른게 거의 없다 RequestEntity 를 활용해 Header 값을 추가해 주고,

<br>

.postForObject 대신 .exchage 를 사용해주면 된다.

<br><br>



<img src="/assets/img/posts/HeaderController.PNG" width="100%" height="100%">

<br><br>

Server 컨트롤러는 위와같이 데이터를 받아 사용할 수 있다.
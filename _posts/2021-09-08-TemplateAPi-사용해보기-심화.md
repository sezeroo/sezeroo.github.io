---
layout: post
title:  "TemplateAPi 사용해보기 심화"
summary: "TemplateApi 심화학습"
author: sezero
date: '2021-09-08 17:30:23 +0530'
category: spring
thumbnail: /assets/img/posts/boot.png

---



<p>데이터를 주고 받을 때 타입을 지정해서 보낸다면 그만큼의 클래스가 만들어 져야한다.
    
</p>

<br>

그렇기에 제네릭 타입을 이용한 클래스를 만들면 데이터의 낭비를 줄일 수 있다.

<br>

<img src="/assets/img/posts/GenericClass.PNG" width="100%" height="100%">

<br><br>

위 사진 처럼 클래스 또는 인터페이스 이름 뒤에 <> 부호가 붙는다.

<br>

저 가로안에 내가 사용하고 싶은 타입을 지정해 주면 된다.

<br><br>

<img src="/assets/img/posts/GenericApi.PNG" width="100%" height="100%">

<br><br>

나는 Req 객체의 반환 타입을 UserResponse 로 지정해 주었다.

<br>

<img src="/assets/img/posts/GenericApi2.PNG" width="100%" height="100%">

<br><br>

이렇게 Service 를 지정해 주었다면 server 의 컨트롤러도 변경해 주어야 한다.

<br><br>

<img src="/assets/img/posts/ServerGeneric.PNG" width="100%" height="100%">


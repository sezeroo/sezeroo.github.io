---
layout: post
title:  "JPA Entity Listener"
summary: "Entity Listener"
author: sezero
date: '2021-11-17 15:25:23 +0530'
category: JPA
thumbnail: /assets/img/posts/entitylistener.PNG
---

JPA 뿐만 아니라 개발을 하다보면 같은 패턴의 코딩을 연속해서 해야할때가 있다. 이것을 편하게 하기위해 

<br>

JPA 는 Listener 를 지원해주고 있다.

<br>

우선 사용할 LIstener 클래스를 만들어준다. 나는 User 데이터를 저장할때 UserHistory 테이블에

<br>

함께 데이터를 저장하기위한 Listener 를 만들계획이다.

<br><br>

<img src="/assets/img/posts/entitylistener2.PNG" width="100%" height="100%">

<br><br>

이러한 형식으로  EntityListener 를 만들어준다. 

<br>

EntityListener 를 사용하려면  Entity 클래스에서 @Listener 를 사용해주어야한다.

<br><br>

<img src="/assets/img/posts/entitylistener3.PNG" width="100%" height="100%">

<br><br>

지정을 해주었다면 테스트를 해보자.

<br><br>

<img src="/assets/img/posts/entitylistener4.PNG" width="100%" height="100%">

<br><br>

<img src="/assets/img/posts/entitylistener6.PNG" width="100%" height="100%">

<br><br>

따로 userhitory 객체를 만들어 주거나 저장해주지 않아도 UserHistory 테이블에는 데이터가 저장되었다.
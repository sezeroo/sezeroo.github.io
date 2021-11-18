---
layout: post
title:  "JPA Converter 사용해보기"
summary: "JPA Converter"
author: sezero
date: '2021-11-18 16:25:23 +0530'
category: JPA
thumbnail: /assets/img/posts/entitylistener.PNG
---

JPA 에서는 객체를 다른객채로 변환해주는 Converter 라는 기능을 제공해준다.

<br>

예를들어 데이터베이스에서 Integer 값으로 저장하고싶은 엔티티  객체가 있다고 생각하면된다.

<br>

데이터베이스에는 Integer 값으로 저장되지만 DB가아닌 곳에서는 객체의 형태로 사용할수있다.

<br><br>

<img src="/assets/img/posts/jpaconverter.PNG" width="100%" height="100%">

<br><br>

책의 판매 상태를 가지고 컨버터를 사용하기위해 위사진처럼 BookStatus 클래스를 만들어주었다.

<br>

converter 사용을위해 converter 설정을해줄 BookStatusConveter 클래스를 만들어주었다.

<br><br>

<img src="/assets/img/posts/jpaconverter2.PNG" width="100%" height="100%">

<br><br>

그 후에 book 클래스(엔티티) 에 BookStatus 엔티티 값을 설정해준다.

<br>

다른 엔티티와는다르게 @Entitiy 어노테이션 설정을 해주지 않아도 된다.

<br><br>

<img src="/assets/img/posts/jpaconverter3.PNG" width="100%" height="100%">

<br><br>

이제 테스트를 해보러가자.

<br><br>

<img src="/assets/img/posts/jpaconverter4.PNG" width="100%" height="100%">

<br><br>

위와같이 테스트코드를작성하고 결과를 확인해보려한다.

<br><br>

<img src="/assets/img/posts/jpaconverter5.PNG" width="100%" height="100%">

<br><br>

DDL 문을 먼저 살펴보면 status integer 를 볼수 있을것이다. 

<br><br>

<img src="/assets/img/posts/jpaconverter6.PNG" width="100%" height="100%">

<br><br>

인서트 문을 보면 status 값을 집어넣게 되어있다. 셀렉트 문을 보면 네이티브 쿼리를 사용했기

<br>

때문에 내가지정한 쿼리그대로 사용하는데 status 값은 200 으로 나온다. 

<br><br>

<img src="/assets/img/posts/jpaconverter7.PNG" width="100%" height="100%">

<br><br>

로그에서 쿼리를 보면 status 갑에는 code값과 description 값이 출력된다.
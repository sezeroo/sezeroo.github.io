---
layout: post
title:  "JPA Embedded 사용해보기"
summary: "JPA Embedded"
author: sezero
date: '2021-11-19 10:25:23 +0530'
category: JPA
thumbnail: /assets/img/posts/entitylistener.PNG
---







JPA 사용중 예를들어 User 의 정보를 저장하는 엔티티를 사용하면서 주소정보를 등록할때가 있다.

<br>

그렇지만 주소정보 안에는 기본주소, 상세주소, 우편번호 등 다양한 정보가 존재해야한다.

<br>

<br>

<img src="/assets/img/posts/jpaembedded.PNG" width="100%" height="100%">

<br>

<br>

위사진을 보면 address, adeeressDetail, district, zipcode 등의 정보를 가져오도록 선언했다.

<br>

객체지향적인 관점에서 봤을때 저런방식으로 선언하는것은 낭비이다.

<br>

그렇다면 객체를 선언한후 사용해야하는데 JPA 에는 어떻게 적용해야될까.

<br>

이러한 상황을 위해 JPA 는 @Embedded 를 지원한다. Address 객체를 선언해보자.

<br>

<br>

<img src="/assets/img/posts/jpaembedded2.PNG" width="100%" height="100%">

<br>

<br>

객체를 선언해주었으면 User 엔티티에서 어떻게 사용해야 되는지 알아보자.

<br>

<br>

<img src="/assets/img/posts/jpaembedded3.PNG" width="100%" height="100%">

<br>

<br>

위 사진처럼 Address 객체를 불러오고 @Embedded 어노테이션을 붙여주면된다.

<br>

이제 테스트를 만들어 어떠한 결과가 나온는지 확인해보자.

<br><br>

<img src="/assets/img/posts/jpaembedded4.PNG" width="100%" height="100%">

<br><br>

<img src="/assets/img/posts/jpaembedded5.PNG" width="100%" height="100%">

<br><br>

결과 로그를 보면 Address 정보가 잘 나오는것을 알 수있다.

<br>

User 정보를 저장하다보면 User 의 주소가 여러개 일수도 있다. 회사주소, 집주소 등등

<br>

이러한 경우에는 어떻게 사용해야 할까. 일단 떠오르는게 User 엔티티에 Address 객체를

<br>

두가지 선언해주는것이다 homeAddress, companyAddress 라는이름으로 한번 해보자.

<br>

<br>

<img src="/assets/img/posts/jpaembedded6.PNG" width="100%" height="100%">

<br>

<br>

테스트도 진행해보자.

<br>

<br>

<img src="/assets/img/posts/jpaembedded7.PNG" width="100%" height="100%">

<br><br>

<img src="/assets/img/posts/jpaembedded8.PNG" width="100%" height="100%">

<br><br>

결과에 오류가 발생한다. 결과 내용을 보면 colum 을 업데이트나 인서트를 하지 못하도록 설정해 놓았다고한다.

<br>

같은 컬럼 이름을 가진 데이터가 하나이상 중복되어 인서트나 업데이트를 하지못하도록 하는것이다.

<br>

Address 객체의 이름만 바꾸어서 선언해주었기때문에 DB에서의 컬럼은 같은 이름을가진 컬럼을 사용하기때문에 오류가 발생하는것이다.

<br>

그렇다면 설정해준 Embedded 타입의 컬럼들을 @AttributeOverrides 를 사용하여 재선언해주어야한다.

<br><br>

<img src="/assets/img/posts/jpaembedded9.PNG" width="100%" height="100%">

<br><br>

복잡해보이지만 전혀그렇지않다. 위사진처럼 선언해준후 다시 테스트를 돌려보자.

<br><br>

<img src="/assets/img/posts/jpaembedded10.PNG" width="100%" height="100%">

<br><br>

정상적으로 데이터가 저장되었고 로그가 잘찍혓다. 이러한 상황이 놓였을때  Embedded 를 사용하면 될것같다.
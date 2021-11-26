---
layout: post
title:  "JPA 오류들 알아보기 (No session)"
summary: "JPA No Session"
author: sezero
date: '2021-11-25 17:25:23 +0530'
category: JPA
thumbnail: /assets/img/posts/jpafetch.PNG
---



JPA 는 영속성 컨텍스트 에서 Entity 들을 관리한다 그렇게하다보니 아무생각없이 데이터를 불러오면 오류들이 많이 발생한다.

<br>

이러한 오류를 자세히 알아보고 수정하는법을 공부하기위해 Review 엔티티와 Comment 엔티티를 사용해 알아보려한다. Review 엔티티를 만들어주자.

<br><br>

<img src="/assets/img/postsjpafetch2.PNG" width="100%" height="100%">

<br><br>

그후에 Comment 엔티티도 만들어준다.

<br><br>

<img src="/assets/img/postsjpafetch3.PNG" width="100%" height="100%">

<br><br>

사용할 엔티티들에 릴레이션을만들어 준후 테스트 코드를 작성해 테스트를 돌려보자.

<br><br>

<img src="/assets/img/postsjpafetch4.PNG" width="100%" height="100%">

<br><br>

<img src="/assets/img/postsjpafetch5.PNG" width="100%" height="100%">

<br><br>

테스트코드를 작성하고 돌리면 위사진과 같은 오류가 발생한다. 오류 메세지를 보면 세션이 없다는 오류가 보인다.

<br>

일단 오류를 알기위해서는  JPA 의 속성을 조금은 알필요가 있다 예를들어 설명해보자.

<br>

예를들어 Review 엔티티 를 불러오는 쿼리 에서 릴레이션된  Comment 엔티티는 항상 불러오지않아도된다.

<br>

Review 엔티티를 불러오면서 Comment 를 같이보고싶다면 그때 불러오면 된다. 그럴때 사용하라고 JPA 에서는 LazyPatch 방식을 사용하게 해주었다.

<br>

Review 엔티티에서 Review.getComment() 를 했을때 호출가능한것이 Lazy 방식이다.

<br>

이와는 다르게 Review 엔티티를 호출할때 릴레이션 되있는 객체를 불러오는것이 Eager 방식이다.

<br>

위에 나온 오류사진에서 보았듯 NoSession 오류는 Lazy패치 관련오류이다.

<br>

Lazy패치는 언제나 가능한것이아니라 세션이 열려있는 시점에만 가능하다. 세션은 영속성 컨텍스트가 엔티티를 관리하고 있는 라이프사이클의 주기이다.

<br>

@OneToMany 는 기본값이 Lazy 타입이고 @ManyToOne 은기본값이 Eager 타입이다.

<br>

영속성 컨텍스트가 해당 엔티티를 관리하고있는시점에 @Transactional을 붙여서 트랜잭션이 열려있을때 Lazy 패치가 동작한다.

<br>

Lazy패치와 Eager 패치를 비교해서 코드로 알아보자. 비교를 위해 user, book 엔티티는 LAZY 타입으로 선언하고 comment 엔티티는 EAGER 로 선언했다.

<br><br>

<img src="/assets/img/postsjpafetch6.PNG" width="100%" height="100%">

<br><br>

테스트를 돌려보자

<br><br>

<img src="/assets/img/postsjpafetch7.PNG" width="100%" height="100%">

<br><br>

결과를 보면 get()으로 호출 하는것에 상관없이 모든 쿼리가 동작 완료한 후에  로그가 찍혓다.

<br><br>

<img src="/assets/img/postsjpafetch8.PNG" width="100%" height="100%">

<br><br>

이번에는 comment 엔티티를 LAZY 타입으로 변경해준후 테스트를 실행해보자.

<br><br>

<img src="/assets/img/postsjpafetch9.PNG" width="100%" height="100%">

<br><br>

결과 를 보면 이번에는 get()으로 호출한 쿼리의 뒤에 로그가 찍혀서 나왔다.

<br>

차이를 보면 EAGER 패치는 쿼리를 모두 실행한후에 로그가 찍히는것을 볼수 있고 

<br>

LAZY 패치는 호출하는시점의 쿼리뒤에 로그가 찍히는것을 볼 수 있다.

<br>

LAZY 패치를 사용하면 JPA 에서 제공해주는 영속성 컨텍스트의 지연로딩을 활용하는것을 볼수있다.

<br>

NoSession 오류를 해결하는 방법을 위해 LAZY 패치 EAGER 패치의 차이점을 알아보았다.

<br>Lazy패치는 언제나 가능한것이아니라 세션이 열려있는 시점에만 가능하다. 세션은 영속성 컨텍스트가 엔티티를 관리하고 있는 라이프사이클의 주기이다. 기억하자.


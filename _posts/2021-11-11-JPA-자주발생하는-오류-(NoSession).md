---
layout: post
title:  "JPA 자주발생하는 오류 (NoSession)"
summary: "NoSession"
author: sezero
date: '2021-11-11 10:25:23 +0530'
category: JPA
thumbnail: /assets/img/posts/mysqlinserterror.PNG

---

JPA 테스트를 실행하다보면 아래와 같은 오류가 많이 발생한다.

<br><br>

<img src="/assets/img/posts/nosession.PNG" width="100%" height="100%">

<br><br>

처음에는 세션이 없다는게 무슨말일까 고민도해보고 내가 잘못 작성한 코드가 있나 <br>확인도 해보고 했었지만 간단하게 해결할수 있는 문제이다.

<br>
해결방법은 두가지이다. 테스트 하려는 Test 메서드를 @Transaction 으로 묶어주던지<br>

실행하려는 Entity 의 컬럼에가서 @Tostring.Exlude 선언해주면 해결된다.
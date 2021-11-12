---
layout: post
title:  "MYSQL Insert 오류"
summary: "Insert 오류"
author: sezero
date: '2021-11-10 10:25:23 +0530'
category: JPA
thumbnail: /assets/img/posts/mysqlinserterror.PNG

---

JPA 사용 test 를 만들기위해 mysql 인서트 문을 사용했는데 오류가 발생했다.

<br><br>

<img src="/assets/img/posts/mysqlinserterror.PNG" width="100%" height="100%">

<br><br>

진짜 아무리찾아봐도 잘못한게 없는거같은데 오류가나오니 머리가아팠다.

<br>
검색도 해보고 이리보고 저리봐도 잘못한게 없는데 머가문제일까 하고 이것저것 시도해보았다.

<br><br>

<img src="/assets/img/posts/mysqlinserterror2.PNG" width="100%" height="100%">

<br><br>

검색뿐 아니라 내가알기에도 컬럼 에는  '' , 작은따옴표가 들어가야한다 알고있는데 혹시나하고 컬럼에서 '' 을 빼보니

<br>
정상작동했다 또 다른방법은 컬럼에 백팁을 통해 입력해주는것이다. 예를들어
<br>
`id` 이렇게 작성해주면 정상작동 가능하다.

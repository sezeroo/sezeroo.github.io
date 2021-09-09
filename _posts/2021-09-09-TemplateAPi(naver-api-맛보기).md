---
layout: post
title:  "TemplateAPi(naver api 맛보기)"
summary: "TemplateApi 심화학습"
author: sezero
date: '2021-09-09 13:30:23 +0530'
category: spring
thumbnail: /assets/img/posts/boot.png
---

<br>

앞서 학습한 기본 Api 활용을 토대로 네이버 api 맛보기 를 해보려 한다.

<br>

내가 사용할 네이버 api 는 영화 검색 api 이다. 

<br>

<br>

<img src="/assets/img/posts/애플리케이션등록.PNG" width="100%" height="100%">

<br>

<br>

네이버 open api 를 검색후 naver Developers 에 들어가 위방식 처럼 클라이언트를 등록해주면

<br>

<br>

<img src="/assets/img/posts/ClientId.PNG" width="100%" height="100%">

<br>

<br>

클라이언트 ID, Secret 를 생성 할 수 있다. 

<br>

이 값은 후에 Api 를 호출할때 해더값에 들어갈 것이기 때문에 복사할 준비를 하면 좋다.

<br>

내가 사용할 Api 는 영화 검색이기 때문에  Document -> 서비스 API -> 검색 탭으로 이동한후

<br>

영화 탭으로 이동해준다. 

<br><br>

<img src="/assets/img/posts/영화Api1.PNG" width="100%" height="100%">

<br><br>

이동을 완료하면 위사진 과같은 페이지가 나오는데 준비사항은 방금 등록을 완료해 준비가 끝났다.

<br>

2.API기본정보에서 내가 사용할 것은 Json 타입의 Get 요청 URL 이기 때문에 복사할 준비를 하자.

<br><br>

<img src="/assets/img/posts/영화Api2.PNG" width="100%" height="100%">

<br><br>

요청변수를 보면 query, display 등등 많은 요청변수가 있지만 꼭 넣어줘야 하는것은 query 이다.

<br>

출력결과 등등 많은 정보들이 있는데 그거는 보면서 어떤 요청변수가 어떤값이 나오는지 보면 알수있다.

<br>

<img src="/assets/img/posts/영화api3.PNG" width="100%" height="100%">

<br><br>

예시를 보면 어떤식으로 요청해야하는지 나와있다.  예시를 참고해 Api 를 사용해보자.



<img src="/assets/img/posts/영화api4.PNG" width="100%" height="100%">

<br><br>


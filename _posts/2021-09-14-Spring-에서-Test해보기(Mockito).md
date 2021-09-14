---
layout: post
title:  "Spring 에서 Test해보기(Mockito)"
summary: "Spring test"
author: sezero
date: '2021-09-14 17:45:23 +0530'
category: spring
thumbnail: /assets/img/posts/boot.png


---



<br>

스프링에서 테스트 코드를 사용하면 수정할때마다 서버를 껏다 켰다 반복하지 않아도 <br>결과를 확인할 수 있다.

<br><br>

<img src="/assets/img/posts/Test1.PNG" width="100%" height="100%">

<br><br>

테스트 클래스에 필요한 어노테이션들은 다양하지만 위사진에 나온것을 주로 사용한다.

<br><br>

<img src="/assets/img/posts/Test2.PNG" width="100%" height="100%">

<br><br>

Get방식의 테스트 코드는 위사진처럼 사용하면 된다.(엄청 간단한코드만 작성했다ㅠ)

<br><br>

<img src="/assets/img/posts/Test3.PNG" width="100%" height="100%">

<br><br>

제대로 된 값을 넣어줬다면 위와 같은 결과가 나온다.

<br><br>

이번에는 Post 방식의 테스트를 확인해보자

<br><br>

<img src="/assets/img/posts/Test4.PNG" width="100%" height="100%">

<br><br>

이런식으로 Get방식과 Post 방식의 Test 코드도 사용할 수 있다.
<br>
테스트 용 코드템플릿을 작성해 놓으면 사용하기 편할 것 같다.

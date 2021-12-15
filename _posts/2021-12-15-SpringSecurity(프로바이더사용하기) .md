---
layout: post
title:  "SpringSecurity(프로바이더사용하기)"
summary: "SpringSecurity"
author: sezero
date: '2021-12-08 10:00:23 +0530'
category: spring
thumbnail: /assets/img/posts/게시판1.PNG
---



<br>
스프링 시큐리티를 사용하면서 스프링 프로바이더를 이용하여 로그인을 해보려고한다.

<br>
학생이라는 객체를 가지고 로그인을 시도해보려고한다.


<br><br>
<img src="/assets/img/posts/provider.PNG" width="100%" height="100%">
<br><br>
학생 객체를 만들어주고 StudentAuthenticationToken 을 작성해주자.
<br><br>
<img src="/assets/img/posts/provider2.PNG" width="100%" height="100%">
<br><br>
기본 템플릿은 이렇게 생겼지만 커스텀 해서 사용할거기 때문에 바꾸어주자
<br><br>
<img src="/assets/img/posts/provider3.PNG" width="100%" height="100%">
<br><br>
그 후에 StudentAuthenticationToken 을 관리해줄 매니져가 필요하다.
<br><br>
<img src="/assets/img/posts/provider4.PNG" width="100%" height="100%">
<img src="/assets/img/posts/provider5.PNG" width="100%" height="100%">
<br><br>
설명은 코드안에 주석으로 작성해놓았다.
<br>
Token 과 Manager 작성을 완료했으면 config 설정을 해주어야 한다.
<br><br>

<img src="/assets/img/posts/provider6.PNG" width="100%" height="100%">
<img src="/assets/img/posts/provider7.PNG" width="100%" height="100%">
<br><br>
이런식으로 기본템플릿을 잡고 사용할수 있다.


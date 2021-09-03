---

layout: post
title:  "Interceptor 알아보기."
summary: "Interceptor"
author: sezero
date: '2021-09-03 16:50:23 +0530'
category: spring
thumbnail: /assets/img/posts/InterceptorClass.PNG
---

SpringBoot 를 활용해 InterCeptor 의 사용방법을 알아보자.

<img src="/assets/img/posts/AuthAnnotation.PNG" width="100%" height="100%">

(내가 직접 만든 Auth 어노테이션 클래스.)

<br>

인증관련하여 어떤 것을 사용해 인증할것인지 많은 종류가 있겠지만 나는 Auth 라는 어노테이션이 사용하는 것으로 인증 을 해보려고한다.

<br>

(@Auth 가 있으면 인증O, 없으면 인증 X )

<br>

인증에 사용할 컨트롤러를 두개 만들어주자.

<br><br>

<img src="/assets/img/posts/PrivateController.PNG" width="100%" height="100%">



<br><br>

<img src="/assets/img/posts/PublicController.PNG" width="100%" height="100%">

<br><br>

PrivateController 은 내가만든 Auth 어노테이션을 사용하고 PublicController 은 사용하지 않는다.

<br> 그렇다면 PrivateController 의 값은 리턴 될것이고, PublicController 은 리턴되지 않을것이다.

<br>

이러한 과정을 실행하기 위해서는 Interceptor 를 지정해주어야한다. 



<img src="/assets/img/posts/InterceptorClass.PNG" width="100%" height="100%">

<br><br><img src="/assets/img/posts/CheckAnnotation.PNG" width="100%" height="100%">

<br><br>

Interceptor 클래스를 생성해준다. HandlerInterCeptor 를 상속받아준다 (그냥외우자.)

<br>

preHandle 메소드를 오버라이드해서 사용해주면된다. 기본적으로 HttpServletRequest,HttpServletResponse,handler 를 사용해주면 다 구현할 수 있다.

<br><br>

@Auth 가 있다면 Interceptor 로그가 찍힐것이고 아니면 찍히지 않을것이다.

<br><br>
<img src="/assets/img/posts/InterceptorLog.PNG" width="100%" height="100%">

<br><br>
<img src="/assets/img/posts/MvcConfig.PNG" width="100%" height="100%">

<br><br>

Interceptor 클래스를 만든후 등록해 주지 않으면 사용할 수 없으니 등록해주는 클래스도 만들어야한다.


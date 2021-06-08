---

layout: post
title:  "WebFluxTest 오류 알아보기(1)"
summary: "내가 겪은 오류들 알아보기"
author: sezero
date: '2021-06-08 16:00:23 +0530'
category: SpringBoot
thumbnail: /assets/img/posts/boot.PNG
---

<p>스프링 부트를 사용하면서 Reactive 한 코드를 사용하다보면  test  를할때 WebMvcTest가 아닌 <br>WebFluxTest 를 사용하게 된다. </p>

<br>

<p> 그중에서 책을  따라 api 만들기 테스트중 겪었던 오류들을 정리해보고자 한다.</p>

<br><br>

<img src="/assets/img/posts/403error.PNG" width="100%" height="100%">

<br><br>

<p>처음 보는 에러이다. 스프링부트를 사용하다 보니 콘솔창에 오류가 좀 직관적(?)으로 알아보기 쉽게 나오는것같은 기분이다</p>

<br><br>

<p>내용을 보면 201CREATED 가 출력되기를 기대했지만 403FORBIDDEN 오류가 나왔다는 말인것같다. 

<p>처음 보는 에러이다. 스프링부트를 사용하다 보니 콘솔창에 오류가 좀 직관적(?)으로 알아보기 쉽게 나오는것같은 기분이다</p>

<br><br>

<p>왜 이런오류가 발생하는지 알아보기 위해 콘솔창을 뒤져보았다.<br>
    
</p>

(주관적인 오류 찾는 방법입니당.)<br><br>

<img src="/assets/img/posts/CsrfNotFound.PNG" width="100%" height="100%">

<br><br>

<p>사진을 보면 눈이가는 곳이 두곳이 있었다. 한곳은 < X-XSS-Protection: [1 ; mode=block]
    <br>
    다른 한 곳은 An expected CSRF token cannot be found 였다.
</p>

<br><br>

<p>두곳을 보자 바로 머리에 떠오르는 것은 Spring Security 관련 오류구나 라고 생각했다.<br><br>
    
</p>

<p>Security 설정을 해놓았기 때문에 데이터를 주고받는 테스트에서 인증오류가 나는 것 이었다.
    <br><br>



<hr>



<p>@WebMvcTest 테스트를 실행하면 Security 설정 컨텍스트가 반영이 된 상태의 테스트 서버 인스턴스가 기동된다<br><br>
하지만 @WebFluxTest 테스트를 실행하면 Security 설정 컨텍스트가 반영이 안된 상태의 테스트 서버 인스턴스가 기동된다.  <br><br>

   <hr> 

이 사실을 모르고 테스트 하면 Spring Security 설정에서 분명히 `csrf().disable()`을 해줬는데도 불구하고 아래와 같이 CSRF 토큰 관련 403 에러가 계속된다.

<br><br>

<p>원인을 알았으니 해결방법은 간단하다. 내가 설정해놓은 scurity 설정을 테스트 클래스에 알려주면 된다.</p>

<br><br>



<img src="/assets/img/posts/TestclassImport.PNG" width="100%" height="100%">

<br><br>

<p>
    WebFluxTest()에 내가설정한 시큐리티 config 클래스 SecurityConfig 클래스를 알려주었다.
</p>

<br><br>

<img src="/assets/img/posts/CreatingBeanerror.PNG" width="100%" height="100%">

<br><br>

<p>기존에 발생했던 오류는 사라졌지만 다른 오류가 생겼다. 항상 오류는 이런식이다. ㅠㅡㅠ <br><br>그렇게 어려운 오류는 아니니 다음포스팅에서 오류를 알아보자.

<br><br>

<hr>

<p>책을 보며 공부를 하는데 책에 나오는 대로 따라해도 생각하지 못한 오류가 나오면 너무 당황스럽다 <br><br> 개발의 길은 정말 너무 끝이없다 .
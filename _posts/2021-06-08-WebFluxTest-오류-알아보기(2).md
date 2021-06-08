---

layout: post
title:  "WebFluxTest 오류 알아보기(2)"
summary: "내가 겪은 오류들 알아보기(2)"
author: sezero
date: '2021-06-08 16:20:23 +0530'
category: SpringBoot
thumbnail: /assets/img/posts/boot.png
---

<p>전편에 이어 2편 오류 찾기이다. 어떤 오류인지 알아보자.

 <br><br>

<img src="/assets/img/posts/CreatingBeanerror.PNG" width="100%" height="100%">



<br><br>

<p>오류 메시지를 찾아보니 java.lang.IllegalStateException: Failed to load ApplicationContext오류이다.<br><br>

<p>진짜 많이 마주치지만 볼떄마다 새롭다. 일단 이오류 메시지는 넘아가고 밑에더 상세한 오류 메시지를 찾아보자
    <br><br>
</p>

<img src="/assets/img/posts/userDetailService.PNG" width="100%" height="100%">

<br><br>

<p>오류메시지를 보니 이것 또한 많이 마주친 오류이다. 이런 오류는 대부분 내가 설정한 클래스에 가면 이유를 찾을 수 있다.</p>

<br><br>

<p>그런데 이 오류는 무작정 설정 클래스에 찾아가면 답을 찾기 어렵다. 앞서 내가 시큐리티를 설정해 놓았기 때문에 시큐리티 에 관한 사전지식이 조금 필요하다.</p>

<br><br><p>나도 시큐리티 코드를 볼때마다 새롭지만 그래도 어떻게 돌아가는지는 머리속에 넣어놓으면 좋을것 같다.</p>

<br><br>

<hr>

<p>SpringSecurity 를 통해 접속하면 AuthenticationFilter 가 UserDB에 들려 User 데이터가 있다면<br>
UserDetails 로 꺼내서 세션을 생성한다. 하지만 나는 이것을 커스텀 해놓았기 때문에 테스트 클래스 쪽에서 찾지 못할 수 도 있다.   
</p>

<hr>

<br><br>

<p>그럼 어떻게해야되느냐, 지금은 그냥 테스트 만 하면되기 때문에 가서 주석 처리해주자.
    
</p>

<br><br>

<img src="/assets/img/posts/SecurityConfig주석.PNG" width="100%" height="100%">

<br><br>

<p>이렇게하니 테스트가 정상적으로 돌아갔다.
    
</p>

<br><br>

<hr>

<p>테스트 하나도 이렇게 오류가 많이 난다. 슬프다ㅠㅠ
---

layout: post
title:  "springboot view 진행 과정 알아보기"
summary: "view"
author: sezero
date: '2021-06-11 17:30:23 +0530'
category: SpringBoot
thumbnail: /assets/img/posts/boot.png
---

<p> 스프링부트 는 스프링 프로젝트와는 다르게 많은 설정이 필요가 없다. 그래서 그런지 <br>
    멀 어디서 어떻게 해야 스프링의 컨트롤러와 뷰를 활용 할 수 있는건지 감도 안잡혀서 <br>
    이리저리 검색을 해보았다.
</p>

<br><br>

<img src="/assets/img/posts/viewlist.PNG" width="100%" height="100%">

<br><br>

<p>스프링부트 프로젝트를 지작하면 기본 구조가 이런식으로 되어있을 것이다. <br>
   스프링프로젝트를 사용할때는 WEB-INF, prefix, surfix 이런 것들을 하나하나 설정 해주어야 했지만 <br>
    스프링부트는 그런걸 할필요가 없다. 그래서 그런지 처음엔 더어렵게만 느껴졋다.
    <br>
</p>

<br><br>

<p>스프링프로젝트에서는 src/main/web-inf/view/... 이런식으로 view 의 경로를 설정했다면 <br>
   부트에서는 templates 안에 view 를 설정해준다 생각하면 편하다. 물론 설정을 통해 <br>
   mvc 패턴과 같은 디렉토리를 만들 수 있지만 나는 이게더 편한것같다.<br>
</p>

<img src="/assets/img/posts/Dierctorylist.PNG" width="100%" height="100%">



<br><br>

<p>이전에는 views 같은 폴더안에 jsp,html 등을 넣어주었지만 부트에서는 templates 안에 만들어주면된다.<br>
 나는 index.html 을 templates 안에 만들어주었다.   
</p>

<br>

<br>

<p>그 후는 컨트롤러 를 만들어 주면된다.  

<img src="/assets/img/posts/indexcontroller.PNG" width="100%" height="100%">

<br><br>

<p>이런 식으로 만들어 주면 우리가 기존에 사용하던 mvc 패턴과 같은 기능을 사용할 수 있다.<br><br> 어플리케이션을 실행해주고 http://localhost8080/ 을 입력후 확인해보자.

   </p>

<br><br>

<p>여기서 주의할점은 한가지다. 내가 사용할 컨트롤러가 application 의 위치보다 상위디렉토리에 <br>있거나 다른곳에 있으면 안된다. 무조건 하위 디렉토리에 만들어주어야한다.!!</p>

<p>


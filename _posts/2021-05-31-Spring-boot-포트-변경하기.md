---
layout: post
title:  "Spring boot 포트 변경하기"
summary: "포트변경"
author: sezero
date: '2021-05-31 17:45:23 +0530'
category: SpringBoot
thumbnail: /assets/img/posts/boot.png
---

<p>스프링 부트를 처음 사용하다보니 스프링 레거시 프로젝트와 다른게 너무 많았다. <br>
 그중에서 가장 기초라고 할 수 있는 포트 변경하는 방법도 몰라 이리저리 검색해 보았지만 원하는 방법을 찾지는 못했다. 
 <br>
알고보니 어렵지 않게 포트를 변경 할 수 있었다.    
</p>

<br><br><br>

<p>Run -> Edit configuration 을 가면 아래그림처럼 창이 하나 열릴것이다.<br>

<img src="/assets/img/posts/editconfiguration.png" width="80%" height="80%">



<br><br>

<p>창이 열리면 <h4>Enviroment variables</h4>  칸 안에 <h4>server.port='변경하고싶은 포트번호'</h4> 를 입력한후 넣어주면 된다.
    
</p>


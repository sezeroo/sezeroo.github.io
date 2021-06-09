---

layout: post
title:  "Intellij 에서 curl 사용해보자"
summary: "curl 사용하기"
author: sezero
date: '2021-06-09 17:20:23 +0530'
category: etc
thumbnail: /assets/img/posts/gitbash.PNG
---

<p>

<p>지금까지 어플리케이션을 시작하거나 서버를 시작할때 버튼을 클릭해서 동작을 수행했다.<br><br>
    하지만 터미널을 사용해서 동작을 수행하는 방법을 책을 통해 알게되었다.

<br><br>

<p>터미널에서 동작을 수행하기 위해서는 cURL 을 사용하는데 cURL 이란 무엇일까?<br><br><h5>cURL(/kɝl/ 또는 /kə:l/[3])은 다양한 통신 프로토콜을 이용하여 데이터를 전송하기 위한 <br><br>라이브러리와 명령 줄 도구를 제공하는 컴퓨터 소프트웨어 프로젝트이다 - 나무위키 펌 -</h5> 

<br><br>

<p>책에서 cURL 을 사용해서 서버를 시작하는등에 행동을 하는데 어떻게 하는지 몰라서 당황했다.
    <br><br>

​    

<p>intellij 에서 cURL 을 사용하려면 터미널 을 사용하면 되는데 gitbash 를 이용해서 사용하면 된다.
    
</p>

<br><br>

<p>그러기 위해서는 intellij 내부 터미널 과 gitbash 를 연결 해줘야한다. </p>

<br><br>

<img src="/assets/img/posts/terminal.PNG" width="100%" height="100%">

<br><br>

<p>File -> Settings->Tools->Terminal <br>로 들어가면 <h5>Shell path</h5> 를 보면 기본값으로 cmd 가 되어있을것이다. <br>

그 부분을 자신의  gitbash 주소로 입력해주자. </p>



<img src="/assets/img/posts/upterminal.PNG" width="100%" height="100%">

<br><br>

<p>이렇게 변경해주고 intellij 를 껏다 가 다시 켜야된다. 꼭 껏다가 재시작 해줘야한다. 
    <br><br>
    그럼 내부 터미널이 gitbash 인터페이스처럼 변경 되어 있을것이다.
</p>


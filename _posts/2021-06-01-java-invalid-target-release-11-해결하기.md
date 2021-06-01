---
layout: post
title:  "java: invalid target release: 11 해결하기"
summary: "오류 해결하기"
author: sezero
date: '2021-06-01 17:45:23 +0530'
category: SpringBoot
thumbnail: /assets/img/posts/release11error.PNG
---

<p>인텔리제이도 처음이고 스프링 부트사용도 처음이다 보니 처음보는 오류들을 마주치는 경우가 많아졌다. 그렇다고 
   이전에는 오류를 마주치지 않앗냐고 물어보면 코린이 임을 내새우며 도망가야겠다.
</p>

<br>

<p>코드를 작성하고 코드에 오류가 없나 확인해보기 위해 어플리케이션을 실행해보니 
   <h4>java: warning: source release 11 requires target release 11</h4>
	이런 오류가 발생했다.
</p>

<br>

<p>일단 내가 해결한 방법은 아래와 같다. (intellij 기준입니당.) <br><br>
    처음으로 확인할곳은 <br> <br>
    File ->Setting -> Bulild,Execution, Deployment -> Compiler -> java Compiler 이다.<br><br>
</p>

<img src="/assets/img/posts/javaCompiler.PNG" width="100%" height="100%">



<br><br>

<p>위에 알려준 경로로 들어가면 위 사진처럼 창이하나 나오는데 확인해줘야 할곳은 
    <h4>Project bytecode version   
 이다.</h4><br>
나는 현재 8로 되어있지만 오류가 난다면 본인에게 맞는 버전을 선택해주면 된다.
</p>

<br><br>

<p>이것만 확인해주고 끝이나면 좋겠지만 확인해줘야할 곳이 남아있다. <br>
<br>    File -> Project Structure -> Project Settings -> Modules 로 들어가준다.

<br><br>

<img src="/assets/img/posts/Modules.PNG" width="100%" height="100%">

<br><br>

<p>경로대로 들어가면 이미지와 같은 창이 뜨는데 이곳에서 변경해줘야 할곳은 <br><br>
    <h4>
        Language level 이다.
</h4>
<br><br>
	내가사용하는 jdk 버전이 1.8 이기때문에 8 로 되어있어야 하지만 이미지 처럼 11 로 되어있어 <br> <br>
오류가 나는 것이었다. 8로 변경해주자.
</p>

<br><br>

<img src="/assets/img/posts/BootConsole.PNG" width="100%" height="100%">

<br><br>

<p>깔끔하게 오류가 해결되고 정상적으로 실행됬다.


---
layout: post
title:  "Uncaught TypeError ~ is not a function 해결하기."
summary: "not a function 해결하기"
author: sezero
date: '2021-05-21 14:30:23 +0530'
category: spring
thumbnail: /assets/img/posts/notfunction.PNG

---

<p>제이쿼리의 가독성을 높이기 위해 모듈화 를 통해 function 을 나누어 사용하다 보니 오류가 발생했다.     
</p>

<img src="/assets/img/posts/notfunction.PNG" width="75%" height="75%">



<br><br>

<p> 코드의 오타, 기호오류 등의 다양한 이유가 있겠지만 나같은 경우에는 모듈화 해놓은 곳에서 function 을 return 해주지 않아 나오는 오류였다.

</p>



<br><br>

<img src="/assets/img/posts/beforefreturn.PNG" width="75%" height="75%">



<br><br>

<p>이런식으로 return 값에 넣어주니 문제가 해결되었다.

<br><br>



<img src="/assets/img/posts/afterReturn.PNG" width="75%" height="50%">



<h3>다시한번 느끼지만 모든 오류는 내 잘못이다. ㅠㅠ
    
</h3>




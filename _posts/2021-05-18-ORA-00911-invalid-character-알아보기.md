---
layout: post
title:  "ORA-00911: invalid character 알아보기"
summary: "ORA-00911: invalid character"
author: sezero
date: '2021-05-18 14:45:23 +0530'
category: spring
thumbnail: /assets/img/sql에러.png

---



<p>페이징 처리를 위해 열심히 sql 을 작성하고 실행해보니 오류가 발생햇다. </P>

<img src="/assets/img/posts/sql에러.PNG" width="75%" height=auto>
<p>
'ORA-00911: invalid characte'

누구인지 알아보니 문자가 부적합 하다는 오류였다.
</P>

<p>'그럴리가 없는데...' 라는 마음으로  xml 파일에 찾아가보니  아니나다를까 </p>

![sql;](https://user-images.githubusercontent.com/76033275/118597699-ffb03b00-b7e7-11eb-86a4-2fafc39ed5fd.PNG)

<br>

<p>마지막에 찍혀있는 ; 나도 모르는 사이 세미콜론을 찍어버렷다. 
    sql 문을 작성할때는 항상 유의하자..

</p>  

<h2>코드는 거짓말 하지 않는다. ㅜㅜ</h2>


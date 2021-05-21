---
layout: post
title:  "Spring JDBC log 제어하기"
summary: "Spring JDBC log 제어하기"
author: sezero
date: '2021-05-12 08:45:23 +0530'
category: spring
thumbnail: /assets/img/log.jpg

---

<p> 예제 프로젝트를 수행하면서 log4jdbc-log4j2 라이브러리 를 이용하여 콘솔 창에 데이터베이스 관련 정보를 볼 수 있도록 하였다. 문제는 너무 많은 로그가 찍혀서 많은 양의 데이터가 들어가면 너무 정신이 없을 것 같아 log4jdbc-log4j2 를 제어하는 법을 알아보았다. 
</P>	

 <br>



​	

![log](https://user-images.githubusercontent.com/76033275/118463599-e8ffda80-b73a-11eb-9811-480cc42e2897.PNG)




<p> 정리를 하기전에는 이런식으로 너무많은 양의 코드가 로그에 찍혀 나와 정신이 없었다. 
    로그에 찍힌 jdbc 관련 정보를 제어 하기 위해서는 src/main/resources 에 있는 log4j.xml을 수정, 추가 해줘야한다.
</p>

<br>



![jdbclog](https://user-images.githubusercontent.com/76033275/118462022-34b18480-b739-11eb-9ec2-6b8444340cf7.PNG)



<p> 나는 이런식으로 정리했다. 
    
</p>

<br> 

<img src="/assets/img/posts/updatejdbclog.PNG" width="50%" height="50%">



<p>정리하고 나니 콘솔창이 깔끔해졋다 ㅎㅎ


---
layout: post
title:  "mybatis sql 조회 결과가 다른경우.."
summary: "조회결과가 다른경우"
author: sezero
date: '2021-05-18 17:10:23 +0530'
category: etc
thumbnail: /assets/img/log.png
---

<p>프로젝트를 하면서 게시글을 조회하는데  console 창에 나오는 sql 구문의 결과 값이 다르게 나와서 
    
</p>

왜 다르게 나오는지 한참 고민했다...

![sql조회](/assets/img/sql조회.png){: width="50%" height="50%"}


<br><br>



<p> 분명히 위에있는 sql 구문을 복사해서 똑같이 확인해봐도 mybatis 결과값이 다르게 나오는것이었다. <br>
저런 오류가 나오니 어떻게 검색을 해야될지도 모르겠고 한시간 가량 소강상태에 빠져 머리만 쥐어 뜯었다. <br>

<p>나같은 경우에는 진짜 어이없는 이유에서 결과 값이 계속 다르게 나왔던 것이엇다.</p>



<br><br>



<h2>데이터베이스 커밋을 항상 습관화 해야겠다..<h2>

<p>




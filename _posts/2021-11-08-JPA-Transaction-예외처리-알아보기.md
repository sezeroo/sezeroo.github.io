---
layout: post
title:  "JPA Transaction 예외처리 알아보기."
summary: "JPA Transaction"
author: sezero
date: '2021-11-08 17:15:23 +0530'
category: JPA
thumbnail: /assets/img/posts/searchservice.PNG

---

JPA Transaction 은 간단하게 말하면 같이 동작해야한다는것이다.

<br>

하나의 메소드 안에 두개의 트랜잭션이 있다면 두개의 트랜잭션 이 모두동작한 후에 

<br>

DB에 커밋이되고 동작을 한다고생각하면된다.

<br>

은행에서 돈을 송금할때 내통장에서 돈이 송금되었지만 받는사람에게 송금되어지지않고

<br>

거래가 끝나버리면 문제가 생기게 되니 그것을 방지하기 위함이라고 생각해도 좋을것 같다.

<br>

트랜잭션 테스트를 위해 기본구성으로 서비스하나, 테스트클래스하나를 만들었다.



<br><br>

<img src="/assets/img/posts/jpatransaction.PNG" width="100%" height="100%">

<br><br>

서비스안에 메소드를 만들어 주고 두개의 트랜잭션또한 만들어준후 @Transactional 어노테이션을 부쳐주었다.

<br>

일반적인 경우라면 두개의 트랜잭션이 완료된후 DB 에 커밋되어 지지만 runtimeException 을 던져주자.

<br>





그후 서비스로 이동해보자.

<br><br>

<img src="/assets/img/posts/jpatransaction2.PNG" width="100%" height="100%">

<br><br>

runtimeException 을 던져주었기때문에 서비스 클래스에서는 try catch 문을 써서 서비스의 메소드를 받아사용하자.

<br>

그후 repository 에 있는 서비스를 로그에 보이게 만들어준다.

<br><br>

<img src="/assets/img/posts/jpatransaction3.PNG" width="100%" height="100%">

<br><br>

처음 디버그 포인트인 book 객체의 생성에서는 book 테이블이 비어있다. 

<br><br>

<img src="/assets/img/posts/jpatransaction4.PNG" width="100%" height="100%">

<br><br>

두번째 체크포인트는 book 테이블에 save() 메소드까지사용했지만 데이터가 커밋되지않았다.

<br>

<br>

<img src="/assets/img/posts/jpatransaction5.PNG" width="100%" height="100%">

<br><br>

두번째 트랜잭션인 author 까지 완료한후에는 DB 에 커밋이 되는거라 생각했지만 커밋이 되지않았다.<br>

그이유가 무엇일까?

<br>

세번째 디버깅 포인트인 RuntimeException 때문이다.

<br><br>

RuntimeException을 받지않으면 transaction 이 완료된 후에 데이터는 DB에 커밋된다.
<br>
결과적으로 RuntimeException 이 발생하면 그 테이블은 드랍되어버린다.

<br><br>

<img src="/assets/img/posts/jpatransaction6.PNG" width="100%" height="100%">

<br><br>

Service 클래스에서 Exception 던져주던것을 주석처리한후 디버깅 포인트를 지나면 사진과 같이 데이터들이 DB 에커밋되어진다.

<br>

그렇다면 Exception 을 던져주면 무조건 transacion 이안되는것일까?? 그것은 아니다.

<br>

CheckException 즉 기본 Exception 을 던져주면 오류가 나더라도  DB 에 데이터들은

<br> 저장이된다.오류가 발생했을떄 로그만 찍을것인지, 로그를 찍고 데이터를 저장시키지 않을것인지

<br>

 이것은 개발자가 잘 선택해서 사용해야할 역량인것같다.

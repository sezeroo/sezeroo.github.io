---
layout: post
title:  "JPA BaseEntity (Listner) 알아보기"
summary: "JPAListner"
author: sezero
date: '2021-11-23 09:25:23 +0530'
category: JPA
thumbnail: /assets/img/posts/baseentity.PNG
---









<br>

CRUD 작업을 하다보면 대부분 공통으로 들어가는 컬럼은 생성일, 업데이트일 이 들어간다.

<br>

거의 모든 테이블에 같은 컬럼이 들어간다면 하나하나 테이블에 선언해주는거는 비효율적이다.

<br>

그랬을때 사용할수 있는게 JPA에서 제공해주는 Listner 이다.

<br>

생성일, 수정일 을 하나의 클래스로만들어서 사용할텐데 그이름을 BaseEntity 로 만들어준다.

<br>

<br>

<img src="/assets/img/posts/baseentity.PNG" width="100%" height="100%">

<br>

<br>

@EntityLister 어노테이션에서는 AuditingEntityListener 클래스를 값으로  지정해준후에(중요하다.)

<br>

대부분의 클래스가 BaseEntity 클래스를 상속받아 사용할것이기때문에 @MappedSuperClass 를지정해준다.

<br>

 생성일에서는 @createDate 를 붙여주면 Jpa에서 자동으로 쿼리를 작성해준다.

<br>

수정일도 마찬가디로 @LastModifiedDate 를 붙여준다. 두가지의 컬럼모두 null 값이들어가면 안되고 수정이 가능하면 안되기에 두가지의 기능모두 설정해준다.

<br>

사용법은 간단하다 생성일 수정일을 사용할 테이블 Entity클래스에서 상속받아 사용하면된다.

<br>

<br>

<img src="/assets/img/posts/baseentity2.PNG" width="100%" height="100%">

<br>

<br>

Entity 클래스를 보면 BaseEntity 를 상속받았다. 클래스내부에는 생성일, 수정일 관련 선언한 값이 없지만 테스트를 통해 테이블이 어떻게 생성되는지 확인해보자.

<br>

<br>

<img src="/assets/img/posts/baseentity3.PNG" width="100%" height="100%">

<br>

<br>

테스트 코드를작성했다. 생성일 수정일 작성을 해주지 않았다. 테스트를 돌려본후 로그를 확인해보자.

<br>

<br>

<img src="/assets/img/posts/baseentity5.PNG" width="100%" height="100%">

<br>

<br>

생성된 테이블을 보면 Phone 이라는 Entity 클래스에  createAt,updateAt  을 설정해주지않았지만 컬럼이 생성되었다. 

<br>

<br>

<img src="/assets/img/posts/baseentity6.PNG" width="100%" height="100%">

<br>

<br>

결과 로그에도 생성일과 수정일이 함께 찍혀나오는것을 볼수 있다.


# spring_practice


#프레임워크
	뼈대나 근간을 이루는 코드들의 묶음
	라이브러리란, 개발자가 작성해놓은 코드파일을 의미하며,
	API란, 여러 라이브러리가 모여있는 패키지(JAR)를 의미한다.
	프레임워크란 API가 굉장히 많이 모여져서 덩치가 커져있는 것을 의미한다.
	프레임워크는 API에 둘러싸여서 작업을 하고있다고 생각하면된다.
	개발자는 각 개개인의 능력차이가 큰 직종이고, 개발자 구성에 따라 프로젝트 결과 역시
	큰 차이를 낳는다. 이런상황을 극복하기 위한 코드이 결가물이 바로 프레임워크이다.
	프로그램의 기본 흐름이나 구조를 정하고 모든 팀원이 이구조에 자신의 코드를 추가하는
	방식으로 개발하게 된다.

#프레임워크의 장점
	개발에 필요한 구저를 이미 코드로 만들어 놓았기 때문에, 실력이 부족한 개발자라 하더라도
	반쯤 완성한 상태에서 필요한 부분을 조립하는 형태의 개발이 가능하다.
	회사 입장에서는 프레임워크를 사용하면 일정한 품질이 보장되는 결과물을 얻을수 있고,
	개발자 입장에서는 완성된 구조에 자신이 맡은 서비스에 대한 코드를 개발해서 넣기
	때문에 개발 시간을 다축할수가 있다.
	
===========================================================

#스프링 프레임워크
	경량 프레임워크 (light-weight)
	예전 프레임워크는 다양한 경우를 처리할수 있는 다양한 기능을 가지도록 만들다보니,
	하나의 기능을 위해서 너무 많은 구조가 필요했다.
	기술이 너무나 복잡하고 방대했기 때문에, 전체를 이해하고 개발하기에는 어려움이 많았다.
	그래서 스프링 프레임워크가 등장했고, 특정 기능을 위주로 간단한 JAR파일 등을 이용해서
	모든 개발이 가능하도록 구성되어 있다.

#스프링 프레임워크의 장점
	-복잡함에 반기를 들어서 만들어진 프레임워크(경량화)
	-프로젝트 전체 구조를 설계할 때 유용한 프레임워크(서버 제작의 빠른 속도)
	-다른 프레임워크들의 포용, 여러 프레임워크를 혼용해서 사용가능하며, 이를 접착성이라고 한다.
	-개발 생산성과 개발도구의 지원

===========================================================

#스프링 프레임워크의 특징 (*아래 다 알아야한다*)
	-POJO 기반의 구성
	-DI를 통한 객체간의 관계 구성
	-AOP 지원
	-트랜잭션 관리
	-편리한 MVC 구조
	-WAS에 종속적이지 않은 개발 환경

#스프링 부트
	스프링 프레임워크를 사용함에 있어서 초기 설정 및 필요한 라이브러리에 대한
	설정의 어려움이 많으며, 시간이 너무 많이 걸리기 때문에 자동 설정(AutoConfiguration)과
	개발에 필요한 모든 것을 관리해주는 스프링 부트를 선호한다. 각 코어 및 라이브러리의 버전
	들도 맞추어야 하지만 스피링 부트를 사용하면 이러한 복잡성을 해결하기에도 좋다.

===========================================================

[ POJO(Plain Old Java Object)기반의 구성 ]
	오래된 방식의 간단한 자바 객체라는 의미이며, JAVA 코드에서 일반적으로
	객체를 구성하는 방식을 스프링 프레임워크에서 그대로 사용할 수있다는 말이다.

[ 의존성 주입(DI)를 통한 객체간의 관계 구성 ]
	의존성(Dependency)이란 하나의 객체가 다른 객체 없이 제대로 된 역할을 할수 없다는 것을 의미한다.
	예를 들어 A객체가 B객체 없이 동작이 불가능한 상황을 'A'가 'B'에 의존적이다 라고 표현한다.
	
	주입(Injection)은 말 그대로 외부에서 밀어 넣는 것을 의미한다.
	예를 들어 어떤 객체가 필요로하는 객체를 외부에서 밀어 넣는 것을 의미한다.
	주입을 받는 입장에서는 어떤 객체인지 신경 쓸 필요가 없고 어떤 객체에 의존하든 자신의 역할은 변하지 않는다.

	**의존성
	a---------------------------------->b
	a객체에서 b객체를 직접 생성

	**의존성 주입
	a---------------???--------------->b
	a는 b가 필요하다는 신호를 보내고, ???가 b객체를 외부에서 생성하여 주입하게 된다.

	의존성 주입방식을 사용하기 위해서는 ???라는 존재가 필요하게 된다.
	스프링 프레임워크에서는 ApplicationContext가 ???라는 존재이며,
	필요한 객체들을 생성하고, 필요한 객체들을 주입해주는 역할을 한다.
	따라서 개발자들은 기존의 프로그래밍과 달리 객체와 객체를 분리해서 생성하고,
	이러한 객체들을 엮는(wiring) 작업의 형태로 개발하게 된다.

	ApplicationContext가 관리하는 객체들을 빈(Bean)이라고 부르고, 빈과 빈사이의 의존관계를 처리하는 방식으로는
	XML, 어노테이션, JAVA 방식이 있다.


[ AOP 지원]
	관점 지향 프로그래밍
	좋은 개발환경에서는 개발자가 비지니스 로직에만 집중할수 있게 한다.
	스프링 프레임워크는 반복적인 코드를 제거해줌으로써 핵심 비지니스 로직에만 집중할 수 있는 방법을 제공한다.
	보안이나 로그, 트랜잭션, 예외처리와 같은 비지니스 로직은 아니지만, 반드시 처리가 필요한 부분을
	관심사(cross-concern)라고 한다. 스프링 프레임워크는 이러한 횡단 관심사를 분리해서 제작하는 것이 가능하고
	횡단 관심사를 모듈로 분리하는 프로그래밍을 AOP라고 한다. 핵심 비지니스 로직에만 집중하여 코드 개발이
	가능해지고, 각 프로젝트마다 다른 관심사 적용시 코드 수정을 최고할수 있으며,
	원하는 관심사의 유지보수가 수월한 코드로 구성이 가능해진다.	


[ 트랜잭션의 지원 ]
	DB 작업 시 트랜잭션을 매번 상황에 맞게 코드로 작성하지 않고, 어노테이션이나 XML로
	트랜잭션을 쉽게 관리 할 수있다.
	

[ 편리한 MVC 구조 ]



[ WAS에 종속적이지 않은 개발 환경 ] - 단위 테스트 
	전체 Application을 실행하지 않아도 기능별 단위 테스트가 용이하기 때문에
	버그를 줄이고 개발 시간을 단축할 수 있다.

===========================================================

프로젝트 기본 경로
   1) src/main/java         : 서버단 JAVA 파일
   2) test/main/java         : 단위 테스트 JAVA 파일
   3) src/main/resources      : 설정 파일 및 뷰단
   4) resources/static         : css, js 파일 경로
   5) resources/templates      : html 파일 경로
   6) pom.xml               : 라이브러리 의존성 관리
   7) application.properties   : 서버 및 DB, 라이브러리 설정 파일

===========================================================


Qualifier
	@Autowired를 통해 객체를 주입할 때 같은 타입의 객체가 여러개 있다면, 구분할 수 없다.
	이때, @Qualifier를 통해 식별자를 부여하면 원하는 객체를 주입받을수 있다.
  
# Spring MVC(Front-Controller 패턴)

       		      HandlerMaping
REQUEST     ①         ②↕             ③                        ④
 	  ]      ↔   DispatcherServlet   ↔  HandlerAdapter   ↔  Controller
RESPONSE   ⑦    ⑥↕        ⑤↕
                      View   ViewResolver
                       ↕
                HTML 및 기타

============================================================

Spring MVC 패턴의 특징
   - HttpServletRequest, HttpServletResponse를 거의 사용할 필요 없이 기능 구현
   - 다양한 타입의 파라미터 처리, 다양한 타입의 리턴 타입 사용 가능
   - GET 방식, POST 방식 등 전송 방식에 대한 처리를 어노테이션으로 처리 가능
   - 상속/인터페이스 방식 대신 어노테이션으로만 설정 가능

============================================================


Dispatcher Servlet에서 Dispatch는 사전적 의미로 '보내다' 라는 의미를 사지고 있습니다. 
클라이언트의 모든 요청을 한 곳으로 받아서 처리하는 역할을 수행합니다. 
즉, 서버 가장 앞단에서 사용자의 요청을 가장 먼저 받아 요청에 알맞는 Hendler, 
즉, Controller에서 위임해주는 역할을 수행합니다.
Handler의 실행 결과는 HTTP Response 형태로 만들어서 다시 반환을 합니다.
사용자의 요청은 Dispatcher Servlet에서 시작해서 Dispatcher Servlet에서 끝납니다.
사용자의 요청이 Dispatcher Servlet으로 전달된다.
Handler Mapping 또는 Controller 에 전달을 한다.
처리된 결과 값을 Model 형태로 Dispatcher에 반환하고,
사용자에게 보여주고자 하는 View 형태로 ViewResolver가 Page를 생성을 하고,
이러한 Page 값에 Model을 포함시켜서 전달을 하게 된다.

#3-tier
	스프링 프로젝트는 3-tier 방식으로 구성한다.

	[Presentation Tier - 화면 계층]
		-화면에 보여주는 기술을 사용하는 영역.
		-컨트롤러에서 사용자의 요청에 맞는 응답처리를 진행하며,
		-HTML엔진(Thymeleaf),HTML등이 담당하는 영역이다.
		-화면 구성이 이에속한다.

	[Business Tier - 비지니스 계층]
		-순수한 비지니스 로직(메인로직)을 담고 있는 영역.
		-고객이 원하는 요구사항을 반영하는 계층이기 떄문에 서비스에 있어서 가장 중요한 영역이다.
		-이영역의 설계는 고객의 요구 사항과 정확히 일치해야 하며, 서비스 영역이다.

	[Persistence Tier - 영속 계층 혹은 데이터 계층]
		-데이트가 어떤 방식으로 보관하고, 사용하는 가에 대한 설계가 들어가는 게층.
		-일반적으로 DBMS를 많이 이용하지만, 상황에 따라서 네트워크 호출 혹은
		-원격 호출등의 기술이 접목될 수 있다.

각 영역은 독립적으로 설계되어 나중에 특정한 기술이 변하더라도 필요한 부분을 전자제품의 부품처럼
쉽게 교환하루 있게 하자는 방식이다. 각 연결 부위는 인터페이스를 이용해서 설계하는 것이 일반적인 구성 방식이다.

==========================================================================
		Presentation ----> Business ----> Persistence ----> DBMS
	    		  Controller        Service(interface)    Mapper(interface)    
==========================================================================
				  

#비지니스 계층
	프레젠테이션 계층과 영속 계층의 중간 다리 역할을 한다.
	영속 계층은 DBMS를 기준으로, 비지니스 계층은 로직을 기준으로 처리한다.
	예를 들어 쇼핑몰에서 상품 구매시 포인트 적립을 한다고 가정한다면,
	영속 계층의 설계는 상품,회원으로 나누어 설계하지만 비지니스 계층은
	상품 영역과 회원 영역을 동시에 사용해서 하나의 로직을 처리하게 된다.
	이때 하나의 서비스에 필요한 여러개의 쿼리 메소드를 하나로 묶어주는 역할이 필요한데,
	이를 Service 객체로 사용한다.


순서 -> MAPPER-> 인터페이스MAPPER -> DAO -> SERVICE -> CONTROLLER
	    		 	 단위test         단위test   단위test         단위test



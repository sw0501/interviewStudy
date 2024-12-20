# JAVA 예상 면접 질문

## WAS와 WS 차이

- ### WAS (Web Application Server)
  - 비즈니스 로직을 넣을 수 있다.
    - 클라이언트 요청에 따라 DB와 통신하여 동적 콘텐츠 제공
  - Tomcat, PHP, ASP.NET 등
- ### WS (Web Server)
  - 비즈니스 로직을 넣을 수 없다.
    - 클라이언트 요청에 따른 단순 페이지 제공
  - Nginx, Apache

## Spring Framework

- 자바 개발을 편리하게 해주는 오픈소스 프레임워크
- ### 특징
  - 경량 컨테이너로서 자바 객체를 직접 관리
    - 각각의 객체 생성, 소멸과 같은 라이프사이클을 관리하며 스프링으로부터 필요한 객체를 얻어올 수 있다.
  - 제어의 역전 (IoC) 기술을 통해 어플리케이션의 느슨한 결합을 도모
    - 컨트롤의 제어권이 사용자가 아닌 프레임워크에 있어서 필요에 따라 스프링에서 사용자의 코드를 호출
  - 의존성 주입 (DI) 지원
    - 각각의 계층이나 서비스들 간의 의존성이 존재할 경우 프레임워크가 서로 연결해준다.
  - 관점 지향 프로그래밍 (AOP) 지원
    - 트랜잭션이나 로깅, 보안과 같이 여러 모듈에서 공통적으로 사용하는 기능의 경우 해당 기능을 분리하여 관리할 수 있다.

## @RequesteBody, @RequestParam, @ModelAttribute 차이

- ### @RequestBody
  - 클라이언트가 JSON 형태로 전송하는 HTTP Body의 내용을 Java Object로 변환시켜주는 역할
- ### @RequestParam
  - HTTP 요청 파라미터를 받이 위해서 사용
- ### @ModelAttribute
  - HTTP Body와 HTTP 파라미터의 값들을 생성자, Getter, Setter를 통해 주입하기 위해 사용한다.

## Spring Boot와 Spring Framework의 차이

- Spring 프로젝트의 경우 초기에 다양한 환경설정을 해야한다.
- Spring Boot 프로젝트의 경우 Auto Configuration을 통해 설정의 많은 부분을 자동화 할 수 있습니다.
- 또한 내장 톰캣을 제공하여 바로 서버 실행 가능

## Spring MVC

- MVC란 Model - View - Controller 디자인 패턴의 약자입니다.
- ### Model
  - 데이터 관리 및 비즈니스 로직을 처리하는 부분 ex\) DAO, DTO, Service 등
- ### View
  - 비즈니스 로직의 처리 결과를 통해 유저 인터페이스가 표현되는 구간 ex\) html, jsp, JSON Response
- ### Controller
  - 사용자의 요청을 처리하고 Model과 View를 중계하는 역할

## MVC의 데이터 요청 처리 흐름

1. Client가 URL을 통해 요청
2. 디스패처 서블릿이 핸들러 매핑을 통해 어떤 컨트롤러에서 요청을 처리할 지 확인
3. 디스패처 서블릿이 핸들러 어댑터에게 요청 전달 맡김
4. 핸들러 어댑터가 해당 컨트롤러에게 요청 전달
5. 컨트롤러가 서비스에 접근해서 비즈니스 로직 처리 후 반환할 뷰 이름 반환
6. 디스패처 서블릿에서 뷰 리졸버를 통해 반환할 뷰 검색
7. 컨트롤러에서 뷰에 전달할 데이터 추가
8. 데이터가 추가된 뷰 반환

## 제어의 역전 IoC

- 제어의 역전 (IoC)란 모든 객체에 대한 생성, 라이프사이클 등 제어권을 개발자가 아닌 IoC 컨테이너에게 넘긴 것을 말한다.
- 스프링에서는 IoC 컨테이너에 객체들을 생성하면 객체끼리 의존성을 주입(DI)하는 역할을 하고 컨테이너에 등록한 객체들을 빈이라고 한다.

## 스프링에서 빈을 등록하는 방법

1. @Component 어노테이션 사용

   - @Controller, @Service, @Repository 모두 @Component를 포함하고 있음
   - @Controller : View를 반환하기 위해 사용
   - @Service : 비즈니스 로직을 수행 @Repository : DB에 접근하는 메소드를 사용하기 위한 인터페이스

2. 자바 코드로 직접 스프링 빈 등록
   - 설정 클래스를 만든 후 @Configuration 어노테이션 추가
   - 특정 타입을 리턴하는 메소드를 만들고 @Bean 어노테이션을 붙이면 자동으로 해당 타입의 빈 객체 생성

## 의존성 주입(DI)

- 의존성 주입은 필요한 객체를 직접 생성하는 것이 아닌 외부로부터 객체를 받아서 사용하는 것
- 객체간의 결합도를 줄임
- 코드의 재사용성을 높일 수 있음
- Test 용이
- 객체 간 의존성을 줄이거나 없앨 수 있다.
- ### 의존성 주입 방법 3가지
  - 필드 주입
    - 필드에 @Autowired 어노테이션을 붙여서 주입, (프레임워크에 의존적)
  - 세터 주입
    - Setter 메소드에 @Autowired 어노테이션을 붙이는 방법, (객체에 final 키워드 사용 불가능)
  - 생성자 주입
    - 클래스의 생성자가 하나이고 생성자로 주입받을 객체가 빈으로 등록되어 있다면 @Autowired를 생략하고 주입이 가능
    #### 장점
    - 순환 참조 방지 가능
    - 불변성
    - 테스트 용이

## Filter, Interceptor, AOP

- ### Filter (Dispathcher Servlet 전 수행)
  - 요청과 응답을 거른 뒤 정제하는 역할
  - Spring Container가 아닌 톰캣과 같은 웹 컨테이너에 의해 관리 됨
  - 디스패처 서블릿에 요청이 전달되기 전 / 후에 url 패턴에 맞는 모든 요청에 대해 부가 작업을 처리할 수 있는 기능 제공
  - 사용 예시
    - 보안 인증/인가 작업
    - 모든 요청에 대한 로깅 또는 검사
    - 이미지/데이터 압축
    - Spring과 분리되어야 하는 기능
- ### Interceptor (Dispathcher Servlet에서 컨트롤러 호출 하기 전 전 수행)
  - 요청에 대한 작업 전 / 후로 가로채 요청과 응답을 참조하거나 가공하는 역할
  - Spring Context에서 동작
  - 디스패처 서블릿이 Controller를 호출하기 전 / 후에 인터셉터가 끼어들어 응답을 참조하거나 가공할 수 있는 기능 제공
- ### AOP (메소드 동작 전후 과정에 부가 로직 처리)
  - 비즈니스 로직에 있는 공통 관심사항을 분리하여 각각 모듈화 하는 것
  - 공통 모듈인 인증, 로깅, 트랜잭션 처리에 용이하다.

## Lombok 라이브러리

- 메소드를 컴파일하는 과정에 개입하여 추가적인 코드를 만들어낸다. (어노테이션 프로세싱)
- 어노테이션 프로세싱은 자바 컴파일러가 컴파일 단계에서 어노테이션을 분석하고 처리하는 기법
- ### 사용시 주의해야 할 어노테이션
  - @AllArgsConstructor
    - 객체 내부의 인스턴스 멤버를 모두 가지고 있는 생성자를 생성하는 어노테이션
    - 인스턴스 멤버의 순서가 생성자의 파라미터 순서와 동일하다.
  - @RequiredArgsContstructor
    - 객체 내부의 final, @Notnull이 붙은 인스턴스멤버들을 가지고 있는 생성자를 생성하는 어노테이션
    - 인스턴스 멤버의 순서가 생성자의 파라미터 순서와 동일하다.
  - @EqulasAndHashCode
    - 불변객체인 경우에는 괜찮지만 그렇지 않은 경우에는 인스턴스 멤버 값이 변경되어 문제가 생길 수 있음
  - @Data
    - 위의 어노테이션을 모두 포함하고 있음
  - @ToString
    - JPA에서 양방향 관계일 때 두 객체가 서로를 참조하다보면 발생할 수 있음

## VO, BO, DAO, DTO

- ### VO (불변)
  - Value Object : 실제 사용할 데이터만을 저장하는 객체
- ### BO (가변)
  - Business Object : DAO를 활용해 비즈니스 로직을 처리하는 객체 (Service에 해당)
- ### DAO (불변)
  - DB의 데이터 접근을 하기 위한 객체 (Repositoy or Mapper에 해당)
- ### DTO (가변)
  - 각 계층간의 데이터 교환을 위한 객채 (계층에는 Controller, View, 등)

## 대용량 트래픽에서 장애 발생 시 어떻게 대응할 지

- 스케일 업을 통해서 하드웨어의 스펙을 향상시킴
- 스케일 아웃을 통해 서버를 여러 대 추가하여 트래픽 분산

## Spring에서 싱글톤 패턴

- Spring에서는 bean 생성 시 별다른 설정 없는 경우 default로 싱글톤이 적용됨
- 컨테이너를 통해 싱글톤 객체를 생성하고 관리
- 요청이 들어올 때마다 매번 객체를 생성하고 관리하지 않기 때문에 효율적인 사용 가능

## 프로토타입 빈

- 일반적으로 Spring에서 빈은 싱글톤 패턴이 적용되어 있는데 스코프를 프로토타입으로 설정할 경우 컨테이너에게 빈을 요청할 때 마다 매번 새로운 객체를 생성하여 반환해준다.

## @Transactional 동작 원리

- @Transactional 어노테이션을 메소드 또는 클래스에 명시하면 AOP를 통해 Target이 상속하고 있는 인터페이스 도는 Target 객체를 상속한 Proxy 객체가 생성되며 Proxy 객체의 메소드를 호출하면 Target 전 후로 트랜잭션 처리를 수행한다.

## ORM?

- Object Relational Mapping으로, 객체 관계 매핑을 의미
- Java에서는 Entity 객체를 활용하여 DB 테이블과 매핑하는 Spring Data JPA 주로 사용

## ORM의 장점

- 객체 지향적으로 DB 조작 가능
- SQL 작성하지 않아 개발 비용 감소
- 코드 가독성 및 재사용성, 유지보수성 좋아짐
- 특정 DB에 대한 종속성 감소

## ORM JPA Spring Data JPA 차이

- JPA는 자바 진영 표준 ORM, 인터페이스의 집합
- JPA의 대표적인 구현체인 Hibernate를 개발자가 사용하기 쉽게 모듈화한 것이 Spring Data JPA이다

## JPA N+1 문제

- 1번의 쿼리를 날렸을 때 의도하지 않은 N번의 쿼리가 추가적으로 실행되는 것을 의미
- Fetch Join을 사용하여 해결하는 방법이 있음
- JPA에서는 연관관계를 가진 엔터티를 조회할 때 한 쪽 테이블만 조회하고 연결된 테이블은 따로 조회를 하기 때문에 발생
- Fetch Join을 하면 두 테이블을 조인하여 한번에 모든 데이터를 가져오기 때문에 N+1 문제를 해결할 수 있음

## ORM 사용 시 쿼리가 복잡해지는 경우

- 복잡한 쿼리나 동적 쿼리를 사용해야 할 경우에 JPQL과 QueryDSL을 사용하는 것이 권장된다.

## Mybatis에서 객체와 매핑되는 과정

- Java 객체와 SQL 데이터베이스 간의 매핑을 처리하는 Persistent 프레임워크
- MyBatis는 SQL을 직접 잓어하고 데이터베이스오 상호작용하는 방식을 취함
- XML 매퍼 파일을 통해서 SQL 쿼리와 매핑 규칙을 정의한다.
- SQL 매핑 어노테이션을 통해 직접 정의
- SqlSession
- Mapper 인터페이스 : 매퍼 XML 파일과 연결되는 Java 인터페이스

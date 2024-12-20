# 공통 질문

---

## Restful API 설명

> HTTP 통신을 Rest 설계 규칙을 잘 지켜서 개발한 API
> Rest 설계 규칙은 URI는 정보의 자원만 표현하고, 상태와 행위는 HTTP Method에 명시하는 것

## 프레임워크와 라이브러리의 차이

- 프레임워크 : 제어권을 개발자가 아닌 프레임워크가 소유
- 라이브러리 : 라이브러리에 대한 제어권을 개발자가 소유

## Call By Value, Reference 차이

- 인자로 들어온 값을 복사하여 처리
- 인자로 들어온 값의 주소를 참조하여 직접 영향
- Java는 모든 것이 Value

## CORS

- 도메인이 서로다른 2개의 사이트가 데이터를 주고 받을 때 보안 상의 이유로 브라우저에서 제한하는 정책
- 데이터를 받기 위해서는 Response 헤더에 이를 명시

## 절차 지향 프로그래밍과 객체 지향 프로그래밍 차이

- ### 절차 지향
  - 순차적인 처리를 중요시하는 프로그래밍
  - 코드 순서가 바뀌면 동일한 결과 보장하기 어려움
- ### 객체 지향
  - 실제 사물을 객체로 모델링하여 개발을 진행
  - 누가 어떤 일을 할 것인가를 중점으로 개발

## OAuth 2.0 흐름

1. 사용자가 클라이언트에게 사용 요청
2. 클라이언트는 인증 서버에게 승인 코드를 요청
3. 인증 서버에서 로그인 페이지 전달
4. 사용자 로그인 이후에 클라이언트에게 승인 코드 전달
5. 승인 코드를 바탕으로 인증 서버에게 액세스 토큰 요청
6. 발급 받은 액세스 토큰을 기반으로 리소스 서버에게 자원 요청 및 응답

## 동적 쿼리

- 실행 시 특정 조건이나 상황에 따라 쿼리 문장이 변경되는 쿼리문
- Java에서는 QueryDSL 활용

## TDD란

- 테스트 주도 개발의 약자
- 테스트 케이스를 작성하고 이를 통과한 후에 상황에 맞게 개발 진행

## DDD

- 도메인 주도 개발
- 비즈니스 관점에서 도메인 별로 나누어 설계하는 개발 방식

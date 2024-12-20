## 모놀리식 아키텍처 (MA)

## 마이크로 서비스 아키텍처 (MSA)

- 하나의 시스템을 독립적으로 배포 가능한 각각의 서비스로 분할
- 각각의 서비스는 API를 통해 데이터를 주고받으며 하나의 큰 서비스 구성
- #### 장점
  - 일부 서비스 장애가 발생해도 전체 서비스에 영향을 미치지 않는다
  - 각각의 서비스는 서로 다른 언어와 프레임워크로 구성 가능
  - 서비스 확장 용이
- #### 단점
  - 서비스가 분리되어 있어 테스트나 트랜잭션 처리가 어려움
  - 서비스 간 API 통신을 진행해서 성능 저하

## 헥사고날 아키텍처 (Port and Adaptor)

- 도메인 비즈니스 로직이 외부요소에 의존하지 않는 아키텍처
- 포트 : 외부 요청이 비즈니스 로직으로 접근하거나, 내부에서 처리된 데이터를 외부 어댑터로 전달할 때 사용
- 유스케이스 : 인커밍 포트 구현체
- 인커밍 어댑터 : 컨트롤러
- 아웃고잉 어댑터 : 아웃고잉 포트를 구현하는 구현체
- ## 요청 동작 순서
- ### 장점
  - 기능 확장 용이
  - 외부로 부터 비즈니스 모델 분리
  - TDD, DDD 적용 편리
- ### 단점
  - 코드가 길어진다
  - 불필요한 오버헤드 발생

## 레이어드 아키텍처

- Contorller
- Service
- Repository
- DB에 직접적으로 연결되기 때문에 의존성 발생

## 클린 아키텍처

# JAVA 예상 면접 질문

## JAVA 언어의 특징

- 객체 지향 프로그래밍 언어이다.
- int, char, float, double 등 기본 자료형을 제외한 모든 요소들이 객체로 표현
- 객체 지향의 개념의 특징인 캡슐화, 상속, 다형성이 잘 적용된 언어
- ### 장점
  - JVM (Java Virtual Machine) 위에서 동작하기 때문에 운영체제에 독립적이다.
  - GC (Garbage Collection)을 통한 자동적인 메모리 관리가 가능하다.
- ### 단점
  - JVM 위에서 동작하기 때문에 실행속도가 C, C++ 언어에 비해서 상대적으로 느리다.
    - GC와 인터프리터 변환 과정 또한 JAVA의 속도를 느리게 만드는 원인

## JVM 역할

- 스택 기반으로 동작하며 JAVA Byte Code를 OS에 맞게 해석 해주는 역할
- 가비지 컬렉션을 통해 자동적인 메모리 관리를 해준다.

## JAVA 컴파일 과정?

1. 개발자가 JAVA 파일을 생성 (.java)
2. Build 진행
3. Java Compiler를 통해 (javac) 자바바이트 파일 생성 (.class)
4. 클래스 로더를 통해 JVM 메모리에 로드
5. 실행엔진(인터프리터)를 통해 기계어로 해석됨

## JAVA에서 Call By Value, Call By Reference

- JAVA에서는 모든 동작이 Call By Value로 동작함
- 예시

  ```java
  User a = new User("abc");

  foo(a);

  public void foo(User b){
    b = new User("cde");
  }
  ```

  > 이때 User 객체 b는 a의 주소값을 복사하여 함수의 인자로 전송된다.
  >
  > 때문에 b에 새로운 User 객체 "cde"를 할당하게 되면 a의 객체가 바뀌는 것이 아닌
  >
  > b에 새로운 User 객체 "cde"의 주소값을 복사하여 할당하게 됨

## JAVA 제공 원시 타입

- 정수형 : byte, short, int, long
- 실수형 : float, double
- 문자형 : char
- 논리형 : boolean

## 오버라이딩과 오버로딩의 차이

- ### 오버라이딩
  - 상위 클래스의 메소드를 하위 클래스에서 재정의 하는 것
- ### 오버로딩
  - 매개변수의 개수나 타입을 다르게 하여 같은 이름의 메소드를 여러 개 정의하는 것

## 객체 지향 프로그래밍 (OOP)

- 프로그램에 필요한 객체를 정의하고 객체들 간 상호작용을 통해 프로그램을 만드는 것
- 모듈 재사용을 통한 확장 및 유지 보수가 쉽다.
- 특징
  - ### 캡슐화
    - 접근제어자를 활용하여 클래스 내부의 변수나 메소드에 접근하는 것을 막는 것
    - 허가받지 않은 사용자로부터 데이터를 보호할 수 있다.
  - ### 상속
    - 기존의 클래스를 재활용하여 새로운 클래스를 작성하는 방법
    - 상위 클래스의 속성과 기능들을 하위 클래스에서 간편하게 사용할 수 있도록 한다.
  - ### 다형성
    - 객체의 속성이나 기능이 여러 가지 형태를 가질 수 있는 성질
    - 오버로딩, 오버라이딩이 있음
  - ### 추상화
    - 객체의 공통적인 속성과 기능을 추출하여 정의하는 것
    - JAVA에서는 추상 클래스와 인터페이스로 이를 활용함

## try-with-resources

- try-catch-finally의 문제점을 보완하는 개념
- try() 안에 자원 객체를 전달하면 try 블록이 끝나고 자동으로 지원을 해제하는 기능
- finally 구문이나 catch에 종료 구문을 작성할 필요가 없음
- AutoCloseable 인터페이스 구현체만 전달 가능

## 불변 객체

- 객체 생성 이후 내부의 상태가 변하지 않는 객체
- 원시 타입인 경우 final 키워드를 사용하여 불변 객체를 만들 수 있음
- 참조 타입인 경우에는 추가적인 작업 필요

  ### 참조 타입인 경우

  - 일반 객체를 참조하는 경우 필드의 참조 변수에 final 키워드를 붙여 불편 객체로 변경
  - 배열이나 리스트의 경우에는 내부 값을 복사하여 새로운 배열이나 리스트를 생성하고 반환하는 경우에도 clone 값을 주는 방식으로 불변으로 만들 수 있음

  ### 불변 객체나 final을 사용해야 하는 이유

  - Thread-safe하여 병렬 ㅍ로그래밍에 유용하며, 동기화를 고려하지 않아도 된다.
  - 실패 원자적인 메소드를 만들 수 있다.
  - 부수효과를 피해 오류를 최소화 할 수 있다.
  - 메소드 호출 시 파라미터 값이 변하지 않는다는 것을 보장할 수 있다.
  - 가비지 컬렉션 성능을 높일 수 있다.

## 추상 클래스와 인터페이스

- ### 추상 클래스
  > 클래스 내 추상 메소드가 하나 이상 포함되어있거나 abstract로 정의된 클래스
- ### 인터페이스
  > 모든 메소드가 추상 메소드로만 이루어져 있는 것
- ### 공통점
  - new 연산자로 인스턴스를 생성할 수 없다.
  - 사용하기 위해서는 하위 클래스에서 추상 메소드를 구현해야한다.
- ### 차이점
  - 인터페이스는 자신을 상속받는 클래스가 특정한 메소드를 반드시 구현하도록 강제한다.
  - 추상 클래스는 상속받는 클래스들의 공통적인 로직을 추상화 시키고 기능 확장을 위해서 사용한다.
  - 추상 클래스는 다중 상속이 불가능하지만 인터페이스는 다중 상속이 가능하다
    - 이유 : 인터페이스의 경우 모든 메소드가 추상 메소드로 이루어져 있어 다이아몬드 문제가 발생하지 않는다.

## 싱글톤 패턴

- 단 하나의 인스턴스만을 사용하는 디자인 패턴
- 인스턴스가 1개만 존재한다는 것을 보장하며 동일한 인스턴스를 자주 생성해야 하는 경우에 주로 사용
  - 메모리 낭비 방지
- 대표 예시는 Spring Bean으로 스프링 빈 등록 후 스프링 컨테이너에서 모든 빈들을 싱글톤으로 관리한다.
- ### 생성 방법
  - 클래스 내 private static final 자기자신의 인스턴스 필드
  - private 생성자
  - public static 인스턴스 접근 메소드

## 가비지 컬렉션

- 동적으로 할당된 메모리 영역 중에서 필요없어진 메모리 영역을 회수하여 메모리를 관리하는 기법
- 개발자가 컨트롤할 수 없음 (호출은 가능하지만 성능에 매우 안 좋은 영향을 끼치기 때문에 거의 사용하지 않음)
- 컬렉션 과정
  1. GC 작업 수행을 위해 JVM이 어플리케이션 실행을 잠시 멈춤
  2. GC를 실행하는 쓰레드를 제외한 모든 쓰레드들의 작업을 중단
  3. 사용하지 않는 메모리를 제거
  4. 작업 재개

## 객체지향의 설계 원칙 (SOLID)

- ### 단일 책임 원칙 (Single Responsibility principle)
  - 하나의 클래스는 하나의 책임만 가져야 한다. (비즈니스 로직 관점) `ex) 주문, 결제`
- ### 개방-폐쇄 원칙 (Open-Close principle)
  - 확장엔 열려있고 수정엔 닫혀있어야 한다.
  - 이를 적용하기 위한 주요 매커니즘으로 추상화와 다형성이 있다.
- ### 리스코프 치환 원칙 (Liskov substitution principle)
  - 하위 타입은 항상 상위 타입을 대체할 수 있어야 한다.
  - 부모 클래스가 들어갈 자리에 자식 클래스를 넣어도 역할을 하는데 문제가 없어야 한다.
- ### 인터페이스 분리 원칙 (Interface segregation principle)
  - 인터페이스 내에 메소드는 최소한 일수록 좋다.
  - 하나의 범용적인 인터페이스보다 여러 개의 분리된 인터페이스가 낫다 (SRP와는 다른 해결책)
- ### 의존관계 역전 원칙 (Dependency inversion principle)
  - 고수준 모듈이 저수준 모듈에 직접 의존하는 것을 피해야한다.
    - 고수준 모듈 : 변경이 없는 추상 클래스 or 인터페이스
    - 저수준 모듈 : 추상화된 클래스나 인터페이스를 상속받은 구현체 클래스
  - 구체적인 클래스보다 상위 클래스, 인터페이스, 추상 클래스와 같이 변하지 않을 가능성이 높은 클래스와 관계를 맺어라
  - DIP 원칙을 따르는 가장 인기있는 방법은 의존성 주입이다.

## 자바 메모리 영역

- 자바의 메모리 공간은 크게 Method 영역, Stack 영억, Headp 영역으로 구분되며 데이터 타입에 따라 할당
- ### 메소드 영역
  - 전역 변수와 static 변수를 저장
  - 프로그램 시작부터 종료까지 메모리에 남아있음
  - 할당되는 시점 : 클래스 로딩 시
- ### 스택 영역
  - 지역 변수와 매개 변수 데이터 값이 저장
  - 메소드가 호출될 때 메모리에 할당되고 종료되면 메모리 해제
  - LIFO 구조를 가지고 변수에 새로운 데이터가 할당되면 이전 데이터는 삭제
  - 할당되는 시점 : 메소드 호출 시
- ### 힙 영역
  - new 키워드로 동적으로 생성되는 객체, 배열 등이 힙 영역에 저장
  - 가비지 컬렉션에 의해 메모리가 관리
  - 할당되는 시점 : 런타임시

## 클래스와 객체

- ### 클래스
  - 객체를 만들어내기 위한 설계도
- ### 객체
  - 객체는 일반적으로 존재하는 것을 추상화하여 속성과 기능으로 표현한 것
- 객체는 클래스를 통해 생성되며 메모리에 할당되어 실제로 활용되는 것을 인스턴스라고 부름

## 생성자

- 클래스와 같은 이름의 메소드로 객체가 생성될 시 호출되는 메소드
- 명시적으로 만들지 않으면 default로 만들어짐
- 매개변수를 다르게하여 오버로딩이 가능

## Wrapper Class, Boxing, Unboxing

- 기본 자료형에 대한 객체 표현을 Wrapper Class라고 함
- 기본 자료형을 Wrapper Class로 변환하는 것을 Boxing
- Wrapper Class에서 기본 자료형으로 변환하는 것 Unboxing

## Synchronized

- 여러 개의 쓰레드가 한 개의 자원을 사용하고자 할 때, 현재 데이터를 사용하는 쓰레드를 제외하고 나머지 쓰레드들은 데이터에 접근할 수 없게 막는 개념
- 멀티 쓰레드 환경에서 쓰레드간 동기화를 시켜 데이터의 thread-safe를 보장
- 남용할 경우 오히려 프로그램 성능 저하 발생

## new String ()과 리터럴 ("")의 차이

- new String()은 new 키워드로 새로운 객체를 저장하기 때문에 Heap 메모리 영역에 저장됨
- ""는 Heap 안에 있는 String Constant Pool 영역에 저장
  - 리터럴로 같은 값을 참조하는 서로 다른 String 객체는 참조하는 주소값이 같기 때문에 객체 비교 시 true 반환
- 객체 참조, 복사, 값 수정 및 비교 시 위의 내용 때문에 원하는대로 동작하지 않을 수 있음

## String, StringBuffer, StringBuilder 차이를 설명

- String은 불변 속성을 가짐, StringBuffer와 StringBuilder는 가변 속성
- StringBuffer는 동기화를 지원하며 thread-safe 보장하여 멀티 쓰레드 환경에서 주로 사용
- Stringbuilder는 동기화를 지원하지 않아 싱글 쓰레드 환경에서 주로 사용

## String 객체가 불변인 이유

- String 객체들은 Heap의 String Pool 공간에 저장되는데 문자열이 String Pool에 존재하는 경우 새로 생성하지 않고 Pool에 있는 객체를 직접 사용하기 때문에 성능 향상 가능
- thread-safe 불변이기 때문에 여러 쓰레드에서 동시에 String 객체를 참조해도 안전하다

## 접근 제한자

- 변수 혹은 메소드의 접근 범위를 설정해주기 위해 사용하는 예약어
- 캡슐화와 관련 있음
- ### public
  - 접근 제한 없음
- ### protected
  - 해당 패키지 내, 다른 패키지에서 상속받아 자손 클래스에서 접근 가능
- ### default
  - 해당 패키지 내에서만 접근 가능
- ### private
  - 해당 클래스에서만 접근 가능

## 클래스 멤버 변수 초기화 순서

1. static 선언부 : 클래스 로드 시 초기화
2. 필드 변수 선언부 : 객체 생성 시 생성자 block보다 먼저 초기화
3. 생성자 block : 객체 생성 시 초기화

## static 키워드

- static 키워드를 사용한 변수나 메소드는 클래스가 메모리에 올라가는 클래스 로드 시 자동으로 생성된다.
- 인스턴스 생성 없이 사용할 수 있음
- 프로그램이 종료될 때까지 메모리에 존재한다.
- ### 사용하는 이유
  - 자주 변하지 않는 값이나 공통으로 사용되는 공용 자원에 대한 접근 방법으로 주요 사용
  - 매번 객체 생성을 통해서 메모리에 로딩 시 낭비가 된다.
  - 싱글톤 패턴에서 사용
- ### 단점
  - Static을 많이 사용하게 될 경우 메모리에 할당이 많이 되기 때문에 성능에 악영향을 끼친다.
  - 인스턴스를 생성하지 않고 바로 사용하기 때문에 객체지향적이지 못하다
  - Interface를 구현하는데 사용될 수 없다.

## Inner Class

- 내부 클래스에서 외부 클래스의 멤버에 손쉽게 접근할 수 있다.
- 서로 관련 있는 클래스를 논리적으로 묶어서 표현함으로써, 캡슐화를 증가시키고, 코드의 복잡성 낮춤
- 외부에서는 내부 클래스에 접근이 불가능하기 때문에 코드의 보안성을 높일 수 있음

## 리플렉션

- 구체적인 클래스 타입을 알지 못해도 그 클래스의 메소드, 타입, 변수들에 접근할 수 있도록 해주는 자바 API
- 인텔리제이 자동완성 기능이나, 스프링 어노테이션이 해당 기능을 사용한 예시로 알고 있다.

## Error와 Exception

- ### Error
  - Error는 실행 중 일어날 수 있는 치명적인 오류
  - 컴파일 시점에 체크할 수 없고 오류가 발생하면 프로그램이 비정상 종료됨
- ### Exception
  - Error보다 경미한 오류이며 try-catch를 이용해 프로그램의 비정상 종료를 막을 수 있음

## 예외 처리 방법

- try, catch, throws, finally 를 활용하여 예외 처리를 진행한다.
- ### try
  - 예외가 발생할 가능성이 있는 범위를 지정
- #### catch
  - 예외 객체가 발생했을 때 finally 구문을 제외한 나머지 구문들을 실행하지 않고 catch 구문을 실행함
- ### throws
  - 예외가 발생한 메소드를 호출 한곳으로 예외 객체를 넘기는 방법
- ### finally
  - 예외 발생 유무나, catch와 관계없이 무조건 수행된다.
  - 종료 구문 작성

## CheckedException, UnCheckedException 차이

- ### CheckedException
  실행하기 전에 예측 가능한 예외, 반드시 예외 처리를 진행해야됨
  - IOException, ClassNotFoundException
- ### UnCheckedException
  런타임 이후에 알 수 있는 예외, 예외처리를 하지 않아도 됨
  - NullPointerException,

## Optional API

Option 클래스를 활용하여 객체의 null과 관련된 상태를 컨트롤 할 수 있음

## JAVA Collection

- 다수의 데이터를 효과적으로 관리할 수 있는 클래스의 집합
- List, Set, Map 인터페이스를 기준으로 여러 구현체가 존재
- Stack과 Queue 인터페이스

## List, Set, Map, Stack, Queue 특징

### List

순서가 있는 데이터 집합, 데이터 중복 허용

- 구현체 : ArrayList, LinkedList

### Set

순서가 없는 데이터의 집합, 데이터 중복 허용 X, Value로 중복 체크

- 구현체 : HashSet, LinkedHashSet(입력된 순서 기억), TreeSet(RB Tree)

### Map

순서가 없는 데이터의 집합, 데이터 중복 허용 X, Key-Value로 중복 체크

- 구현체 : HashMap, LinkedHashMap(입력된 순서 기억), TreeMap(RB Tree)

### Stack

LIFO 방식으로 데이터를 관리하는 집합, 중복 허용 가능

### Queue

FIFO 방식으로 데이터를 관리하는 집합, 중복 허용 가능

## Set과 Map 타입이 Wrapper Class가 아닌 Object를 받을 때 중복 검사는 어떻게 할 건 지 설명

- hashCode() 메소드를 오버라이딩하여 리턴된 해시코드 값이 같은지를 보고 해시 코드 값이 다르다면 다른 객체로 판단
- 해시 코드 값이 같으면 equals() 메소드를 오버라이딩하여 다시 비교, 2개가 같다면 중복 객체로 인식

## Vector와 List의 차이

- 벡터는 데이터 중간 삽입 시 원소를 밀어 내지만 O(n) 리스트는 노드만 연결하기 때문에 O(1) 시간복잡도에서 우위를 가짐
- 벡터는 랜덤 부분 접근이 가능하지만 O(1) 리스트는 불가능 O(n)
- 벡터는 항상 동기화되는 장점이자 단점 멀티쓰레드 환경에서는 동기화가 유지되지만, 싱글 스레드에서는 성능이 떨어짐

## 제네릭에 대해 설명하고 왜 쓰는 지

- 제네릭은 데이터 타입을 하나로 지정하지 않고 사용할 때마다 범용적으로 지정한다는 의미
- 제네릭 타입을 사용하여 잘못된 타입이 사용될 수 있는 문제를 컴파일 과정에서 제거할 수 있음
  ### 장점
  - 타입 안정성 제공
  - 타입 체크와 형변환 생략 가능
  ### 단점
  - static 멤버에 타입 변수 T 사용 불가능
  - 제네릭 타입 배열 선언 불가능

## final / finally / finalize 차이 설명

- final : 클래스, 메소드, 변수, 인자를 선언할 때 사용할 수 있으며, 한 번만 할당하고 싶을 때 사용
- finally : try-catch가 종료될 때 finally 블록이 항상 수행되기 때문에 마무리 해줘야 하는 작업을 처리할 때 사용
- finalize : GC에 의해 호출되는 메소드로 호출하거나 오버라이딩하여 구현하는 것 권장하지 않음

## 직렬화에 대해 설명

- 시스템 내부에서 사용되는 객체 또는 데이터를 외부의 시스템에서도 사용할 수 있도록 byte 형태로 데이터를 변환하는 기술
- 직렬화된 바이트 형태의 데이터를 다시 객체로 변환하는 과정을 역직렬화라고 함
- JVM 메모리에 상주되어 있는 객체 데이터를 바이트 형태로 변환하는 기술

## SerialVersionUID를 선언해야 하는 이유

- JVM은 직렬화와 역직렬화를 하는 시점의 클래스에 대한 버전 번호를 부여하는데, 만약 그 시점에 클래스의 정의가 바뀌어 있다면 새로운 버전 번호를 할당
- 그래서 직렬화 할때의 번호와 역직렬화를 할 때 번호가 다르면 역직렬화가 불가능 할 수 있기 때문에 이런 문제를 해결하기 위해 사용
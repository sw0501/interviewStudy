# 무붕 합주실 예약 시스템 면접 대비

---

## 질문 목록

1. [프로세스와 쓰레드](#1-프로세스와-쓰레드)

### 1. 프로세스와 쓰레드

> 프로세스  
> 실행중인 프로그램을 의미하며 최소 1개의 쓰레드를 가지고 있습니다.

> 쓰레드  
> 프로세스 내에서 Stack 공간만 할당받고 그 이외의 메모리 영역(Head, Code, Data)은 공유하여 작업을 처리하는 단위입니다.

### 2. 멀티 프로세스와 멀티 쓰레드의 특징

> 멀티 프로세스

- 장점
  > 하나의 프로세스가 죽어도 다른 프로세스에 영향을 미치지 않고 계속 실행된다.
- 단점
  > PCB를 모두 교체해야 하기 때문에 컨텍스트 스위칭으로 인한 오버헤드가 크다.

> 멀티 쓰레드

- 장점
  > 스택을 제외한 프로세스 내 자원을 공유하기 때문에 컨텍스트 스위칭 비용이 적다.
- 단점
  > 하나의 쓰레드에 문제가 생길 경우 프로세스 내 모든 쓰레드에 영향을 받으며 동기화 문제도 발생한다.

### 3. 멀티 프로세스와 멀티 프로세서

> 프로세스는 프로그램의 실행 상태를 의미하며 프로세서는 CPU 코어를 말한다.

> 멀티 프로세스는 하나의 프로그램에서 여러 개의 프로세스를 실행하는 것이다.

> 멀티 프로세서는 여러 개의 CPU 코어에 내장된 프로세서가 하나의 시스템에서 동시에 실행되는 것을 의미한다.

### 4. 멀티 쓰레드의 동시성과 병렬성

- 동시성

  > 동시에 여러 작업을 진행하기 위해서 싱글 코어에서 여러 개의 쓰레드가 번갈아가며 작업을 진행하는 것

- 병렬성
  > 여러 작업을 위해 멀티 코어에서 한 개 이상의 쓰레드를 포함하는 각 코어들을 동시에 실행하는 것

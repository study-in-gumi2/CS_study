> # COMPUTER SIENCE_STUDY
- ### Feat. 오주영, 정형빈, 홍종혁

## 🚩 8월 Plan -> 개발자 틀 잡아가기
### 🚩 Study Plan

|날짜|CS STUDY TITLE|
|---|---|
|8/4|자료구조(Data Structure)|
|8/9|네트워크(Network)|
|8/11|운영체제(Operating System)|
|8/16|데이터베이스(Data Base)|
|8/18|디자인패턴(Design Pattern|
|8/23|프레임워크 & 라이브러리 차이(Framework & Library)|
|8/25, 8/30| 기술 스택들 찾아보고 9월 계획 세우기(Planning)|

---

## 3. 운영체제 (Operating System)

	3-1. 프로세스와 스레드의 차이
	3-2. 멀티스레드
	3-3. 스케줄러
	3-4. CPU 스케줄러
	3-5. 동기와 비동기의 차이
	3-6. 프로세스 동기화
	3-7. 메모리 관리 전략
	3-8. 가상 메모리
	3-9. 캐시의 지역성

# 3-3. 스케줄러

프로세스를 스케줄링할때는 각 프로세스를 스케줄링을 위해 마련되어있는 Queue에 넣고 빼가면서 스케줄링을 진행한다.

1. Job Queue : 현재 시스템 내에 있는 모든 프로세스의 집합
2. Ready Queue : 현재 메모리 내에 있으면서 CPU를 잡아서 실행되기를 기다리는 프로세스의 집합
3. Device Queue : Device I/O 작업을 대기하고 있는 프로세스의 집합

여기서 각각의 Queue에 프로세스들을 넣고 빼주는 스케줄러에도 3가지 종류가 존재한다.

### 장기 스케줄러(Long-term scheduler or job scheduler)
메모리는 한정되어 있는데 많은 프로세스들이 한꺼번에 메모리에 올라올 경우, 대용량 메모리(하드디스크, ssd등)에 임시 데이터로 저장된다. 이렇게 저장된 프로세스들의 집합을 pool이라 하고, 이 pool에 저장되어 있는 프로세스 중 어떤 프로세스에 메모리를 할당하고 ready queue에 보낼지 결정하는 역할을 수행한다.

  - 메모리와 디스크 사이의 스케줄링을 담당
  - 프로세스에 memory(각종 리소스)를 할당
  - degree of Multiprogramming 제어(실행중인 프로세스의 수 제어)
  - 프로세스의 상태 --> new >> ready(in memory)

> 메모리에 프로그램이 너무 많이 올라가도, 너무 적게 올라가도 성능이 좋지는 않다. 또한, time sharing system에는 장기 스케줄러가 없다. 바로 메모리에 올려버린다.

### 단기 스케줄러(Short-term scheduler or CPU scheduler)

- CPU와 메모리 사이의 스케줄링을 담당
- Ready Queue에 존재하는 프로세스중, 어떤 프로세스를 running시킬지 결정.
- 프로세스에 CPU를 할당
- 프로세스의 상태
  - ready >> running >> waiting >> ready

### 중기 스케줄러(Medium-term scheduler or Swapper)

- 여유 공간 마련을 위해 프로세스에 통째로 메모리에서 디스크로 쫓아냄(swapping)
- 프로세스에게서 memory를 deallocate
- degree of Multiprogramming 제어
- 현 시스템에서 메모리를 너무 많은 프로그램이 동시에 올라가는 것을 조절하는 스케줄러
- 프로세스의 상태
  - ready >> suspended
    
    

# 3-4. CPU 스케줄러

## 다중 프로그램의 OS

- PC 에서 프로그램을 한개 실행시킨다?
  -> cpu가 한가지 동작에 집중하여 성능을 발휘한다.
  - 그럼 두개 이상의 프로그램을 실행시키면 cpu는 어떻게 동작할까???
    1. PC는 멍청해서 한번에 한가지 일밖에 하지 못한다.
    2. 분신술을 하는 방법
      1. 사람이 가만히 있으면 1명으로 보인다.:
      2. 한걸음 옆으로 움직이면 사람이 움직인것처럼 보인다.
      3. 사람의 눈 깜빡이는 순간에 맞춰서 움직인다.
      4. 엄청난 속도로 움직인다.
      5. 두명으로 보인다.
    3. 이렇게 PC는 사람이 알아채지 못하도록 엄청나게 빠른 속도로 프로그램 하나씩 옮겨가면서 일을 하는것이다.
    
- 이렇듯 process(**컴퓨터에서 연속적으로 실행되고 있는 컴퓨터 프로그램**)를 사람이 체감하지 못할 속도로 옮겨다니면서 우리에게 마치 여러 작업을 동시에 하듯이 보여주는 것이다!!!
- 컴퓨터는 멍청하지만 속도는 아주 아주 빠르다.

## 그렇다면 process들을 어떤 순서로 옮겨 다닐까???

- 이 개념을 **스케줄링** 이라고 한다. 
- 스케줄러는 Ready Queue에 프로세스들을 특정한 우선순위를 기반으로 CPU의 관심을 받을 수 있게 해준다.

> ### 스케줄링의 최대 관심사(Point) 는?
> - 스케줄링의 기준이 되는 대표적인 예
>   - 대기 시간(Waiting Time)
>   - CPU 할당(allocation time)
> - 위 Point에 맞춰서 최대한 CPU 리소스를 활용하고 적은 시간안에 많은 처리를 하기 위한것이 스케줄링의 목적이다.

## 스케줄링의 종류

- 스케줄링의 비선점, 선점 스케줄링
  1. 비선점
    - Time-slice 가 없는 스케줄링
    - CPU가 사용중인 프로세스를 자율적으로 반납하도록 하는 방식
    - 선점방식보다 스케줄러의 호출 빈도가 낮고 문맥 교환의 오버헤드가 적다.
    - 따라서, 일괄처리 시스템에 적합

      >1. FCFS(First Come First Served Scheduling) 스케줄링
      >> 먼저 온놈이 먼저 서비스 받는다.
      >2. SJF(Shortest Job First Scheduling) 스케줄링
      >> CPU제일 짧게 먹는 친구부터 먼저 CPU에 할당
      >3. HRRN(Highest Response Ratio Next Scheduling) 스케줄링
      >> 2번과 1번을 동시에 해결할수 있는 타협점을 찾은 친구
    
  2. 선점
    - 낮은 우선순위를 가진 프로세스보다 높은 우선순위를 가진 프로세스가 CPU를 선점하는 방식
    - 어떤 프로세스가 CPU를 할당받아 실행중에 있어도 다른 프로세스가 실행중인 프로세스를 중지시키고 CPU를 강제 점유할 수 있다.(이 기준은 종류에 따라 다름)

      >1. RR 스케줄링(Round Robin Scheduling)
      >> 프로세스들 사이에 우선순위를 두지 않고 순서대로 시간단위(Time Quantum)로 CPU를 할당하는 알고리즘
      >2. 다단계 큐 스케줄식(Multilevel Queue Scheduling)
      >> Ready Queue를 여러개의 Queue로 쪼개서 각 Queue마다 우선순위를 부여하는 방식

### 더 알고싶은 사람은 링크 참조하세용
[스케줄링 설명](https://ko.m.wikipedia.org/wiki/스케줄링_(컴퓨팅))
[스케줄링 개념을 담은 블로그 추천](https://hyunah030.tistory.com/4)

# 3-5. 동기와 비동기의 차이

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FQTtEk%2Fbtq97xo2K97%2FZn9PYmMco5vrcYjErcHJ30%2Fimg.png">
### 비유
1. 해야할 일 (task)이 빨래, 설거지, 청소가 있다고 하자.
2. 이 일들을 동기(Synchronous)로 처리할 경우 빨래를 먼저하고 설거지하고 청소를 해야한다.
    - 하나의 작업이 진행중이라면 끝날때까지 다른 작업은 받지 않는다!
3. 하지만 비동기(Asyncronous)를 사용할경우 빨래업체, 설거지업체, 청소업체에 모두 맡기고 내할일을 하면된다.
4. 근데 이제 돈(자원, resource)의 문제는 알아서

> 비동기의 경우 코드의 구현이 어렵지만 더 빠른속도로 작업을 처리할 수 있다는 장점이 있다. 즉, 자원을 효율적으로 굴릴수있다. 그렇다면 비동기방식이 항상 옳은 방법인가 ??? NONO
>> - 3way handshake를 기억하는가? 이 과정중에 비동기로 작동해서 다른 서버와 통신을 하게되면? 컴퓨터는 혼란스러워 한다. 즉, 다 사용하는 때가있다. 때는 나중에 몸으로 느끼면서 알아가라.

[동기, 비동기 설명 블로그](https://private.tistory.com/24)
[동기, 비동기 설명2_github](https://github.com/JaeYeopHan/Interview_Question_for_Beginner)

# 3-6. 프로세스 동기화
<img src="https://img.seoul.co.kr//img/upload/2018/02/26/SSI_20180226143151_V.jpg">
### 프로세스 동기화란??
앞에서 말한 멀티쓰레딩에서의 문제점을 다시 살펴보자.

1. 프로세스들이 쭉 있음
2. 그중 한 프로세스 안에는 여러개의 쓰레드(멀티쓰레딩)들이 Heap영역을 공유하면서 서로 데이터를 주고받고 일을 하고있음 (like 협업)
3. 근데 결국 사용하는 파일은 겹치게 되어있다.
4. 그럼 누가 그 파일을 동시에 접근하면 문제가 발생하게 되는데, 이 문제의 영역을 Critical Section(임계영역)이라고 한다.

> 우리반 사람들이 모두 모여 한 git repository안에서 같은 파일을 수정한 뒤에 업로드한다고 생각해보자. 같은 시간대에.

##### 이런 문제들을 해결해주기 위해서 나온 방법이 프로세스 동기화이다.

#### 문제 해결을 위한 기본 조건

1. Mutual Exclusion(상호배제)
    - A가 Critical Section에서 실행중이라면, 다른 프로세스들은 Critical Section 접근 금지
2. Progress(진행)
    - Critical Section에서 실행중인 프로세스가 없고, 별도의 동작이 없는 프로세스들만 Critical Section 진입 후보로서 참여될 수 있다.
3. Bounded Waiting(한정된 대기)
    - A가 Critical Section에 진입신청하고 승인될때까지, 다른 프로세스들이 Critical Section에 진입하는 횟수에는 제한이 있어야 한다.

### 그래서 나온 해결책 Mutax Lock!!!

화장실개념, 볼일다볼때까지 문잠그고 안나온다 마인드

- 아주 근본적인 해결책
- Critical Section에 진입한 프로세스가 Lock을 획득(문을 잠궈버린다.)
- 이후 볼일을 다볼때까지 해당 파일에는 그 무엇도 접근할수가 없다.

### 근데 그건 좀 불편한데? Semaphores!!!(세마포)

아니 문을 잠그는건 너무 좀 아니지않나? 세수만 좀 할게요

- 카운팅 세마포
  - 가용한 개수를 가진 자원에 대한 세마포
  - 자원을 사용하면 세마포 감소, 방출하면 증가
- 이진 세마포
  - mutax라고도 부르며, mutax 0과 1 사이의 값만 가능하며, 사용중인 함수를 잠그는 개념.

> 세마포와 MutaxLock 둘 모두 결국 CriticalSection(임계영역)문제를 해결하기 위해 나온 방법

##### Deadlock(교착상태)
- 세마포가 Ready Queue를 가지고 있고, 둘 이상의 프로세스가 Critical Section 진입을 무한정 기다리고 있는 상황에서 Critical Section안에 프로세스는 진입 대기중인 프로세스가 실행되야만 빠져 나올 수 있는 상황을 지칭


[프로세스 동기화_github](https://github.com/JaeYeopHan/Interview_Question_for_Beginner)

[세마포](https://copycode.tistory.com/62)

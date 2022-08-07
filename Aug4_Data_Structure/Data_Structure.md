> # COMPUTER SIENCE_STUDY
- ### Feat. 오주영, 정형빈, 홍종혁
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
### 1. 자료구조 (Data Structure)

    1-1. Stack(스택)
    1-2. Queue(큐) 
    1-3. Hash(해시데이터)
    1-4. Graph(그래프)
    1-5. Tree(트리구조)
    1-6. Search(탐색)
    1-7. Selection sort(정렬)

---
### 들어가기에 앞서

#### 자료 구조를 배우는 이유는 뭘까?
- 자료 구조의 기본은 원하는 데이터를 최대한 빠르게 찾으면서 최소한의 리소스를 사용하기 위해서 여러가지 저장 구조를 배우는 것이다.

- 데이터를 빠르게 찾기 위해서는 데이터를 저장하는 방법 뿐 아니라 어떤 구조로 데이터를 저장하고 관리해야하는지를 알아야한다. Data Structure는 그러한 구조를 배우는 챕터이다.

#### 자료구조란?
- 여러 데이터들의 효율적으로 사용할 수 있도록 묶음을 저장하고, 사용하는 방법

#### 데이터란?
- 문자, 숫자, 소리, 그림등 모든 요소
- 데이터는 그 자체만으로 정보를 가지기는 힘들다.
  - 예를 들어 나이라는 데이터만으로는 사람의 나이인지 강아지의 나이인지 나무의 나이인지 알기 힘들다.
- 데이터를 분석하고 정리하고 활용해야만 의미를 가질 수 있다.
- 데이터를 사용하는 목적에 맞게 형태를 구분하고 분류해야 한다.
---
# 1-1. Stack(스택)
- 한쪽 끝에서만 자료를 넣고 뺄수 있는 구조
- LIFO(Last In First Out)구조로, 후입선출 구조를 이루는 데이터 구조
- 빨래바구니 또는 상자에 차곡차곡쌓은 물건들을 생각하면 쉽다.
<img src="https://github.com/study-in-gumi2/CS_study/blob/main/images/Data_Structure_images/stack1.png">

- Stack의 예시 : 인터넷 뒤로가기, 재귀함수, ctrl+z

## top
스택에서 현재 target인 스택의 위치를 가리키는 top은 마지막으로 들어온 데이터를 기억하며 인덱스로 가리킬 수 있도록 한다.
<img src="https://github.com/study-in-gumi2/CS_study/blob/main/images/Data_Structure_images/stack2.png">


---
# 1-2. Queue(큐)
- 삽입, 삭제의 위치가 제한적인 자료구조
  - Queue의 뒤(Enqueue) : 데이터 삽입 / Queue의 앞(Dequeue) : 데이터 추출
- FIFO(First In First Out)구조로, 선입선출 구조를 이루는 데이터 구조
- Queue의 예시 : 서비스 대기 행렬(은행 번호표)
<img src="https://github.com/study-in-gumi2/CS_study/blob/main/images/Data_Structure_images/queue1.png">

## Queue의 종류
### 선형 큐
  - 선형큐의 문제점
<img src="https://github.com/study-in-gumi2/CS_study/blob/main/images/Data_Structure_images/queue2.png">

  - 해결방법
	1. 매 연산이 이루어질 때마다 저장된 원소들을 배열의 앞부분으로 이동시킨다 -> 많은 리소스 사용!!!!
	2. 환형 큐(원형 큐) 써
### 환형 큐(원형 큐)
<img src="https://github.com/study-in-gumi2/CS_study/blob/main/images/Data_Structure_images/queue3.png">
  - 1차원 배열을 사용하되, 논리적으로 배열의 처음과 끝이 연결되어 있는 원형의 Queue가 있다고 가정
  - 선형 큐에서는 데이터를 가리키는 인덱스가 하나였지만, 환형 font, rear 두개의 인덱스 변수가 존재한다.
    - front는 첫 번째 데이터를 가리키는 변수
    - rear는 마지막 데이터를 가리키는 변수
    - front 와 rear 가 가르키는 변수가 같다면 원형큐는 비어있다고 볼 수 있다

  
### 우선순위 큐
일단 PASS

---
# 1-3. Hash(해시)

- 다양한 길이를 가진 데이터를 고정된 길이를 가진 데이터로 mapping한 값
- 마치 파이썬의 Dictionary 와 같이 key 와 value 가 1:1 mapping 되어 있는 데이터 구조
- 기존의 자료 구조들은 탐색이나 삽입에 선형적인 시간이 걸리는 반면, 해시구조는 즉시 저장하거나 찾고자 하는 위치를 참조할 수 있으므로 빠른 속도로 처리할 수 있다.

## hash의 특성

### 무결성

- hash는 특정한 데이터를 이를 상징하는 더 짧은 길이의 데이터로 변환하는 행위를 의미한다(key-value)
- 여기서 value값은 원래의 데이터가 조금만 달라져도 확연하게 달라지기 때문에 무결성을 지키는데 많은 도움을 준다.
  - 예를들어 'A' 라는 문자열의 해시와 'B'라는 문자열의 해시는 한글자 차이지만 결과값은 완전히 다른 문자열이 나온다.

### 보안성

- 해시는 기본적으로 복호화가 불가능
- 동일한 출력값을 만들 수 있는 입력값의 가짓수는 수학적으로 무한개이기 때문
- 즉, 해커가 중간에 해시 데이터를 가져가도 쉽게 복호화를 할 수 없다는 점에서 강한 보안성을 가진다.

## 해시 함수(Hash function)
- 해시 함수는 임의의 길이를 갖는 임의의 데이터에 대해 고정된 길이의 데이터로 매핑하는 함수를 말함
- 해시 함수를 적용하여 나온 고정된 길이의 값을 해시값이라 한다.

## 해시 테이블(Hash Table)
- Key 와 Value 값을 매핑해 둔 데이터 구조
- 해시 함수를 이용하여 검색하고자 하는 값을 변환하면 그 값이 저장된 위치를 즉시알아낼 수 있다.
- 데이터의 양이 아무리 많아지더라도 원리적으로는 검색에 걸리는 시간은 항상 동일하다.

> 하지만, 해시 테이블의 기본 개념은 데이터를 담을 테이블을 미리 크게 확보해 놓은 후 입력받은 데이터를 해시하여 테이블 내의 주소를 계산하고 따라서, 데이터가 입력되지 않은 여유공간이 많아야 제 성능을 발휘할 수 있다.

# 1-4. Graph(그래프)

<img src="https://velog.velcdn.com/images/nnnyeong/post/edb986b2-bca7-40a2-ab99-f07c2a1e3efa/image.png">
- 그래프란 정점과 간선으로 이루어진 자료구조
- 알고리즘에서 특히, 굉장히 많이 사용된다.
- 주로 2차원의 지도 또는 미로찾기 문제, 다익스트라(몰라도됨 일단) 알고리즘 등에 많이 사용되는 구조

## 그래프의 탐색 방법(DFS, BFS)

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcoHi34%2FbtqSjAPXa41%2FDwji6MLkkGCfd09dsTxnzk%2Fimg.png">

- 위 그림과 같은 사진이 있을때, 1에서 3까지 갈수 있다는 판단을 내리기 위해서는 어떻게 해야할까?
- 컴퓨터는 사람과 같은 판단을 할 수 없기 때문에 제한된 시간안에 정확하고 빠른 판단을 하기 위해서는 알고리즘을 통해 방법을 알려주어야 한다. 
  - 예를 들어, 랜덤한 방향으로 이어진 정점으로 이동하는 프로그램을 짠다면 프로그램이 돌다가 어쩌다 1에서 3까지 도달하게 됨으로, 이어져있다고 판단을 내릴 수는 있겠으나 이러한 방법으로는 제한된 시간안에 제대로된 답변을 내놓을 수 없다.
- 여기서 착안된 그래프를 효율적으로 탐색할수 있는 알고리즘 두개가 DFS(Deeps-First-Search), BFS(Breadth-First-Search)이다.

<img src="https://blog.kakaocdn.net/dn/cFgEJ6/btqKmoJkq5a/pwm3O8T4rERuL4wSTrkgnK/img.gif">

# 1-5. Tree(트리구조)
- Tree구조는 그래프의 일종으로, 한 노드에서 시작해서 다른 정점들을 순회하며 자기 자신에게 들어오는 순환이 없는 연결 그래프

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f7/Binary_tree.svg/400px-Binary_tree.svg.png">



# 1-6. Search(탐색)
# 1-7. Selection sort(정렬)

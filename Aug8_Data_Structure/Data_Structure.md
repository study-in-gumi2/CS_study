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
	1-4. Tree(트리구조)
	1-5. Graph(그래프)
	1-6. Selection sort(정렬)
	1-7. Search(탐색)
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
<img src="https://github.com/study-in-gumi2/CS_study/blob/main/images/stack1.png?raw=true">
## top
스택에서 현재 target인 스택의 위치를 가리키는 top은 마지막으로 들어온 데이터를 기억하며 인덱스로 가리킬 수 있도록 한다.
<img src="https://github.com/study-in-gumi2/CS_study/blob/main/images/stack2.png?raw=true">
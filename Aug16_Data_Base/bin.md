# Statement vs PreparedStatement

## statement?
명령형 프로그래밍 언어의 가장 작은 독립 요소.
DB에 SQL을 보내기 위한 준비작업과 실제 SQL을 실행하여 결과값을 제공
  1) 쿼리 문장 분석
  2) 컴파일
  3) 실행

  - 장점
    - 테이블, 컬럼에 대한 동적 쿼리 작성이 가능하다. 즉 DDL 작성에 적합하다.
    - 쿼리실행문을 직접 확인 가능하므로 쿼리 분석이 쉽다.
    
   - 단점
    - 1번 처리구간을 매 요청마다 수행하므로 쿼리 처리비용이 더 들게 된다
    - 위와 반대로 SQL injection으로 인한 공격에 노출된다.
      where 변수 부분에 or 문을 추가할 경우 항상 참이 되어버리므로 악용가능

## preparedStatement?
'준비된 문장'
  처음에만 3단계를 거치고 그후는 캐시에 담아 재사용

  - 장점
    - 1번 처리구간을 건너뛰고 2번부터 처리하기 때문에 SQL 처리가 빠르다
    - 1번 구간은 SQL을 분석하는 처리도 하고 있지만, 건너뛰기 때문에 SQL injection을 예방할 수 있다.
    
   - 단점
    - 쿼리에 오류가 생긴 경우 분석하기 어렵다. 
    - 허용된 위치에서만 사용할 수 있기 떄문에 동적 쿼리 작성이 어렵다.
      변수를 활용해 동적으로 테이블을 변경하는 쿼리를 작성해야 하는 경우 처리가 불가능하다.

## 결론
  가장 큰 차이는 캐시(cache) 사용여부이다.
  Statement는 SQL문을 실핼 할때마다 SQL을 매번 구문에 새로 작성하고 해석해야한다
  PreparedStatement는 SQL문을 미리 준비해 놓고 변수를 활용하여 반복되는 SQL문을 쉽게 처리

  Statement 는 DDL(CREATE, ALTER, DROP) 구문을 처리할 떄 적합하다.
  매 실행시 쿼리를 다시 파싱하기 떄문에 속도가 느리며, SQL injection 공격에 취약하다
  
  Prepared Statement DML(SELECT, INSERT, UPDATE, DELETE) 구문 처리에 적합하다.
  캐시에 저장된 쿼리를 활용하기 떄문에 실행이 빠르며, SQL injection을 막기 위한 방법으로 활용된다.
  
  
  # NoSQL
  
  ## NoSQL?
  NoSQL데이터 베이스는 특정 데이터 모델에 대해 특정 목적에 맞추거 구축되는 데이터베이스로서 현대적인 애플리케이션 구축을 위한 유연한 스키마
  https://www.youtube.com/watch?v=Q_9cFgzZr8Q
  
  

# 과거 JDBC가 없기 전의 문제
이건 옛날방식)
주로 TCP IP 를 사용해서 tb 와 서버를 연결한다./
sql을 db에 전달해서 db가 수행해서 결과 응답한다.

# 문제점
- 다른 방식의 db로 변경하면 서버 코드를 다 변경해야 한다. 
	- 각기 다른 커넥션 방법, SQL 응답받는 방법 새로 학습 해야함.
# 그래서 JDBC가 등장했다.

JDBC 표준 인터페이스 (java database connectivity) 가 등장했다! 
jdbc 인터페이스를 각각의 db회사에서 구현해서 라이브러리로 구현한다.
이거를 jdbc driver 라고 한다.

## 우리는 jdbc 인터페이스 만 맞춰서 해주면된다.
- 만약 db를 바꿔야 하면 Driver(라이브러리)만 바꾸면 해결됩니다. 

# 최신 데이터 접근 기술

1. jdbc 직접 사용


2. [[SQL Mapper]]
	sql을 직접 

3. [[ORM]] 


# Connection 

[[jdbc connection]]

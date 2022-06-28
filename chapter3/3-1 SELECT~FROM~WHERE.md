

market_db.sql 파일 내용 살펴보기
1. SQL
2. MySQL Workbench

* 데이터베이스 만들기
1. CRERATE DATABASE market_db;
2. Create Schema

* 테이블 만들기
1. USE market_db 
2. SCHEMAS 패널에서 market_db 더블 클릭

* 데이터 입력하기
1. INSERT INTO member VALUES('TWC', '트와이스', 9, '서울', '02', '11111111', 167, '2015.10.19') 
2. Tables -> Select Rows - Limit 1000 -> 데이터 입력

* 데이터 조회
1. SELECT * FROM member;

# SELECT 열이름 FROM 테이블이름 WHERE 조건식

## USE문: SELECT문을 실행하기 전에 먼저 사용할 데이터베이스를 지정해야
* USE 데이터베이스_이름;

## SELECT ~ FROM ~ WHERE: 테이블에서 데이터 가져오기 위한 예약어
* SELECT 열_이름 FROM 데이터베이스_이름.테이블_이름 WHERE 조건식;<br>
cf) 열 이름에 별칭을 입력하고 싶으면 뛰어쓰고 별칭 입력(별칭에 공백이 있으면 큰따옴표(")로 묶어주기<br>
cf) 조건식: >,<,>=,<=,= / AND,OR / BETWEEN AND / IN() / LIKE / _

 



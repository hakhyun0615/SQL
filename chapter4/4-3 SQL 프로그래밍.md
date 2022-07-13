# 스토어드 프로시저
* MySQL에서 프로그래밍 기능이 필요할 때 사용하는 데이터베이스 개체
* SQL 프로그래밍은 스토어드 프로시저 안에 만들어야 한다
* DELIMITER $$<br>
CREATE PROCEDURE 이름()<br>
BEGIN<br>
여기에 SQL 프로그래밍<br>
END $$<br>
DELIMITER;<br>
CALL 이름();

# IF문
IF 조건<br>
SQL문장1<br>
ELSE<br>
SQL문장2<br>

# CASE문
SELECT CASE<br>
WHEN 조건1 THEN 값1<br>
WHEN 조건2 THEN 값2<br> 
WHEN 조건3 THEN 값3<br>
ELSE 값4<br> 
END<br>
FROM 테이블이름;<br> 
<img width="1304" alt="image" src="https://user-images.githubusercontent.com/88610333/177915839-6cace31e-3afb-4f22-857b-e8c58695e0f3.png">
<img width="1409" alt="스크린샷 2022-07-11 오전 9 47 17" src="https://user-images.githubusercontent.com/88610333/178169446-898a9e12-d3d3-40ae-acce-775118a1ddf5.png">


# WHILE문
* WHILE <조건식> DO SQL문장들 END WHILE;

## ITERATE
* continue와 동일

## LEAVE
* break와 동일

# 동적 SQL
* 미리 SQL을 준비한 후 나중에 실행하는 것

## PREPARE
ex) PREPARE myQuery FROM 'INSERT INTO gate_table VALUES(NULL,?)';

## EXECUTE
ex) EXECUTE myQuery USING @curDate;

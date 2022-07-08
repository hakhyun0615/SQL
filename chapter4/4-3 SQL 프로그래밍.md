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
* IF <조건문> THEN SQL문장들 END IF;

# CASE문
* CASE 열 WHEN 조건1 THEN SQL문장들1 WHEN 조건2 THEN SQL문장들2 WHEN 조건3 THEN SQL문장들3 ELSE SQL문장들4 END CASE; 

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

## INSERT(테이블 행 데이터 입력)
* INSERT INTO 테이블_이름 VALUES (값1, 값2, ..);
* 모든 열이 아닌 부분만 입력하고 싶으면 테이블 뒤에 (열1, 열2, ..) 써야, 생략된 열에는 NULL이 들어감
* INSERT INTO 입력할_테이블_이름 SELECT 열_이름 FROM 테이블_이름; : 다른 테이블의 데이터를 한 번에 입력

## AUTO_INCREMENT PRIMARY KEY
* ALTER TABLE 테이블_이름 AUTO_INCREMENT=숫자; : 숫자부터 시작
* SET @@auto_increment_increment=숫자; : 증가값은 숫자로 지정
* INSERT시 자동 증가하는 열은 NULL값으로 채워 넣으면 된다
* SELECT LAST_INSERT_ID(): 어느 숫자까지 증가되었는지 확인

cf) SELECT COUNT(별) FROM 테이블 이름: 테이블 개수 조회<br>
cf) DESC 테이블_이름: 테이블 구조 확인

## UPDATE(행 데이터 수정)
* UPDATE 테이블_이름 SET 열1=값1, 열2=값2, ... WHERE 조건;
* WHERE을 생략하면 테이블의 모든 행의 값이 변경

## DELETE(행 데이터 삭제)
* DELETE FROM 테이블_이름 WHERE 조건; : WHERE 없으면 전체 삭제

cf) DROP(테이블 자체를 삭제), TRUNCATE(DELETE와 동일학게 빈 테이블 남김)은 속도가 DELETE보다 빠름 but, WHERE(조건문)을 쓸 수가 없어 조건 없이 전체 행 삭제시 사용

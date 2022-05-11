# SELECT 열_이름 FROM 테이블_이름 WHERE 조건식 GROUP BY 열_이름 HAVING 조건식 ORDER BY 열_이름 LIMIT 숫자

## ORDER BY: 결과 출력 순서 조절
* SELECT 열_이름 FROM 테이블_이름 WHERE 조건문 ORDER BY 열_이름 ASC/DESC;

## LIMIT: 출력 개수 제한
* SELECT 열_이름 FROM 테이블_이름 WHERE 조건문 ORDER BY 열_이름 ASC/DESC LIMIT 시작, 개수;

## DISTINCT: 중복된 결과에서 중복된 데이터를 1개만 남김
* SELECT DISTINCT 열_이름 FROM 테이블_이름

## GROUP BY: 그룹으로 묶어주는 역할
* GROUP BY와 함께 사용되는 집계 함수: SUM(), AVG(), MIN(), MAX(), COUNT(), COUNT(DISTINCT)
* SELECT 열_이름, SUM(열_이름) FROM 테이블_이름 GROUP BY 열_이름
cf) 별칭 이용시 한 칸 뛰고 큰 따옴표 이용

## HAVING: WHERE과 비슷한 개념으로 집계 함수에 대해서 조건을 제한 따라서 꼭 GROUP BY 다음에 나와야 됨

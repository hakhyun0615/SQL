# 특정 문자가 포함되어 있는 데이터를 검색

## 특정 문자로 시작하는 데이터 검색
* SELECT [필드명] FROM [테이블명] WHERE [필드명] LIKE '특정 문자열%';

## 특정 문자로 끝나는 데이터 검색
* SELECT [필드명] FROM [테이블명] WHERE [필드명] LIKE '%특정 문자열'

## 특정 문자를 포함하는 데이터 검색
* SELECT [필드명] FROM [테이블명] WHERE [필드명] LIKE '%특정 문자열%';

## 복수개의 특정 문자를 포함하는 데이터 검색 
* SELECT [필드명] FROM [테이블명] WHERE [필드명] LIKE '%특정 문자열%' OR [필드명] LIKE '%특정 문자열2%';
* SELECT [필드명] FROM [테이블명] WHERE [필드명] REGEXP '특정 문자열|특정 문자열2'; (특정 문자열을 '|' 를 기준으로 나눈다)
* ex) SELECT DISTINCT CITY FROM STATION WHERE CITY NOT REGEXP '^[aeiou]' AND CITY NOT REGEXP '[aeiou]$'

# 정규표현식 
* https://codingspooning.tistory.com/entry/MySQL-%EC%A0%95%EA%B7%9C%ED%91%9C%ED%98%84%EC%8B%9D-%EA%B2%80%EC%83%89%ED%95%98%EA%B8%B0-REGEXP-LIKE

# 문자열의 부분 가져오기

## LEFT
* 문자에 왼쪽을 기준으로 일정 갯수를 가져오는 함수
* LEFT(문자, 가져올 갯수);

## MID
* 문자에 지정한 시작 위치를 기준으로 일정 갯수를 가져오는 함수
* MID(문자, 시작 위치, 가져올 갯수);
* SUBSTR(문자, 시작 위치, 가져올 갯수);
* SUBSTRING(문자, 시작 위치, 가져올 갯수);

## RIGHT
* 문자에 오른쪽을 기준으로 일정 갯수를 가져오는 함수
* RIGHT(문자, 가져올 갯수);

# ORDER BY 다중정렬
* ORDER BY 열1 DESC, 열2 DESC;
* 열1을 기준으로 정렬 후, 열1에서 같은 값에 한해서 열2로 정렬

# 숫자 대체 예제
* SELECT CEIL(AVG(Salary)-AVG(REPLACE(Salary,'0',''))) FROM EMPLOYEES;

# GROUP BY 1
* 첫 번째 열을 기준으로 그룹화

# 상위 몇 퍼센트, 하위 몇 퍼센트 구하기
* PERCENT_RANK() OVER (ORDER BY 열)
<img width="1593" alt="image" src="https://user-images.githubusercontent.com/88610333/177905207-2181ea5c-592f-4b58-8dd6-667dc5c83773.png">

# Any/All
* Any: 하위 쿼리에서 하나의 조건 만 만족하면 True
* All: 하위 쿼리에서 모든 값이 조건 만족하면 True

# 서브쿼리(쿼리문 안에 또 다른 쿼리문 포함)
<img width="686" alt="image" src="https://user-images.githubusercontent.com/88610333/178189255-2bff195b-e827-4c76-b5c1-b1a6084dea48.png">

# WHERE -> GROUP BY / GROUP BY -> HAVING(문제 읽고 순서 파악)
<img width="686" alt="image" src="https://user-images.githubusercontent.com/88610333/178197533-7332062a-0299-40eb-865f-352639961078.png">
<img width="684" alt="image" src="https://user-images.githubusercontent.com/88610333/178197559-53c9fef9-f4ed-4834-96f6-2a56a7e78b88.png">

# COALESCE
<img width="562" alt="image" src="https://user-images.githubusercontent.com/88610333/178639527-c0f6bf18-3f5c-4dd4-afa2-d266a465e84c.png">
<img width="679" alt="image" src="https://user-images.githubusercontent.com/88610333/178648888-229cb693-b371-4863-ba3b-9d2165119aaa.png">




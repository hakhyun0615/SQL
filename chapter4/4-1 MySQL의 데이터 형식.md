# 데이터 형식

## 정수형
* TINYINT(-128~127)
* TINYINT UNSIGNED(0~255)
* SMALLINT(-32768~32767)
* SMALLINT UNSIGNEDE(0~65535)
* INT(-21억~21억)
* BIGINT(-900경~900경)

## 문자형
* CHAR(속도 빠름)(최대 255자)
* VARCHAR(공간 효율)(최대 16383자)
* TEXT(대용량 텍스트)(최대 65535자)
* LONGTEXT(최대 42억자)
* BLOB/LONGBLOB(사진이나 동영상 저장)<br>
cf) 데이터가 숫자 형식이라도 연산이나 크기에 의미가 없다면 문자형으로 지정하는게 좋다.

## 실수형
* FLOAT(소수점 아래 7자리까지)
* DOUBLE(소수점 아래 15자리까지)

## 날짜형
* DATE(YYYY-MM-DD)(날짜만 저장)
* TIME(HH:MM:SS)(시간만 저장)
* DATETIME(YYYY-MM-DD HH:MM:SS)(날짜 및 시간 저장)

# 변수의 사용

* SET @변수이름 = 변수의 값;
* SELECT @변수이름;

## PREPARE, EXECUTE
ex) SET @count = 3;<br>
PREPARE mySQL FROM 'SELECT mem_name, height, FROM memver ORDER BY height LIMIT ?';<br>
EXECUTE mySQL USING @count

# 데이터 형 변환

## 함수를 이용한 명시적인 변환
* CAST(값 AS 데이터_형식 [(길이)])
* CONVERT(값, 데이터_형식 [(길이)])<br>
cf) 여기서 데이터 형식은 CHAR, SIGNED(부호 있는 정수), UNSIGNED(부호 없는 정수), DATE, TIME, DATETIME...

## 자연스러운 암시적인 변환


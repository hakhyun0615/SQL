# 연동 프로그래밍 기본
* 파이썬과 MySQL 데이터베이스를 연동하면 MySQL 워크벤치 없이도 MySQL에 접근 가능

## 연동 프로그램을 위한 쇼핑몰 생성
* MySQL 워크벤치를 실행해서 'soloDB'를 생성
DROP DATABASSE IF EXISTS soloDB;<br>
CREATE DATABASE soloDB;<br>

## 파이썬에서 데이터 입력
* MySQL 연결하기 > 커서 생성하기 > 테이블 만들기 > 데이터 입력하기 > 입력한 데이터 저장하기 > MySQL 연결 종료하기

### MySQL  연결하기
pymysql.connect(host=서버IP주소, user=사용자, password=암호, db=데이터베이스, charset=문자세트)<br>

### 커서(데이터베이스에 SQL문을 실행하거나 실행된 결과를 돌려받는 통로) 생성하기
cur = conn.cursor()<br>

### 테이블 만들기(테이블을 만드는 SQL문을 함수의 매개변수로 넘겨주면 SQL문이 데이터베이스에 실행)
cur.execute("CREATE TABLE userTable(id char(4), userName char(15), email char(20), birthYear int)")<br>

### 데이터 입력하기
cur.execute("INSERT INTO userTable VALUES('hong', '홍지윤', 'hong@naver.com', 1996)")<br>

### 입력한 데이터 저장하기
conn.commit()<br>

### MySQL 연결 종료하기
conn.close()<br>

# 연동 프로그래밍 활용

## 완전한 데이터 입력 프로그램의 완성
* 사용자가 반복해서 데이터를 입력하는 코드를 작성(더 이상 입력할 데이터가 없으면 ENTER키를 입력하여 종료)
import pymysql<br>
<br>
conn, cur = None, None<br>
data1, data2, data3, data4 = "", "", "", ""<br>
sql = ""<br>
<br>
conn = pymysql.connect(host='127.0.0.1', user='root', password='0000', db='soloDB', charset='utf-8')<br>
cur = conn.cursor()<br>
<br>
while(True):<br>
  data1 = input('사용자 ID ==> ")<br>
  if data1 == "":<br>
    break;<br>
  data2 = input("사용자 이름 ==> ")<br>
  data3 = input("사용자 이메일 ==> ")<br>
  data4 = input("사용자 출생연도 ==> ")<br>
  sql = "INSERT INTO userTable Values('" + data1 + "', '" + data2 + "' + data3 + "'," + data4 + ")"<br>
  cur.execute(sql)<br>
<br>
conn.commit()<br>
conn.close()<br>

## MySQL의 데이터 조회를 위한 파이썬 코딩 순서
* MySQL 연결하기 > 커서 생성하기 > 데이터 조회하기 > 조회한 데이터 출력하기 > MySQL 연결 종료하기

## 완전한 데이터 조회 프로그램의 완성
import pymysql<br>
<br>
conn, cur = None, None<br>
data1, data2, data3, data4 = "", "", "", ""<br>
row = None<br>
<br>
conn = pymysql.connect(host='127.0.0.1', user='root', password='0000', db='soloDB', charset='utf-8')<br>
cur = conn.cursor()<br>
<br>
cur.execute("SELECT * FROM userTable")<br>
<br>
print("사용자ID 사용자이름 이메일 출생연도")<br>
print("---------------------------")<br>
<br>
while(True):<br>
  row = cur.fetchone()<br>
  if row == None:<br>
    break<br>
  data1 = row[0]<br>
  data2 = row[1]<br>
  data3 = row[2]<br>
  data4 = row[3]<br>
  print("%5s %15s %20s %d" %(data1,data2,data3,data4))<br>
<br>
conn.close()<br>
  



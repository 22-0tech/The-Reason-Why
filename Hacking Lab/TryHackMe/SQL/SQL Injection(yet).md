![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.1.png)<br>
OWASP Top 10 A03 identifies SQL Injection as a critical vulnerability.<br>
OWASP10의 A03으로 핵심 취약점 SQL Injection입니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* In-Band<br>
<br>
Error-Based SQLi // Union-Based SQLi 두 개로 나뉩니다.<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.2.png)<br>

It is an error-based SQL injection displayed on the initial screen when the machine starts.<br>
머신을 시작하면 나오는 초기 화면으로 Error-Based SQLi입니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.3.png)<br>

The parameter is changed and 2 is entered. The data exists.<br>
파라미터를 바꿔가며 이번에는 2를 넣어보겠습니다. 데이터가 존재합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.4.png)<br>

This time, when 3 is entered, the data does not exist.<br>
이번엔 3을 넣었더니 데이터가 존재하지 않습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.5.png)<br>

The ORDER BY clause is used to determine the number of columns. Since the data exists when the value is 3, there are at least three columns.<br>
order by를 이용해 column의 개수를 파악하겠습니다. 3일 때 데이터가 존재하므로 최소 3개 이상입니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.6.png)<br>

When 4 is entered, it cannot be found, indicating that there are up to three columns.<br>
4를 넣었더니 찾을 수 없다고 합니다. column은 3개까지 존재함을 알 수 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.7.png)<br>

The ORDER BY clause is used to analyze id=2 as well.<br>
id=2도 order by를 이용해서 파악하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.8.png)<br>

For id=2, there are also up to three columns.<br>
id=2 또한 column은 3개까지 존재합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.9-0.png)<br>
<br>
Since there are three columns, the table is queried with three parameters.<br>
However, because the original data with id=1 exists, the attacker’s input is obscured.<br>

column이 3개이므로 인자를 3개로 맞춰서 테이블을 조회하겠습니다. 
하지만, 원래 데이터 id=1이 존재하기 때문에 공격자의 입력값이 묻혀진 상태입니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.9.png)<br>
<br>
As confirmed above,<br>
the ID is set to a non-existent value such as 0, similar to the non-existent id 3, and the query is constructed with three parameters.<br>
After that, 3 appears on the page, indicating that the third position may be the channel through which data is transmitted.<br>

위에서 확인했듯이 존재하지 않는 id 3처럼 존재하지 않는 0으로 설정하고 인자 3개로 설정하겠습니다.<br>
그 후 페이지에 3이 나왔습니다. 3번 자리가 데이터가 전송되는 통로임을 의심할 수 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.10.png)<br>
<br>
When 10 is entered instead of 3, 10 is displayed. This confirms that it is a data transmission channel.<br>
3대신 10을 넣었더니 10이 출력이 됐습니다. 데이터가 전송되는 통로로 검증되었습니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.11.png)<br>
<br>
To retrieve the table names, table_name is placed in the data transmission channel.<br>
The table name returned is CHARACTER_SETS, which is a system table, so a user-defined table needs to be identified.<br>

테이블 이름을 조회하기 위해 데이터 전송로에 table_name을 배치시킵니다.<br>
조회된 테이블 이름은 CHARACTERS_SETS로 기본 테이블이므로, 사용자 정의 테이블을 찾아야합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.12.png)<br>

Using where table_schema = database(), only the table names required for the current website will be checked.<br>
where table_schema=database()를 이용해 현재 이 웹사이트에서 필요한 테이블 이름만 확인하겠습니다. 

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.13.png)<br>

In addition to article, a table named staff_users was found.<br>
article 외에 staff_users 이름의 테이블을 찾았습니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.14.png)<br>

Based on the identified tables, the names of all columns will be determined.The column names are id, username, and password.<br>
찾은 테이블을 기반으로 모든 column의 이름을 파악하겠습니다. column의 이름은 각각 id,username,password입니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* Blind-Based SQLi<br>
<br>
Boolean // Time-Based 두 개로 나뉩니다.<br>
추가로 인증 우회(Authentication Bypass)방법이 있습니다.<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.15-0.png)<br>

Based on the identified columns, Martin’s password was obtained in username:password format.<br>
찾은 column을 기반으로 username:password 형식으로 martin의 비밀번호를 찾았습니다.
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.15.png)<br>


<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.15-2.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.16.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.18.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.19.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.20.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.21.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.22.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.23.png)<br>

<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.24.png)<br>

<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.25.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.26.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.27.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.28.png)

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.29.png)

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.30.png)

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.31.png)

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.32.png)

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.34.png)

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.35.png)

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.36.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.37.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.38.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.39.png)<br>










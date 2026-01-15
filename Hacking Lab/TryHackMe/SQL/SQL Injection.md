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
As confirmed above,<br>
the ID is set to a non-existent value such as 0, similar to the non-existent id 3, and the query is constructed with three parameters.<br>

위에서 확인했듯이 존재하지 않는 id 3처럼 존재하지 않는 0으로 설정하고 인자 3개로 설정하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.10.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.11.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.12.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.13.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.14.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.15-0.png)<br>

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










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
Error-Based SQLi // Union-Based SQLi 두 가지 방법으로 나뉩니다.<br>
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
<br>
<br>
The ORDER BY clause is used to determine the number of columns. Since the data exists when the value is 3, there are at least three columns.<br>
order by를 이용해 column의 개수를 파악하겠습니다. 3일 때 데이터가 존재하므로 최소 3개 이상입니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.6.png)<br>
<br>
When 4 is entered, it cannot be found, indicating that there are up to three columns.<br>
4를 넣었더니 찾을 수 없다고 합니다. column은 3개까지 존재함을 알 수 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.7.png)<br>
<br>
The ORDER BY clause is used to analyze id=2 as well.<br>
id=2도 order by를 이용해서 파악하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.8.png)<br>
<br>
For id=2, there are also up to three columns.<br>
id=2 또한 column은 3개까지 존재합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.9-0.png)<br>
<br>
<br>
Since there are three columns, the table is queried with three parameters.<br>
However, because the original data with id=1 exists, the attacker’s input is obscured.<br>

column이 3개이므로 인자를 3개로 맞춰서 테이블을 조회하겠습니다.<br>
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
A table named staff_users was found in addition to article.<br>

where table_schema=database()를 이용해 현재 이 웹사이트에서 필요한 테이블 이름만 확인하겠습니다.<br>
article 외에 staff_users 이름의 테이블을 찾았습니다.<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.13.png)<br>
<br>
<br>
Based on the identified table, all column names will be examined. The column names are id, username, and password.<br>
찾은 테이블을 기반으로 모든 column의 이름을 파악하겠습니다. column의 이름은 각각 id,username,password입니다.<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.14.png)<br>

Based on the identified columns, Martin’s password was obtained in username:password format.<br>
찾은 column을 기반으로 username:password 형식으로 martin의 비밀번호를 찾았습니다.
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
Boolean // Time-Based 두 가지 방법으로 나뉩니다.<br>
추가로 인증 우회(Authentication Bypass)방법이 있습니다.<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.15-0.png)<br>
<br>

First, the method of authentication bypass is described.<br>
먼저 인증우회(Authentication Bypass)방법입니다.
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.15.png)<br>
<br>
By setting the ID to admin'# and using a random number for the password,<br>
login was successfully achieved by using the hash symbol (#) to ignore the remaining part of the query.<br>

ID에 admin'# 비밀번호는 랜덤숫자로 해시사인#을 이용해 뒤에 오는 문자열을 무시하는 방법으로 로그인에 성공했습니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.15-2.png)<br>

This time, authentication bypass was successfully achieved by appending OR '2=2#' to the password.<br>
*WHY – 2=2 is always true.<br>

이번엔, 비밀번호에 OR'2=2#'를 붙여 인증 우회 방법에 성공했습니다.<br>
*WHY- 2=2는 반드시 (True)참이기 때문입니다. 
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* Boolean-Based SQLi<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.16.png)<br>

Depending on the user input, a true or false result is returned. This method infers information based on those responses.<br>
On the initial screen, admin was provided as a hint for the ID.<br>

사용자 입력값에 따라 참(True) 또는 거짓(False)를 내놓습니다. 이를 이용해 추론하는 방법입니다.<br>
초기 화면으로 ID는 admin을 힌트로 주었습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.18.png)<br>
<br>
Because there was no URL-encoded value, the result was false.<br>
URL 인코딩값이 없어 False로 나왔습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.19.png)<br>
<br>

Because a true result was returned without any syntax errors, the attack can be executed successfully.<br>
문법적 오류없이 True가 나왔기 때문에, 정상적으로 공격을 실행할 수 있습니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.21.png)<br>

The length function is used to check the length of the password.<br>
When tested with a length of 3 characters, the result was false, confirming that the password is not 3.<br>

length는 비밀번호 길이를 확인하는 것으로 3글자일 때 False로 3글자가 아님을 확인했습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.22.png)<br>
<br>

When 4 was tested, the result was true, indicating that the password is 4 characters long.<br>
4를 넣었더니 True로 비밀번호는 4글자입니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.23.png)<br>
<br>
<br>
The process of finding the characters will use ASCII character codes.<br>
Since values greater than 90 return false, it can be determined that the characters are not lowercase letters.<br>

글자를 찾는 과정은 ascii 아스키 문자 코드를 이용해 찾겠습니다. 90 초과는 False이므로 소문자가 아님을 알 수 있습니다.
<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.24.png)<br>
<br>

When tested with values of 50 or higher, the result was true, narrowing down the range.<br>
50 이상일 때는 True로 범위가 좁혀졌습니다. 
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.25.png)<br>

The password must be discovered by repeating this process multiple times.<br>
이러한 과정을 여러번 거쳐서 비밀번호를 찾아야합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.26.png)<br>
<br>

The first character is 51, which corresponds to the number 3.<br>
첫 번째 글자는 51로 숫자 3을 나타냅니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.27.png)<br>
<br>

The second character is 56, which corresponds to the number 8.<br>
두 번째 글자는 56으로 숫자 8입니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.28.png)<br>
<br>

The third character is 52, which corresponds to the number 4.<br>
세 번째 글자는 52로 숫자 4입니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.29.png)<br>
<br>

The last character is the number 5.<br>
The password is 3845, and the process will proceed to the next step.<br>

마지막은 숫자 5입니다. 비밀번호는 3845로 다음 단계로 넘어가겠습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* Time-Based SQLi<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.30.png)<br>

This is a method of forcibly introducing time delays to extract data when no clues are visible on the screen.<br>
It is an attack that determines a condition as true when the same amount of time is delayed by inserting a waiting time into user input.<br>

화면에 아무런 단서가 없을 때 강제적으로 시간을 넣어 데이터를 이끌어내는 방법입니다.<br>
사용자 입력값에 대기시간을 넣어 같은 시간이 소요되면 참(True)로 판별하는 공격입니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.31.png)<br>

By creating a waiting state for 5 seconds using SLEEP(5),<br>
if a response is received after 5 seconds, it indicates a true result without any syntax errors.<br>

SLEEP(5)처럼 5초 동안 대기상태를 만들어 5초 뒤에 응답이 오면 문법적 오류없이 참(True)를 나타냅니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.32.png)<br>

Instead of the initial URL tryhackme.com, a non-existent value such as admin123 was used to prevent the user input from being overridden.<br>
A response was received after a 5-second delay.This confirms normal operation and indicates that the attack can be carried out.<br>

초기화면의 Url tryhackme.com 대신에 'admin123'이라는 존재하지 않는 값을 넣어 사용자 입력값이 묻히는 걸 방지하겠습니다.<br>
대기시간 5초 뒤에 응답이 왔습니다. 정상작동으로 공격이 가능한 상태입니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.34.png)<br>

This is the process of identifying the first character.<br>
It exists within the ASCII code range of 48 to 57, and a response was received after 3 seconds according to the user input.<br>

첫 번째 글자를 찾는 과정입니다. ascii코드 48에서 57사이에 존재하는 값이며, 사용자 입력값대로 3초뒤에 응답이 왔습니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.35.png)<br>

The second character is 57, which corresponds to the number 9.<br>
두 번째 글자는 57로 숫자 9입니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.36.png)<br>

The second character is 54, which corresponds to the number 6.<br>
세 번째 글자는 54로 숫자 6입니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.37.png)<br>

Finally, the exact value will be identified using LIKE 'a%'.<br>
Because the response time was 0.001 seconds instead of the expected 1 second, it indicates that the password is not 4960.<br>

마지막은 LIKE 'a%'를 이용해 정확한 값을 찾겠습니다. 사용자 입력값 1초와 다르게 0.001초로 비밀번는 4960이 아닙니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.38.png)<br>

The password was identified as 4961, and it was successfully discovered using LIKE '4961%'.<br>
비밀번호는 4961로 LIKE '4961%'을 이용해 찾기에 성공했습니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/sql/sqlinjection/.39.png)<br>

In this section, SQL injection was successfully performed, and the flag was obtained.<br>
이번 섹션의 Flag로 SQL Injection 성공했습니다. 








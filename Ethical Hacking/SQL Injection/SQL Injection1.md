![image break](/Pictur/ethicalhacking/sqlinjection/1.png)<br>
The database will be obtained by exploiting an SQL injection vulnerability.<br>
SQL 인젝션 취약점을 이용해 데이터베이스를 획득하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/1-1.png)<br>
![image break](/Pictur/ethicalhacking/sqlinjection/1-2.png)<br>
![image break](/Pictur/ethicalhacking/sqlinjection/1-3.png)<br>
![image break](/Pictur/ethicalhacking/sqlinjection/1-4.png)<br>

<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/2.png)<br>
Mutillidae will be used. First, an account will be created.<br>
Mutillidae를 이용하겠습니다. 먼저 계정을 만들겠습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/3.png)<br>
The account was created, but record creation failed.<br>
계정을 만들었는데 레코드 생성에 실패했습니다. 
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/4.png)<br>
The configuration file will be accessed to change the settings.<br>
설정 파일로 이동해 설정 변경을 하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/5.png)<br>
These are the default settings.<br>
기본 설정값입니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/6.png)<br>
The setting will be changed to OWASP 10.<br>
owasp10으로 변경합니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/7.png)<br>
An account will be created.<br>
계정을 생성하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/8.png)<br>
An account named ‘james’ has been created.<br>
james라는 이름으로 계정이 생성되었습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/.9.png)<br>
When logging in with the created account using an incorrect password, the system crashes and an error occurs.<br>
The AND operator will be used to log in.<br>

만든 계정으로 올바른 암호가 아닌 '만 입력하면 시스템이 망가지면서 오류가 나옵니다. 이 AND를 이용해서 로그인 하도록 하겠습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* Post Method Injection
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/10.png)<br>
The password for ‘james’ is 222222. Login will be attempted using the AND operator and # to test whether 2 equals 3.<br>
james의 비밀번호는 222222입니다. 2와 3이 같다는 걸 AND와 #을 이용해 로그인 하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/11.png)<br>
Login attempt failed.<br>
로그인에 실패했습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/12.png)<br>
This time, login will be attempted using # to test whether 2 equals 2.<br>
이번엔 2는 2와 같다는 걸 (해시사인) # 이용해 로그인 하겠습니다.
<br>
<br>
<br>
<br>
<br>
* Login
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/13.png)<br>
Login was successful. Login was successful. Using the hash sign (#), it is possible to log in without knowing the password.<br>
로그인에 성공했습니다. 해시사인 #을 이용해 비밀번호를 몰라도 로그인할 수 있습니다. 
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/14.png)<br>
This time, an attempt will be made using the administrator account name ‘admin’.<br>
Only the portion from 2' up to the hash sign (#) will be used as the password.<br>

이번엔 admin 관리자 이름으로 시도하겠습니다. 2'부터 해시사인까지만 비밀번호로 사용하겠습니다.
<br>
<br>
<br>
<br>
<br>
* Login
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/14-1.png)<br>
Login was successful.<br>
로그인에 성공했습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/15.png)<br>
Login will be attempted using admin'# with random numbers instead of admin.<br>
admin 대신 admin'#와 숫자를 랜덤으로 로그인 하겠습니다.
<br>
<br>
<br>
<br>
<br>
* Login
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/16.png)<br>
Login was successful.<br>
로그인에 성공했습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* Get Method Injection
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/17.png)<br>
This time, user information will be extracted.<br>
이번엔 사용자 정보를 추출하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/18.png)<br>
When logging in with the initially created credentials (james / 222222), the account details are displayed.<br>
초기 생성대로 james 222222로 로그인하면 계정 세부 정보가 나옵니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/.19.png)<br>
As with the POST method, the # symbol will be used to perform login by attaching it directly to the URL.<br>
Post Method 방법처럼 '#를 이용해 Url 그대로 url에 붙여넣어서 로그인을 하겠습니다. 
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/19-1.png)<br>
No response is received.<br>
아무런 응답이 없습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/20.png)<br>
When using the GET method, # is interpreted as a special character, so it must be replaced with its HTML-encoded value %23 before sending.<br>
Get 방식을 이용할 때는 #을 특수한 용도로 인식하기 때문에 HTML 인코딩 값인 %23으로 바꿔서 전달해야합니다.<br>
<br>
<br>
<br>
<br>
<br>


![image break](/Pictur/ethicalhacking/sqlinjection/22.png)<br>
The account details for the admin account have been displayed.<br>
admin 계정의 세부 정보가 나왔습니다.
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
* Database
<br>
<br>
<br>


![image break](/Pictur/ethicalhacking/sqlinjection/23.png)<br>
By using UNION SELECT * FROM accounts, all accounts can be queried.<br>
UNION SELECT * FROM accounts를 넣어 모든 계정을 조회할 수 있습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/24.png)<br>
These are all the accounts in the database.<br>
데이터베이스에 있는 모든 계정입니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/25.png)<br>
ORDER BY 1 sorts the data by the first column. By using numbers, the number of columns can be determined.<br>
ORDER BY 1은 1열의 데이터 정렬로 숫자를 넣음으로써 컬럼(칸)의 개수를 알 수 있습니다. 
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/26.png)<br>

For example, if 10 is used and a syntax error occurs, it indicates that the number of columns is fewer than 10.<br>
예를 들어, 10을 넣어서 구문 오류가 나왔으면 컬럼의 개수가 10개 미만임을 나타냅니다. 
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/29.png)<br>

<br>


![image break](/Pictur/ethicalhacking/sqlinjection/30.png)<br>

It can be determined that values exist in columns 2, 3, and 4.<br>
값에 2,3,4열에 값이 존재함을 알 수 있습니다. 
<br>
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/31.png)<br>
<br>
<br>
<br>
<br>
<br>
![image break](/Pictur/ethicalhacking/sqlinjection/32.png)<br>
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/33.png)<br>
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/34.png)<br>
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/35.png)<br>
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/36.png)<br>
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/37.png)<br>
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/38png)<br>
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/39.png)<br>
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/ethicalhacking/sqlinjection/40.png)<br>














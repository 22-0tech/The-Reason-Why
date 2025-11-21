**Mysql/MariaDB<br>
<br>
The purpose is to systematically store and protect data.<BR>
* 목적 : 데이터를 체계적으로 저장 및 보호를 하기 위함<br>
<bR>
<br>
<Br>


The package name for the MariaDB server is mariadb-server.
MariaDB 서버의 패키지 이름은 mariadb-server입니다.<BR>

![image break](../Pictur/step16/db1.png)<br>
<br>
<br>

![image break](../Pictur/step16/db2.png)<br>
MariaDB is enabled.<bR>
MariaDB를 활성화합니다.<br>
<br>
<br>
<br>


![image break](../Pictur/step16/db3.png)<br>
MariaDB is used with the mysql client.<br>
mysql로 MariqDB를 사용합니다.<br>
<br>
<br>
<Br>
<Br>
<Br>



![image break](../Pictur/step16/db2-1.png)<br>
<br>
* the MariaDB daemon owner name is 'mysql', high compatibility is maintained, allowing seamless operation.<br>
* Why MariaDB 데몬의 소유자 이름이 Mysql로 높은 호환성을 유지하여 운용이 가능합니다.<br>
<br>
<br>
<br>


![image break](../Pictur/step16/db4.png)<br>
MariaDB has three default databases.<br>
MariaDB에는 기본적으로 세 개의 데이터베이스가 있습니다.<br>
<Br>
<Br>
<Br>


![image break](../Pictur/step16/db5.png)<br>
An additional database will be created.<Br>
To create tables in that database, it must be selected with the USE command<br>

데이터베이스를 하나 더 만들겠습니다.<br>
해당 DB에 테이블 만드는 작업을 하려면 use명령으로 지정해야 합니다.<br>
<br>


![image break](../Pictur/step16/db6.png)<br>
The database has been created.<br>
DB가 생성되었습니다.
<br>
<br>
<br>
<br>
<Br>


![image break](../Pictur/step16/db7.png)<br>
<br>

![image break](../Pictur/step16/db7-1.png)<br>
The tables d_grade and d_info are defined with their respective columns.<Br>
VARCHAR is a variable-length data type, and the number specifies the maximum length.<br>
d_grade, d_info라는 테이블에 각 항목을 지정합니다. varchar는 변수가 자료형이며 숫자는 최대 길이입니다.<br>
<br>
<Br>
<Br>


![image break](../Pictur/step16/db8.png)<br>
The table structure requires each row to be unique, necessitating a key.<Br>
As NULL values are not permitted, the primary key must not allow NULL; thus, NULL is disallowed by default.<BR>
테이블의 구조입니다. 각 행마다 고유성을 가져 키를 보유해야 합니다.<br>
Null값은 없다는 뜻이므로, 기본 키 값에 Null을 허용하면 안 되므로, 먼저 null을 허용하지 않겠습니다.<br>
<br>
<br>
<br>
<br>

![image break](../Pictur/step16/db9.png) ![image break](../Pictur/step16/db10.png)<br>
NULL was changed from allowed to disallowed, and the primary key was created.<BR>
Null 허용에서 거부로 바꿨으며, 기본 키를 생성했습니다.<br>
<br>
<br>


![image break](../Pictur/step16/db9-1.png)<br>

<br>
<br>
<br>
<br>
<Br>
<Br>
<Br>
<Br>
<Br>



![image break](../Pictur/step16/db11.png)<br>
Strings and integers are entered as data.<br>
데이터로 문자열과 정수를 입력합니다.<br>

<br>
<br>

![image break](../Pictur/step16/db12.png)<br>
When the table is queried, the entered values are displayed.<br>
테이블을 조회하면 입력 값이 보입니다.<br>




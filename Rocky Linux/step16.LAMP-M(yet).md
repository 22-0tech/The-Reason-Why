**Mysql/MariaDB<br>
<br>

* 목적 : 데이터를 체계적으로 저장 및 보호를 하기 위함<br>


MariaDB 서버의 패키지 이름은 mariadb-server입니다.<BR>

![image break](../Pictur/step16/db1.png)<br>
<br>
<br>

![image break](../Pictur/step16/db2.png)<br>
<br>
MariaDB를 활성화합니다.<br>
<br>
<br>
<br>


![image break](../Pictur/step16/db3.png)<br>

mysql로 MariqDB를 사용합니다.<br>
<br>
<br>
![image break](../Pictur/step16/db2-1.png)<br>
<br>
*Why - MariaDB 데몬의 소유자 이름이 Mysql로 높은 호환성을 유지하여 운용이 가능합니다.<br>
<br>
<br>
<br>


![image break](../Pictur/step16/db4.png)<br>
<br>
MariaDB에는 기본적으로 세 개의 데이터베이스가 있습니다.<br>
<Br>


![image break](../Pictur/step16/db5.png)<br>
<br>
데이터베이스를 하나 더 만들겠습니다.<br>
해당 DB에 테이블 만드는 작업을 하려면 use명령으로 지정해야 합니다.<br>
<br>


![image break](../Pictur/step16/db6.png)<br>
<br>
DB가 생성되었습니다.
<br>
<br>
<br>
<br>
<Br>


![image break](../Pictur/step16/db7.png)<br>
<br>

![image break](../Pictur/step16/db7-1.png)<br>
<br>
d_grade, d_info라는 테이블에 각 항목을 지정합니다. varchar는 변수가 자료형이며 숫자는 최대 길이입니다.
<br>
<Br>
<Br>


![image break](../Pictur/step16/db8.png)<br>

테이블의 구조입니다. 각 행마다 고유성을 가져 키를 보유해야 합니다. 

<br>
<br>
<br>
<br>

![image break](../Pictur/step16/db9.png)<br>

<br>
<br>

![image break](../Pictur/step16/db9-1.png)<br>

<br>
<br>


![image break](../Pictur/step16/db10.png)<br>

<br>
<br>

![image break](../Pictur/step16/db11.png)<br>

<br>
<br>

![image break](../Pictur/step16/db12.png)<br>











<br>
dnf -y install mariadb-server
<br>
systemctl --now enable mariadb
<br>
mysql
<br>

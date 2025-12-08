* File transfer & Network
<br>
<br>
<Br>


![image break](/Pictur/Docker/docker2/do2-1.png)<br>
It is possible to check the network using the ifconfig command. To use this command, net-tools needs to be installed.<br>
ifconfig 명령어로 네트워크를 확인합니다. 이때 명령어를 사용하기 위해 net-tools을 설치해야 합니다.
<br>
<br>

![image break](/Pictur/Docker/docker2/do2-2.png)<br>

<br>

![image break](/Pictur/Docker/docker2/do2-3.png)<br>

<br>
<br>
<br>
<br>


![image break](/Pictur/Docker/docker2/do2-4.png)<br>
pwd displays the current working directory.<br>
현재 경로입니다.
<br>
<br>
<br>

![image break](/Pictur/Docker/docker2/do2-5.png)<br>
A terminal is opened, and Ubuntu is started.<br>
터미널을 하나 열고 ubuntu를 실행합니다.
<br>
<br>
<br>

![image break](/Pictur/Docker/docker2/do2-6.png)<br>
The file test.txt in the current directory is copied to /home in the newly started Ubuntu container.<br>
현재 경로에 있는 test.txt를 새로 시작한 ubuntu 컨테이너 /home에 복사합니다. 
<br>
<br>
<br>

![image break](/Pictur/Docker/docker2/do2-7.png)<br>
The file transfer is complete.<Br>
파일 전송이 됐습니다.
<br>
<br>
<br>
<br>
<br>
<br>

* postgres
<br>


![image break](/Pictur/Docker/docker2/do2-8.png)<br>
Postgres is an open-source database management system.<br>
postgres는 오픈 소스로, 데이터베이스 관리 시스템입니다.
<br>
<br>

![image break](/Pictur/Docker/docker2/do2-9.png)<br>
![image break](/Pictur/Docker/docker2/do2-10.png)<br>

<Br>
<br>
<Br>


![image break](/Pictur/Docker/docker2/do2-11.png)<br>
Before running PostgreSQL, a container is created.<br>
The -n option sets the name, the -e option specifies the superuser password, and the -d option allows it to run in the background.<Br>
postgresql 실행 전에 컨테이너를 만듭니다.<BR>
-n으로 이름을 설정, -e로 Superuser의 비밀번호를 정합니다. -d로 백그라운드에서도 실행될 수 있도록 합니다.<br>
<br>
<br>
<Br>


![image break](/Pictur/Docker/docker2/do2-12.png)<br>
The created container is opened with a bash shell to access PostgreSQL.<br>
A superuser is created, and a database is created.<br>
만들어진 컨테이너를 bash쉘로 열어 postgres에 진입합니다.<br> 
Superuser를 생성하고 데이터베이스를 생성합니다.<br>
<br>
<br>
<br>


![image break](/Pictur/Docker/docker2/do2-13.png)<br>
A table is created in the database, and the tables are viewed using \dt.<br>
데이터베이스에서 테이블을 생성하고 \dt로 테이블을 조회합니다.<br>
<br>
<Br>
<Br>

![image break](/Pictur/Docker/docker2/do2-14.png)<br>
Values are entered into id and name.<br>
id와 name에 값을 입력합니다.<br>



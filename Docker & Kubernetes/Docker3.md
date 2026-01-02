**Storage
<br>
<Br>
<Br>

There are three types of storage in Docker: volumes, bind mounts, and tmpfs mounts.<br>
도커 저장소에는 Volume, bind mount, tmpfs mount 세 가지 종류가 있습니다.<br>
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
* volume
<br>
<br>
<br>
<br>

![image break](/Pictur/Docker/docker3/do1.png)<br>
First, the repository will be checked.<br>
먼저 저장소를 확인하겠습니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Docker/docker3/do2.png)<br>
A container is run with the created volume connected to PostgreSQL.<br>
생성된 볼륨을 PostSQL과 연동시켜 컨테이너를 실행하겠습니다
<br>
<br>
<br>
<br>

![image break](/Pictur/Docker/docker3/do3.png)<br>
A user named user1 is created with SUPERUSER privileges.<br>
user1이라는 사용자를 SUPERUSER권한으로 생성합니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Docker/docker3/do4.png)<br>
The location where Docker database data is stored on the host PC has been identified.<br>
It can be confirmed that the data remains safe and persistent even if the container is deleted.<br>
도커 DB 데이터가 호스트 PC 어디에 저장되는지 경로를 찾아냈습니다.<br>
컨테이너를 삭제하더라도 데이터가 유실되지 않고 안전하게 보존된다는 걸 확인할 수 있습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

* bind mount
<br>
<br>
<br>
<br>

![image break](/Pictur/Docker/docker3/do5.png)<br>
test1.txt and test2.txt are stored on both the Docker host and inside the container.<br>
test1.txt 파일과 test2.txt 도커 호스트뿐만 아니라 파일이 컨테이너에도 저장될 예정입니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Docker/docker3/do6.png)<br>
The container is run.<Br>
컨테이너를 실행하겠습니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Docker/docker3/do7.png)<br>
Checking the file list shows that test1.txt and test2.txt exist.<br>
파일 목록을 확인하면 test1.txt 파일과 test2.txt 파일이 존재하는 것을 알 수 있습니다.
<br>
<br>
<br>
<br>
<br>
<Br>
<br>

* tmpfs mount
<br>
<br>
Since a tmpfs mount stores data temporarily in the Docker host’s memory, it does not support data sharing between containers.<br>
tmpfs mount는 일시적으로 도커 호스트 메모리에 저장하기 때문에 컨테이너 간 데이터 공유를 지원하지 않습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/Docker/docker3/do8.png)<br>
The container is queried.<br>
컨테이너를 조회합니다.
<br>
<br>
<br>

![image break](/Pictur/Docker/docker3/do9.png)<br>
inspect can be used to view detailed configuration settings.<br>
Inspect를 이용해 상세 설정값을 확인할 수 있습니다.
<br>
<br>
<br>

![image break](/Pictur/Docker/docker3/do10.png)<br>



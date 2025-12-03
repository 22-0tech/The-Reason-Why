**Docker

<br>
Docker Installation and Basics<br>
도커 설치 및 기초 
<br>
<Br>
<br>


<br>
<Br>
<Br>

![image break](/Pictur/Docker/do1.png)<br>
Ubuntu is installed following the official Docker documentation.<br>
도커 공식 문서에 따라 Ubuntu 설치를 진행합니다.<br>
<br>
<Br>
<Br>

Docker will be practiced on Ubuntu using MobaXterm.<br>
MobaXterm을 이용해서 Ubuntu로 Docker를 실습하겠습니다.
<br>
<br>

![image break](/Pictur/Docker/do2.png)<br>
It was verified that everything works properly by using docker run hello-world.<br>
docker run hello-world를 이용해 잘 작동하는지 알아봤습니다.<br>
<br>
<Br>
<Br>

![image break](/Pictur/Docker/do3.png)<br>
In Docker, an image is a package that can be executed inside a container.<br>
도커에서 이미지란 컨테이너 안에서 실행 가능한 패키지입니다.<br> 
<Br>
<Br>

![image break](/Pictur/Docker/do4.png)<br>
The Ubuntu and Python images were pulled.<br>
우분투와 파이썬 이미지를 가져왔습니다.

<br>
<Br>
<Br>

![image break](/Pictur/Docker/do5.png)<br>
![image break](/Pictur/Docker/do5-1.png)<br>
Upon listing the images, Python and Ubuntu are visible.<br>
이미지 조회를 해보니 파이썬과 우분투가 보입니다.<br>
<br>
<Br>
<Br>

![image break](/Pictur/Docker/do6.png)<br>
The Ubuntu and Python images were run as containers. It can be observed that the containers do not produce any output.<br>
This is because when the internal process of a container terminates, the container itself also stops.<br>
우분투와 파이썬 이미지를 컨테이너로 실행했습니다. 컨테이너가 출력되지 않는 것을 볼 수 있습니다.<br>
컨테이너를 실행했을 때 내부 프로세스가 종료되면 컨테이너도 종료되기 때문입니다.<br>
<br>
<Br>

<br>
<Br>
<Br>

![image break](/Pictur/Docker/do8.png)<br>
The container can be accessed using the -it (interactive) option, and entry into the container was achieved<br>
컨테이너 내부에 접속할 때 -it(interactive) 옵션을 활용해 접속할 수 있으며, 내부로 들어왔습니다.
<br>
<Br>
<Br>

![image break](/Pictur/Docker/do9.png)<br>
When listed, the container is visible.<br>
조회를 했을 때 해당 컨테이너가 보입니다.
<br>
<Br>
<Br>

![image break](/Pictur/Docker/do10.png)<br>
At this point, another terminal is opened to stop the running container using stop.<br>
여기서 터미널을 하나 더 열어서 실행시킨 컨테이너를 stop으로 중단합니다.<br>
<br>
<Br>
<Br>

![image break](/Pictur/Docker/do11.png)<br>
Since it was stopped in another terminal, the existing terminal container has been terminated.<br>
다른 터미널에서 중지했기 때문에 기존 터미널 컨테이너는 종료되었습니다.
<br>
<Br>
<Br>

![image break](/Pictur/Docker/do12.png)<br>
The container can be started with start and re-entered using attach.<br>
start로 컨테이너를 실행시키고 attach로 다시 내부로 접속할 수 있습니다. 
<br>
<Br>
<Br>
<br>
<Br>
<br>

![image break](/Pictur/Docker/do13.png)<br>
It is possible to view even the stopped containers by using ls -a.<br>
ls -a로 종료된 컨테이너까지 조회할 수 있습니다.

<br>
<Br>
<Br>

![image break](/Pictur/Docker/do14.png)<br>
The stopped container is removed using rm.<br>
종료된 컨테이너를 rm으로 삭제합니다.






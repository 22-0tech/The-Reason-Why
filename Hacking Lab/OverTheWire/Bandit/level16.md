**Applied problem<br>
응용 문제<br>
<br>


![image break](/Pictur/Level16/bandit1.png) <br>
As described in the problem, the first step is to find a port listening between 31000 and 32000.<br>
문제에 제시된 것처럼 먼저 31000부터 32000사이에 리스닝 중인 포트를 찾습니다.
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit2.png) <br>
Purpose: service detection. Using -sV makes it easier to solve.<br>
Among the two SSL-enabled ports, only one returns the password; an unknown service is suspected.<br>
The service could not be identified, and it may be a server with special behavior.<br>

*WHY-서비스 탐지 목적. -sV를 사용하면 더 수월하게 풀 수 있습니다. <BR>
ssl 사용하는 두 개 포트 중 한 개만 비밀번호를 반환한다고 합니다. unknown이 의심됩니다. <br>
서비스를 판별하지 못했으며, 특별 동작을 하는 서버일 가능성이 있습니다.<br>
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit3.png) <br>
First, a connection is made to one of the ports.<br>
먼저 한 개 포트 연결합니다<br>
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit4.png) <br>
The current password is entered, but the connection closes.<br>
현재 비밀번호를 입력했지만 닫힙니다. 
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit5.png) <br>
An attempt is made to connect to the other port.<br>
다른 포트에 연결 시도합니다.<br>
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit6.png) <br>
The current password is entered, but “KEYUPDATE” keeps appearing.<br>
현재 비밀번호를 입력했는데 계속 KEYUPDATE라고 나옵니다.
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit7.png) <br>
Protocol information appears in the middle, showing TLSv1.3.<br>
In TLS version 1.3, there is a bug where sending EOF occurs when the first character is k/K.<br>

중간에 프로토콜 정보가 있는데 TLSv1.3이라고 나옵니다. <br>
TLS 버전 1.3에서, 첫 글자가 k/K일 때 EOF를 보내는 버그입니다. <Br>
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit8.png) <br>
The connection is retried with the option to ignore EOF.<br>
EOF 무시 옵션을 넣어주고 다시 접속합니다.
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit9.png) <br>
A private key file is displayed. The password can be obtained using the key file.<br>
개인 키 파일이 나옵니다. 키 파일을 이용해서 비밀번호를 얻을 수 있습니다.<br>
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit10.png) <br>
A temporary directory is created for performing the work.<br>
작업할 수 있게 임시 디렉터리를 만듭니다.
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit11.png) <br>
The key file is added, and an SSH session is initiated.<br>
키 파일을 붙여넣고 ssh 접속 합니다.<br>
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit12.png) <br>
SSH rejected the connection, judging the private key as too publicly accessible.<br>
SSH가 개인 키를 너무 공개적으로 판단해서 거부했습니다.<br>
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit13.png) <br>
The key file permissions are changed to the standard 600, then the next level is accessed.<br>
키파일 표준 600으로 변경 후 다음 레벨로 접속합니다.<br>
<br>
<br>
<br>

![image break](/Pictur/Level16/bandit14.png) <br>


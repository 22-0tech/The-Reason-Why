![image 1](/Pictur/Hacking%20lab/lazyadmin/0.png)

<br>
<br>


![image 1](/Pictur/Hacking%20lab/lazyadmin/1.png)<br>
The scan will be started using Nmap. <br>
-A: Detailed scan for operating system, service version, etc., -T4: Speed up scan with level 4 timing, -p-: Scan all ports.<br>
nmap을 이용한 스캔부터 하겠습니다. -A:운영체제, 서비스 버전 등 상세 스캔, -T4: 4단계 속도 상승, -p-:모든 포트 스캔
<br>
<br>
<br>

![image 2](/Pictur/Hacking%20lab/lazyadmin/2.png)<br>
The web page is functioning normally, but the specific services cannot be determined.<br>
웹 페이지가 정상적으로 작동 중이며, 구체적인 서비스는 알 수 없습니다.
<br>
<br>
<br>


![image 3](/Pictur/Hacking%20lab/lazyadmin/3.png)<br>
dirsearch will be used to search the web page, excluding the 400-series responses, and including PHP and HTML.<br>
dirsearch를 이용해 웹 페이지를 검색하는데 400번 대는 빼고, php,html을 포함합니다.
<br>
<br>
<br>
<br>

![image 4](/Pictur/Hacking%20lab/lazyadmin/4-1.png)<br>
![image 4](/Pictur/Hacking%20lab/lazyadmin/4-2.png)<br>
<br>
The directory '/content' was discovered, and upon accessing it, a web page named 'Sweet rice' appeared.<br>
/content 발견 디렉터리에 접속 후 Sweet rice라는 웹 페이지가 나왔습니다.
<br>
<br>
<br>
<br>
<br>


![image 5](/Pictur/Hacking%20lab/lazyadmin/5.png)<br>
Google will be used to search for vulnerabilities.<br>
구글을 이용해 취약점 검색을 하겠습니다.
<br>
<br>
<br>
<br>

![image 6](/Pictur/Hacking%20lab/lazyadmin/6.png)<br>
First, navigate to the directory of the vulnerability on the first page.<br>
먼저 첫 번째 페이지 취약점의 디렉터리로 이동합니다.
<br>
<br>
<br>
<br>

![image 7](/Pictur/Hacking%20lab/lazyadmin/7.png)<br>

<br>
<br>
<br>

![image 8](/Pictur/Hacking%20lab/lazyadmin/8.png)<br>
Upon further inspection of the content, account details and hash values are visible.<br>
내용을 자세히 살펴보면, 계정과 해시값이 보입니다.<br>
<br>
<br>
<br>

![image 9](/Pictur/Hacking%20lab/lazyadmin/9-0.png)<br>
<br>
<br>


![image 9](/Pictur/Hacking%20lab/lazyadmin/9.png)<br>
<br>
<br>
The hash values were decoded to plain text using a site called CrackStation.<br>
CrackStation이라는 사이트를 이용해 해시값을 평문으로 해독했습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>


![image 10](/Pictur/Hacking%20lab/lazyadmin/10.png)<br>
This is the second page.<br>
두 번째 페이지입니다.
<br>
<br>

![image 11](/Pictur/Hacking%20lab/lazyadmin/11.png)<br>
This is a vulnerability where a script is uploaded to request a connection to the attacker's PC, allowing for privilege escalation.<br>
공격자의 PC로 연결을 요청하는 스크립트 올려 권한을 획득하는 취약점입니다.
<br>
<br>
<br>
<br>



![image 12](/Pictur/Hacking%20lab/lazyadmin/12.png)<br>
Accessing '/as/' led to a login page. The previously obtained ID and decoded value can be used to log in.<br>
/as/로 접속했더니 로그인 페이지가 나왔습니다. 앞서 얻은 ID와 해독값을 이용해 접속할 수 있습니다. 
<br>
<br>
<br>

![image 13](/Pictur/Hacking%20lab/lazyadmin/13.png)<br>
This is the media center. A PHP reverse shell file will be used to upload a file that meets the conditions.<br>
Media Center입니다. 여기에 파일을 올리는데 조건에 맞게 php 리버스 쉘 파일을 이용하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 14](/Pictur/Hacking%20lab/lazyadmin/14.png)<br>


<br>
<br>
<br>

![image 15](/Pictur/Hacking%20lab/lazyadmin/15.png)<br>
This is a PHP reverse shell script. 'change this' sets the attacker's IP and port.<br>
The vulnerability exploits the loophole in the security policy that allows signals to go from internal to external.<br>

php 리버스 쉘 스크립트입니다. 'change this' 공격자의 IP와 포트를 설정합니다.<br>
*Why-내부에서 외부로 나가는 신호는 허용하는 허점 이용(보안 정책 우회) 
<br>
<br>
<br>

![image 16](/Pictur/Hacking%20lab/lazyadmin/16.png)<br>
The attacker's IP and port 7777 are opened and waiting.<br>
*Why - Reverse shell.<br>
공격자의 IP와 7777번 포트를 열고 기다립니다.<br>
*Why-리버스 쉘
<br>
<br>
<br>


![image 17](/Pictur/Hacking%20lab/lazyadmin/17.png)<br>
Upload the reverse shell script<br>
리버스 쉘 스크립트 업로드
<br>
<br>
<br>

![image 18](/Pictur/Hacking%20lab/lazyadmin/18.png)<br>
Clicking the uploaded file will allow obtaining a shell from the open port 7777.<br>
업로드 된 파일을 클릭하면 열린 7777번 포트에서 쉘을 획득할 수 있습니다.
<br>
<br>
<br>

![image 19](/Pictur/Hacking%20lab/lazyadmin/19.png)<br>
Currently, privilege escalation from the web service account to root is required.<br>
The command to execute root privileges without a password will be checked.<br>
현재, 웹 서비스 계정에서 root로 권한상승을 해야합니다. 비밀번호 없이 root 권한을 실행할 수 있는 명령어를 확인하겠습니다.
<br>
<br>
<br>

![image 20](/Pictur/Hacking%20lab/lazyadmin/20.png)<br>
This is a reverse shell script. The attacker's IP will be changed as shown above.<br>
리버스 쉘 스크립트입니다. 위와 같이 공격자의 IP로 변경하겠습니다.
<br>
<br>
<br>

![image 21](/Pictur/Hacking%20lab/lazyadmin/21.png)<br>
<br>
<br>
<br>


![image 22](/Pictur/Hacking%20lab/lazyadmin/22.png)<br>
The modified script will be executed, and port 5554 will be monitored.<br>
변경된 스크립트를 실행하고 5554번 포트를 보겠습니다.
<br>
<br>
<br>

![image 23](/Pictur/Hacking%20lab/lazyadmin/23.png)<br>
Privilege escalation has been successfully achieved.<br>
권한 상승(Privilege Escalation)에 성공했습니다.



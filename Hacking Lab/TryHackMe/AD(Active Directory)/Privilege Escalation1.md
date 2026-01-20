![image 1](/Pictur/Hacking%20lab/AD/privesc/1.png)<br>
The objective is Windows privilege escalation.<br>
윈도우 권한 상승이 목표입니다.
<br>
<br>
<br>
<br>
<br>
<br>

<Br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/privesc/2.png)<br>
As provided, the initial access is established via RDP.<br>
주어진대로 첫 시작은 rdp로 시작합니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/privesc/.3.png)<br>

<br>

![image 1](/Pictur/Hacking%20lab/AD/privesc/4.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/privesc/0.png)<br>
By navigating to the visible PrivEsc folder and reviewing the tools, inferences can be made.<br>
보이는 폴더 PrivEsc로 이동해 도구들을 보고 추론이 가능합니다.
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/AD/privesc/5.png)<br>
First, a reverse shell payload is created.<br>
먼저 리버스 쉘 페이로드를 만들겠습니다.
<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/AD/privesc/6.png)<br>
The reverse shell will be downloaded on Windows using the web server.<br>
웹 서버를 이용해 윈도우에서 리버스 쉘을 다운받도록 하겠습니다.
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/AD/privesc/7.png)<br>
The executable is run using .\reverse.exe.<br>
.\reverse.exe를 이용해 실행하겠습니다.
<br>
<br>
<br>
<br>
<br>
<Br>

![image 1](/Pictur/Hacking%20lab/AD/privesc/8.png)<br>
A prompt was obtained on the active port.<br>
활성화된 포트에서 프롬포트가 열렸습니다.
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/AD/privesc/9.png)<br>
winPEASany.exe was the first tool that stood out, and a vulnerability scan is performed immediately.<br>
winPEASany.exe가 먼저 눈에 띄었습니다. 바로 취약점 스캔 하겠습니다.
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/privesc/10.png)<br>
All users are able to exercise full permissions. By copying reverse.exe to the corresponding file, privilege escalation is possible.<br>
모든 유저가 모든 권한을 행사할 수 있습니다. reverse.exe를 해당 파일에 복사해서 실행하면 권한 상승과 연관지을 수 있습니다.
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/AD/privesc/11.png)<br>

<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/privesc/12.png)<br>
The malware (reverse.exe) will be copied to the specified file and executed.<br>
악성코드(reverse.exe)를 해당 파일에 복사하고 start 하겠습니다. 
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/AD/privesc/.13.png)<br>
An active port opens, and identity verification confirms the highest administrative account available on the Windows operating system.<br>
활성화된 포트가 열리고 신원을 확인하면 윈도우 운영체제에서 존재할 수 있는 최고 관리자 계정입니다.
<br>
<Br>
<Br>
<br>
<br>
<br>
<br>
<Br>
<Br>


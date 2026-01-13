![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/1.png)<br>
It is a vulnerability in the Windows Print Spooler service.<br>
Windows Print Spooler 서비스의 취약점입니다. 
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
* 공격(Attack)<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/2.png)<br>
First, CVE-2016-1676 is downloaded using git clone.<br>
git clone을 이용해서 먼저 CVE-2016-1676를 다운 받습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/3.png)<br>
Most Windows system function extensions are .dll. Based on this, a reverse shell payload is generated.<br>
윈도의 시스템 기능의 확장자는 대부분 .dll입니다. 이를 적용해 리버스 쉘 페이로드를 생성합니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/4.png)<br>
The payload is configured according to the constructed payload.<br>
구성한 페이로드대로 페이로드 설정을 합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/5.png)<br>
The attacker’s IP address and port number are set to localhost.<br>
localhost에 공격자 IP와 포트번호를 설정합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/6.png)<br>
It is executed in the background using -j and verified with jobs.<br>
-j를 이용해 백그라운드에서 실행하고 jobs으로 확인합니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/7.png)<br>
A Samba server is opened so that the target can download the attacker’s malicious DLL via the network shared folder pn using the SMB2 protocol.<br>
SMB2 프로토콜을 이용해 공격자의 악성코드 DLL을 타깃이 네트워크 공유폴더 pn을 통해 다운받을 수 있도록 삼바 서버를 오픈합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/7-1.png)<br>
Before carrying out the attack, it is necessary to check whether the printer service protocols MS-RPRN or MS-PAR are running.<br>
공격을 수행하기 전에 프린터 서비스인 MS-RPRN 또는 MS-PAR 프로토콜이 작동 중인지 확인을 해야합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/8.png)<br>
In this step, the attack is performed by exploiting the CVE-2021-1675 vulnerability on the target server and delivering the attacker’s malicious .dll file.
Errors occur after Try3, which is normal behavior.<br>

CVE-2021-1675의 취약점을 타깃 서버에 전송하여 공격을 수행하는 단계로 공격자의 악성코드 .dll을 전송합니다.<br>
Try3 이후로 오류가 나는데 정상적인 상황입니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/9.png)<br>
A Meterpreter session has been successfully opened.<br>
미터프리터 세션이 성공적으로 열렸습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/10.png)<br>
Privilege checks confirm that SYSTEM-level privileges have been obtained.<br>
윈도우 운영체제 최고 권한인 SYSTEM 권한을 획득했습니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/11.png)<br>
With SYSTEM privileges, the flag was verified, and the passwords of all accounts can also be obtained via hashdump.<br>
SYSTEM 권한으로 flag를 확인했으며, hashdump로 모든 계정의 비밀번호 또한 확인할 수 있습니다.

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

* 방어(Deffense)<br>

<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/15.png)<br>
At the specified path, a malicious file (reverse.dll) planted by the attacker was identified.<br>
해당 경로에 공격자가 심어놓은 악성파일(reverse.dll)이 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/16.png)<br>
Assuming the role of a defender, the malicious file (reverse.dll) will be deleted.<br>
'방어자'라고 가정하고 악성파일(reverse.dll)을 삭제하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/7-2.png)<br>
Even though the malicious file (reverse.dll) has been deleted, the shell is still running.<br>
악성파일(reverse.dll)이 삭제되었는데도 쉘이 작동 중입니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/17.png)<br>
The running processes will be checked using tasklist.<br>
tasklist로 실행 중인 프로세스를 조회하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/18.png)<br>

rundll32.exe는 보통 시스템 설정이나 제어판 등을 열 때 실행됩니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/19.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/nightprintmare/21.png)<br>

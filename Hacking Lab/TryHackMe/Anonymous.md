![image 1](/Pictur/Hacking%20lab/anonymous/1.png)
<br>
<br>
<br>
<br>
<br>

![image 2](/Pictur/Hacking%20lab/anonymous/2.png)<br>

The scan will be started using Nmap.<br>
-A: Detailed scan for operating system, service version, etc., -T4: Speed up scan with level 4 timing, -p-: Scan all ports.<br>
nmap을 이용해 스캔부터 하겠습니다. -A:운영체제, 서비스 버전 등 상세 스캔, -T4: 4단계 속도 상승, -p-:모든 포트 스캔<br>
<br>
FTP was seen first, but SMB is also available and can be utilized.<br>
가장 먼저 ftp가 보였지만, SMB도 있어서 활용할 수도 있습니다.<br>

<br>
<br>
<br>
<br>
<br>

![image 3](/Pictur/Hacking%20lab/anonymous/3.png)<br>
An anonymous connection was made, and the directory will be accessed.<br>
익명으로 접속을 했고 디렉터리로 이동하겠습니다.<br>
<br>
<br>
<br>
<br>
<br>
<br>
![image 4](/Pictur/Hacking%20lab/anonymous/4.png)<br>
Everything can be downloaded using mget, and due to the weak security, put can also be considered.<br>
mget을 이용해 전부 다운로드가 가능했고, 허술한 탓에 put까지 고려할 수 있습니다.
<br>
<br>
<br>
<br>
![image 4](/Pictur/Hacking%20lab/anonymous/4-1.png)<br>
If the attacker modifies this script to a reverse shell and uploads it, they could gain access.<br>
Note: The condition if [ $tmp_files=0 ] will always evaluate to true in Bash, making it a potential vulnerability.<br>
<br>
공격자가 이 스크립트를 리버스 쉘로 수정해서 업로드를 하면 권한을 얻을 수도 있습니다.<br>
참고-if [ $tmp_files=0 ] 이 부분은 Bash 쉘에서 항상 참(True)이 되기 때문에, 취약점이 될 수 있습니다.<br>
<br>
<br>
<br>
<br>
<br>
<br>

![image 5](/Pictur/Hacking%20lab/anonymous/5.png)<br>
*WHY: A one-liner reverse shell is required for the attack's likelihood and convenience.<br>
*WHY-공격 확률과 편의성을 위해 한 줄 리버스 쉘이 요구됩니다.
<br>
<br>
<br>
<br>
<br>
![image 6](/Pictur/Hacking%20lab/anonymous/6.png)<br>
<br>
<br>
<br>
<br>
<br>
![image 7](/Pictur/Hacking%20lab/anonymous/7.png)<br>


<br>
<br>
<br>
<br>
<br>
![image 8](/Pictur/Hacking%20lab/anonymous/8.png)<br>
<br>
<br>
<br>
<br>
<br>
![image 9](/Pictur/Hacking%20lab/anonymous/9.png)<br>
<br>
<br>
<br>
<br>
<br>
![image 10](/Pictur/Hacking%20lab/anonymous/10.png)<br>
<br>
<br>
<br>
<br>
<br>
![image 11](/Pictur/Hacking%20lab/anonymous/11.png)<br>
<br>
<br>
<br>
<br>
<br>
![image 12](/Pictur/Hacking%20lab/anonymous/12.png)<br>
<br>
<br>
<br>
<br>
<br>
![image 13](/Pictur/Hacking%20lab/anonymous/13.png)<br>
<br>
<br>
<br>
<br>
<br>
![image 14](/Pictur/Hacking%20lab/anonymous/14.png)<br>
<br>
<br>
<br>
<br>
<br>
![image 15](/Pictur/Hacking%20lab/anonymous/15.png)<br>
<br>
<br>
<br>
<br>
<br>
![image 16](/Pictur/Hacking%20lab/anonymous/16.png)<br>
<br>
<br>
<br>
<br>
<br>
![image 17](/Pictur/Hacking%20lab/anonymous/17.png)<br>
<br>
<br>
<br>
<br>
<br>
![image 18](/Pictur/Hacking%20lab/anonymous/18.png)<br>

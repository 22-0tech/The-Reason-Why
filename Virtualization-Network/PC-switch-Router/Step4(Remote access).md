** Router Security <br>
<br>


(Packet Tracer)<br>

![image break](../../Pictur/step4/passwd-1.png) <br>
Set the password to AAA to enter privileged mode from user mode.<br>
사용자 모드에서 관리자 모드로에 진입비밀번호를 AAA로 설정합니다. 

![image break](../../Pictur/step4/passwd-2.png)  <br>
The password is in uppercase letters.<br>
*비밀번호는 대문자입니다. 

<br>
<br
<br>
<br>

![image break](../../Pictur/step4/passwd-3.png) <br>
When accessing the device physically or via Telnet, the password can be exposed in plain text.<br>
*장비에 물리적 접근 또는 Telnet 접속 환경에서는 비밀번호가 그대로 노출될 수 있다.

<br>
<br>
<br>

![image break](../../Pictur/step4/passwd-4.png) <br>
service password-encryption – Weak Encryption(Cisco Type 7) <br>
service password-encryption 약한 암호화
<br>
<br>
<br>


![image break](../../Pictur/step4/passwd-5.png) <br>
enable secret - MD5 Hash – Stronger Encryption (password=aaa)<br>
*MD5해시값으로 강한 암호화 

![image break](../../Pictur/step4/passwd-6.png) <br>
<br>
<br>
<br>
<br>
![image break](../../Pictur/step4/passwd-7.png) <br>

![image break](../../Pictur/step4/passwd-8.png) <br>
Even if no service password-encryption is configured, the passwords remain encrypted.<br>
*비밀번호 해제해도 그대로 암호화 되어있음 
no service password-encryption 복호화 안 됨.
<br>
<br>
<br>
<br>
![image break](../../Pictur/step4/passwd-9.png) <br>
Removing the enable password using no enable password.<br>
*no enable password 비밀번호 해제 

<br>
<br>
<br>

![image break](../../Pictur/step4/passwd-10.png) <br>

![image break](../../Pictur/step4/passwd-11.png) <br>
sh run = show running-config<br>
*Password removal completed.
<br>
<br>

![image break](../../Pictur/step4/passwd-12.png) <br>
line vty 0 4 – Virtual Terminal (VTY) lines for remote access, covering lines 0 through 4.<br>
line vty 0 4 :VTY 원격 접속용 가상 포트 0~4번 라인<br>

Set the VTY password to b for remote access.<br>
password b : VTY 접속 시 비밀번호를 b로 설정 <br>

login – Enables password authentication for the line.<br>
login : 패스워드 인증 활성화 <br>

transport input telnet – Allows only Telnet connections on the VTY lines.<br>
transport input telnet : VTY 라인에서 Telnet 접속만 허용 <br>

transport input all – Allows all remote access protocols (for security, it is safer to allow only SSH).<br>
transport input all : 모든 원격 접속 프로토콜 허용 (SSH만 허용하는 것이 안전)

<br>

![image break](../../Pictur/step4/passwd-13.png) <br>
Attempted to connect to the router via Telnet from the PC and entered the password b, but access to privileged mode failed<br>
because the router has no enable password set.<br>
*PC로 라우터에 텔넷 접속 비밀번호 b 입력 그러나 라우터에 비밀번호가 없으므로 관리자 모드에 진입 불가<br>

![image break](../../Pictur/step4/passwd-14.png) <br>
** Save the running configuration from volatile memory (RAM) to non-volatile memory (NVRAM) so that the settings are retained even after a reboot.<br>
*휘발성 메모리(RAM)에서 동작 중인 설정을 비휘발성 메모리(NVRAM)에 저장해, 재부팅해도 설정을 유지<br>
<br>
<br>
![image break](../../Pictur/step4/passwd-15.png) <br>
** finger – Allows querying device information (typically disabled by default for security reasons).<br>
(Only available on actual Cisco routers or advanced simulators like GNS3/EVE-NG.)<br>
*finger : 장비 정보 조회 가능 (보안적으로 기본 차단되어있음)(실제 Cisco 라우터나 GNS3/EVE-NG 같은 고급 시뮬레이터에서만 사용 가능)










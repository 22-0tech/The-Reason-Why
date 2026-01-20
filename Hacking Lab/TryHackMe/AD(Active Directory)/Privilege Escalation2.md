![image 1](/Pictur/Hacking%20lab/AD/privesc/1.png)<br>
The second approach will attempt privilege escalation using all methods provided by TryHackMe.<br>
두 번째는 Tryhackme에서 제공하는 모든 방법대로 권한상승을 시도하겠습니다.

<br>
<br>
<br>
<br>
<br>
<br>

* accesschk.exe 1
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/privesc2/1.png)<br>

<br>

![image 2](/Pictur/Hacking%20lab/AD/privesc2/2.png)<br>
The /accepteula option automatically accepts pop-up prompts during the attack.<br>
The -uwcqv options represent: -u (ignore errors), -w (write permission), -c (service), -q (quiet mode), and -v (verbose).<br>
The Discretionary Access Control List (DACL), which is applied to all files in Windows, is analyzed to identify vulnerabilities.<br>
A misconfiguration in the target service settings is identified.<br>

/accepteula : 공격 시 팝업 자동 수락<br>
-uwcqv (u:오류 무시, -w:쓰기 권한, -c: 서비스, -q:조용히, -v: 상세)<br>
윈도우의 모든 파일에 붙는 계정 목록인 DACL을 약점을 찾겠습니다. 해당 서비스의 설정 변경을 발견했습니다. <br>
<br>
<br>
<br>
<br>
<br>
<br>


![image 3](/Pictur/Hacking%20lab/AD/privesc2/3.png)<br>
The daclsvc service information will be examined.<br>
If the service is manipulated while running as LocalSystem, the highest level of privileges can be obtained.<br>
daclsvc 서비스 정보 확인을 하겠습니다. LocalSystem으로 서비스 조작했을 때 최고 권한을 얻을 수 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 4](/Pictur/Hacking%20lab/AD/privesc2/4.png)<br>
Based on the above CHANGE_CONFIG, the file path is configured to point to malware.<br>
위의 CHANGE_CONFIG대로 파일 경로를 악성코드로 설정하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 5](/Pictur/Hacking%20lab/AD/privesc2/5.png)<br>
After executing the malware, the activated ports will be examined.<br>
악성코드 실행 후 활성화된 포트를 보겠습니다. 
<br>
<br>
<br>
<br>
<br>


![image 5](/Pictur/Hacking%20lab/AD/privesc2/5-3.png)<br>
After the shell was opened, the superuser was confirmed.<br>
쉘이 열리면서 최고 관리자를 확인했습니다. 
<br>
<br>
<br>
<br>
<br>
<br>
<br>

* accesschk.exe 2
<br>

<br>
<br>
<br>

![image 6](/Pictur/Hacking%20lab/AD/privesc2/6-0.png)<br>
Current user privileges.<br>
현재 권한입니다.
<br>
<br>
<br>
<br>
<br>

![image 6](/Pictur/Hacking%20lab/AD/privesc2/6.png)<br>
In this case, the service uses an unquoted service path.<br>
For example, if C:\Program Files\Unquoted Path Service\Common Files\service.exe is the legitimate executable,<br>
Because the service path is unquoted, the malware at C:\Program Files\Unquoted Path Service\Common.exe<br>
is executed before the legitimate service binary.<br>

이번엔 따옴표가 없는 서비스 경로입니다. 예를 들어, C:\Program Files\Unquoted Path Service\Common Files\service.exe 이게 원래 실행 파일이면<br>
C:\Program Files\Unquoted Path Service\Common.exe(Malware) 앞에 있는 악성 코드를 먼저 실행하게 됩니다. 따옴표가 없기 때문입니다.

<br>
<br>
<br>
<br>
<br>


![image 7](/Pictur/Hacking%20lab/AD/privesc2/7.png)<br>
Read and write permissions are granted for the specified path.<br>
해당 경로에 읽고 쓰기 가능한 권한이 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 8](/Pictur/Hacking%20lab/AD/privesc2/8.png)<br>
The malware (reverse.exe) is placed at the Common.exe path.<br>
Common.exe라는 경로에 악성코드(reverse.exe)를 설정합니다.
<br>
<br>
<br>
<br>
<br>

![image 9](/Pictur/Hacking%20lab/AD/privesc2/9.png)<br>
After execution, the shell will be checked.<br>
실행 후 쉘을 확인하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 5](/Pictur/Hacking%20lab/AD/privesc2/5-3.png)<br>
When the shell was opened, privileges were escalated to the superuser level.<br>
쉘이 열리면서 최고 관리자 권한으로 상승했습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* accesschk.exe 3
<br>
<br>
<br>
<br>

![image 11](/Pictur/Hacking%20lab/AD/privesc2/11.png)<br>
This time, the registry permission service will be checked.<br>
이번엔 레지스트리 권한 서비스를 확인하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 12](/Pictur/Hacking%20lab/AD/privesc2/12.png)<br>
This is the actual location within the Windows Registry where the configuration information for a specific service is stored.<br>
All actions are permitted on this key.<br>

윈도우 레지스트리 내에서 특정 서비스의 설정 정보가 저장되는 실제 위치입니다. 해당 키에 모든 행위를 허용한다고 합니다.
<br>
<br>
<br>
<br>
<br>

![image 13](/Pictur/Hacking%20lab/AD/privesc2/13.png)<br>
After placing the malware at the specified path, the regsvc service will be started.<br>
해당 경로에 악성코드를 설정 후 regsvc를 시작하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 5](/Pictur/Hacking%20lab/AD/privesc2/5-3.png)<br>
The shell opened and confirmed execution with elevated administrator privileges.<br>
쉘이 열리면서 최고 관리자 권한을 확인했습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

* accesschk.exe 4
<br>
<br>
<br>
<br>
<br>
<br>

![image 15](/Pictur/Hacking%20lab/AD/privesc2/15.png)<br>
This time, the executable permission service will be examined.<br>
이번에는 실행 파일 권한 서비스를 보겠습니다. 
<br>
<br>
<br>
<br>
<br>

![image 16](/Pictur/Hacking%20lab/AD/privesc2/16-1.png)<br>
The file is accessible to all users.<br>
모든 유저가 파일에 접근이 가능합니다.
<br>
<br>
<br>
<br>
<br>

![image 17](/Pictur/Hacking%20lab/AD/privesc2/17.png)<br>
The malware (reverse.exe) will be copied to the specified file.<br>
해당 파일에 악성코드(reverse.exe)를 복사하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 18](/Pictur/Hacking%20lab/AD/privesc2/18.png)<br>
After the configuration is completed, the filepermsvc service will be started.<br>
설정 후, filepermsvc를 시작하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 5](/Pictur/Hacking%20lab/AD/privesc2/5-3.png)<br>
The shell opened with elevated administrator privileges.<br>
쉘이 열리면서 최고 관리자 권한을 획득했습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* accesschk.exe 5
<br>
<br>
<br>
<br>

![image 19](/Pictur/Hacking%20lab/AD/privesc2/19.png)<br>
The registry storing the auto-run settings will be checked.<br>
자동 실행 설정이 저장된 레지스트를 조회하겠습니다.
<br>
<br>
<br>
<br>
<br>


![image 20](/Pictur/Hacking%20lab/AD/privesc2/20.png)<br>
![image 21](/Pictur/Hacking%20lab/AD/privesc2/21.png)<br>
The retrieved file has read and write permissions enabled.<br>
조회된 파일에 읽고 쓸 수 있는 권한이 허용되고 있습니다.
<br>
<br>
<br>

![image 22](/Pictur/Hacking%20lab/AD/privesc2/22.png)<br>
The executable at that path was replaced by a malicious program (reverse.exe) instead of program.exe.<br>
해당 경로에 program.exe 대신 악성코드(reverse.exe)로 복사했습니다.
<br>
<br>
<br>
<br>
<br>

![image 22](/Pictur/Hacking%20lab/AD/privesc2/22-0.png)<br>
An RDP connection will be established.<br>
rdp접속을 하겠습니다.
<br>


![image 22](/Pictur/Hacking%20lab/AD/privesc2/22-1.png)<br>
Administrator privileges were successfully obtained.<br>
관리자 권한 확보에 성공했습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* AlwaysInstallElevated
<br>
<br>
<br>
<br>

![image 23](/Pictur/Hacking%20lab/AD/privesc2/23.png)<br>
Using reg query, check the Installer policies that always allow elevated installation in two locations: user level (HKCU) and system level (HKLM).<br>
It is possible to attack using impersonal hexadecimal 0x1 and 1 with all permissions allowed.<br>

reg query를 이용해 항상 최고 권한으로 설치를 진행하는 Insatller 정책 두 곳을 확인합니다. 사용자 수준(HKCU) & 시스템 수준(HKLM)<br>
0x1 16진수 1로 모두 허용으로 공격이 가능합니다. 
<br>
<br>
<br>
<br>
<br>

![image 24](/Pictur/Hacking%20lab/AD/privesc2/24-4.png)<br>
AlwaysInstallElevated applies only to MSI packages. A reverse shell payload is generated with the .msi extension.<br>
AlwaysInstallElevated는 MSI 형식만 적용이 가능합니다. 확장자 msi로 리버스 쉘 페이로드를 생성합니다. 
<br>
<br>
<br>
<br>
<br>
<br>

![image 25](/Pictur/Hacking%20lab/AD/privesc2/253.png)<br>
An MSI file is executed via msiexec, after which SYSTEM-level privileges are obtained.<br>
확장자 msi 파일을 msiexec를 이용해 실행합니다. 실행 후 윈도우 최고 권한을 획득했습니다.
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
* Password Registry<br>
<br>
<br>
<br>

![image 25](/Pictur/Hacking%20lab/AD/privesc2/26.png)<br>
A comprehensive search is performed in HKLM (system level), including all subkeys (/s), to find the string "password"<br>
HKLM(시스템 수준)에서 하위 폴더(/s)까지 전수 조사로 password라는 글자를 찾습니다.  
<br>
<br>
<br>
<br>
<br>

![image 27](/Pictur/Hacking%20lab/AD/privesc2/.27.png)<br>
This registry path corresponds to the Windows Login Manager (Winlogon), where login traces can be identified.<br>
The last logged-in user can be confirmed as admin.<br>
However, since AutoAdminLogon is set to 0, automatic logon is disabled and the password is entered manually at login, 
so it is not stored in the registry. In this case, an attempt can be made to log in using a common password such as password123.<br>

이 레지스트리의 경로는 윈도우의 로그인 매니저(winlogon)으로 로그인 흔적을 확인할 수 있습니다. 마지막 로그인을 admin을 알 수 있습니다.<br>
하지만, AutoAdminLogon에 0으로 자동 로그인 없이 비밀번호를 수동으로 입력해 로그인하기 때문에 레지스트리에 저장하지 않습니다.<br>
이럴 경우 흔한 비밀번호 password123으로 로그인을 시도해볼 수 있습니다.<br>
<br>
<br>
<br>
<br>
<br>

![image 28](/Pictur/Hacking%20lab/AD/privesc2/28.png)<br>
An interactive Windows shell can be attempted using impacket-psexec. SYSTEM-level privileges are successfully obtained.<br>
impacket-psexec로 윈도우 대화형 쉘을 시도할 수 있습니다. 시스템 최고 권한 획득에 성공했습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* Run as<br>
<br>
<br>

![image 29](/Pictur/Hacking%20lab/AD/privesc2/29.png)<br>
Stored credentials can be identified by checking the accounts listed using cmdkey /list.<br>
cmdkey /list로 비밀번호가 저장되어 있는 계정을 확인할 수 있습니다.<br>
<br>
<br>
<br>
<br>
<br>

![image 30](/Pictur/Hacking%20lab/AD/privesc2/30.png)<br>
The previously successful admin account can be added.<br>
앞서 로그인에 성공한 admin 계정을 추가할 수 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 31](/Pictur/Hacking%20lab/AD/privesc2/31.png)<br>
Using the stored credentials, a malicious executable (reverse.exe) is executed via runas.<br>
저장되어 있는 자격으로 runas를 통해 악성코드(reverse.exe)를 실행합니다.
<br>
<br>
<br>
<br>
<br>

![image 32](/Pictur/Hacking%20lab/AD/privesc2/32.png)<br>
A shell is opened, and an admin shell is obtained using the corresponding credentials.<br>
쉘이 열리고 자격대로 admin 쉘을 획득했습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* SAM<br>

<br>
<br>
<br>
<br>
<br>

![image 34](/Pictur/Hacking%20lab/AD/privesc2/34.png)<br>
A Samba server is launched using the known user account user.<br>
알고 있는 계정 user로 samba 서버를 실행합니다.
<br>
<br>
<br>
<br>
<br>

![image 35](/Pictur/Hacking%20lab/AD/privesc2/35.png)<br>
On the Windows side, legitimate credentials are registered using net use to establish a secure connection.<br>
The SAM and SYSTEM files are copied in order to extract password hashes for all Windows accounts.<br>

윈도우 쪽에서는 net use를 통해 정당한 자격증명을 등록해서 안전하게 연결을 맺습니다.<br>
*WHY - SAM과 SYSTEM을 복사합니다. 윈도우 모든 계정의 비밀번호 해시를 훔치기 위함입니다. 

<br>
<br>
<br>
<br>
<br>

![image 36](/Pictur/Hacking%20lab/AD/privesc2/36.png)<br>
Password hashes can be extracted from the SYSTEM and SAM files using pwdump.py from the creddump7 toolkit.<br>
creddump7 툴킷의 pwdump.py을 이용해 SYSTEM, SAM의 파일을 해시로 추출할 수 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 37](/Pictur/Hacking%20lab/AD/privesc2/37.png)<br>
Among the NTLM hashes, the NT portion is the value actually used and can be cracked to plaintext using Hashcat module 1000.<br>
NTLM의 해시 중 뒤의 NT가 실제 이용되는 값으로 hashcat 모듈 1000을 이용해 평문으로 해독할 수 있습니다. 
<br>
<br>
<br>
<br>
<br>

![image 38](/Pictur/Hacking%20lab/AD/privesc2/38.png)<br>
The Administrator password is successfully recovered in plaintext.<br>
Administrator의 비밀번호를 평문으로 해독했습니다.
<br>
<br>
<br>
<br>
<br>

![image 39](/Pictur/Hacking%20lab/AD/privesc2/39.png)<br>
SYSTEM-level privileges are successfully obtained using the cracked admin credentials.<br>
해독한 admin 로그인으로 시스템 권한 획득에 성공했습니다.
<br>
<br>
<br>
<br>
<br>

![image 40](/Pictur/Hacking%20lab/AD/privesc2/40.png)<br>
All successfully cracked hashes can be listed using the --show option.<br>
--show를 이용해 해독에 성공한 해시들을 전부 조회할 수 있습니다. 
<br>
<br>
<br>
<br>
<br>

![image 41](/Pictur/Hacking%20lab/AD/privesc2/41.png)<br>
SYSTEM-level privileges are successfully obtained using the cracked admin credentials.<br>
해독한 admin 로그인으로 시스템 권한 획득에 성공했습니다
<br>
<br>
<br>
<br>
<br>

<br>
<br>

![image 42](/Pictur/Hacking%20lab/AD/privesc2/42.png)<br>
Although password cracking was successful, <br>
login attempts failed: the user account lacked sufficient privileges, and the Administrator account was disabled.<br>

비밀번호 해독에 성공했어도 user는 권한 부족, Administrator는 계정 비활성화로 로그인에 실패했습니다.
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
* Pass the Hash<br>
<br>
<br>

![image 43](/Pictur/Hacking%20lab/AD/privesc2/43.png)<br>
The admin account successfully authenticated, <br>
and login was possible using the NT hash value employed for password authentication without cracking it to plaintext.<br>

admin은 로그인에 성공했는데 비밀번호에 이용되는 NT 해시값만만으로 해독 없이 로그인이 가능합니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* Scheduled Tasks<br>
<br>
<br>

![image 44](/Pictur/Hacking%20lab/AD/privesc2/44.png)<br>
In practice, there are cases where folders such as DevTools exist for operational convenience.<br>
These are reported to be executed every minute with the highest Windows operating system privileges (SYSTEM).<br>
A scenario can be considered in which a malicious executable (reverse.exe) is run in place of the script that is executed every minute.<br>

실무에서 업무 편의를 위해 DevTools 같은 폴더가 있는 경우가 있습니다. 매 분마다 윈도우 운영체제 최고 권한 시스템으로 실행한다고 합니다.<br>
1분 마다 실행되는 스크립트 대신에 악성코드(reverse.exe)를 실행하는 시나리오를 생각해볼 수 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 45](/Pictur/Hacking%20lab/AD/privesc2/.45.png)<br>
There is permission to append content using the >> operator and to write file contents.<br>
Malicious code (reverse.exe) will be appended using the >> operator.<br>

기존 내용에 >> 연산자를 통해 내용 추가와 파일 내용 작성하는 권한이 있습니다.<br>
' >> '을 통해 악성코드(reverse.exe)를 추가하겠습니다. 
<br>
<br>
<br>
<br>
<br>

![image 46](/Pictur/Hacking%20lab/AD/privesc2/46.png)<br>
System privileges were obtained when a prompt was opened by malware executed every minute.<br>
1분 마다 실행되는 악성코드를 통해 프롬포트가 열리면서 시스템 권한을 획득했습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* Insecure GUI Apps<br>
<br>
<br>

![image 48](/Pictur/Hacking%20lab/AD/privesc2/48.png)<br>
An administrator Paint application (adminpaint) is located on the desktop. Privilege escalation can be performed through this GUI application.<br>
바탕화면에 adminpaint 관리자 그림판이 있습니다. 이 GUI App을 통해 권한 상승을 할 수 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 47](/Pictur/Hacking%20lab/AD/privesc2/99.png)<br>
After launching Paint, it can be observed that the account changes from user to admin.<br>
그림판 실행 후 user에서 admin으로 계정이 바뀐 걸 볼 수 있습니다.
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

![image 51](/Pictur/Hacking%20lab/AD/privesc2/50.png)<br>
Privilege escalation can be attempted by directly accessing the Paint application.<br>
직접 그림판에 가서 권한상승을 시도해볼 수 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 51](/Pictur/Hacking%20lab/AD/privesc2/51.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 52](/Pictur/Hacking%20lab/AD/privesc2/52.png)<br>
Both methods failed to execute.<br>
두 방법 모두 실행에 실패했습니다.
<br>
<br>
<br>
<br>
<br>

![image 47](/Pictur/Hacking%20lab/AD/privesc2/101.png)<br>
A Command Prompt window will be opened via a right-click.<br>
여기서 우클릭을 통해 cmd 창을 띄우겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 47](/Pictur/Hacking%20lab/AD/privesc2/100.png)<br>
When the Command Prompt was executed through the Paint application, privilege escalation to admin was successful.<br>
However, when the Command Prompt was launched simply via File Explorer, it ran under the user login session.<br>

그림판을 통해서 cmd를 실행했을 때 admin으로 권한 상승에 성공했습니다.<br>
단순히, 탐색기를 통해 cmd를 실행하면 로그인 세션 user로 나옵니다.
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

* Start Apps(From a real attacker’s perspective.)

<br>
<br>

![image 53](/Pictur/Hacking%20lab/AD/privesc2/53.png)<br>
Permissions on the Start Menu path were checked using accesschk.exe, and read and write permissions for a standard user were confirmed.<br>
accesschk.exe를 통해 시작메뉴 경로에 권한을 확인합니다. 일반 사용자 읽고, 쓰기 권한을 확인했습니다. 
<br>
<br>
<br>
<br>
<br>
![image 54](/Pictur/Hacking%20lab/AD/privesc2/..102.png)<br>
Assuming a real-world scenario, the attacker creates the two files mentioned above. <br>
CreateShortCut is a script used to install a .lnk (shortcut) file.<br>

실제 상황이라고 가정할 때, 공격자는 위에 두 개 파일을 생성합니다.<br>
CreateShortCut으로 .lnk(바로가기)를 설치하는 스크립트입니다.
<br>
<br>
<br>
<br>
<br>

![image 54](/Pictur/Hacking%20lab/AD/privesc2/54.png)<br>
cscript is an engine used to execute VBScript and JScript. It installs a .lnk (shortcut) icon.<br>
csript는 VBScript JScript를 실행하는 엔진입니다. .lnk (바로가기) 아이콘을 설치합니다. 
<br>
<br>
<br>
<br>
<br>

![image 54](/Pictur/Hacking%20lab/AD/privesc2/103.png)<br>
Malicious code (reverse.lnk) has been installed.<br>
악성코드(reverse.lnk)가 설치되었습니다.
<br>
<br>
<br>
<br>
<br>

![image 54](/Pictur/Hacking%20lab/AD/privesc2/104.png)<br>
In a real-world scenario, the left side represents the attacker opening a port and waiting.<br>
On the right, a scenario is assumed in which the victim PC is logged into as a server administrator.<br>

실제 상황이라면, 왼쪽은 공격자가 포트를 열고 기다립니다.<br>
오른쪽은 피해PC 서버 관리자로 로그인하는 상황을 가정합니다.  
<br>
<br>
<br>
<br>
<br>

![image 54](/Pictur/Hacking%20lab/AD/privesc2/105.png)<br>
The administrator logs into the system.<br>
관리자가 로그인합니다.
<br>
<br>
<br>
<br>
<br>

![image 54](/Pictur/Hacking%20lab/AD/privesc2/106.png)<br>
<br>
When the administrator logs in, the attacker’s waiting Command Prompt opens, resulting in the acquisition of administrative privileges.<br>
관리자가 로그인 하면 기다리고 있던 공격자의 프롬포트가 열리면서 admin 관리자 권한을 획득합니다. 
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
<br>
<br>

* Token Impersonation
<br>
<br>

![image 59](/Pictur/Hacking%20lab/AD/privesc2/59-1.png)<br>
The RoguePotato attack requires intercepting Windows RPC communication (port 135).<br>
Incoming traffic to port 135 on Kali must be forwarded (tunneled) to port 9999 on the Windows system.<br>

RoguePotato 공격은 윈도우의 RPC(P:135) 통신을 가로채야합니다.<br>
kali 135번 포트로 들어오는 통신을 윈도우 9999 포트로 포워딩(통로)을 해야합니다.
<br>
<br>
<br>
<br>
<br>

![image 58](/Pictur/Hacking%20lab/AD/privesc2/58.png)<br>
PSExec64 is a tool that executes programs under the privileges of a specified account.<br>
The malicious code (reverse.exe) will be executed with low privileges as the Local Service account.<br>
WHY – The Potato attack is an attack technique that escalates privileges from a low-privileged context to a high-privileged one through token impersonation.<br>

PSExec64는 특정 계정의 권한으로 프로그램을 실행해주는 도구입니다. Local service라는 낮은 권한으로 악성코드(reverse.exe)를 실행하겠습니다.<br>
*WHY - Potate Attack은 낮은 권한에서 토큰 사칭을 통해 높은 권한으로 상승하는 공격 
<br>
<br>
<br>
<br>
<br>

![image 60](/Pictur/Hacking%20lab/AD/privesc2/60.png)<br>
RoguePotato.exe lures an account with SYSTEM privileges and executes the malicious file (reverse.exe) using the -e option.<br>
It then activates port 9999 on the Windows system.<br>

RoguePotate.exe가 시스템 권한을 가진 계정을 낚아서 -e로 악성파일(reverse.exe) 실행하며, 윈도우의 9999번 포트 활성화합니다.
<br>
<br>
<br>
<br>
<br>

![image 61](/Pictur/Hacking%20lab/AD/privesc2/61.png)<br>
A Command Prompt opened on the waiting port, resulting in the acquisition of SYSTEM privileges.<br>
기다리고 있던 포트에서 프롬포트가 열리면서 시스템 권한을 획득했습니다.
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
* Token Impersonation<br>
<br>
<br>

![image 62](/Pictur/Hacking%20lab/AD/privesc2/.62.png)<br>
This time, token impersonation will be carried out using PrintSpoofer.exe.<br>
이번엔 PrintSpoofer.exe를 통해 토큰 사칭을 하겠습니다. 낮은 권한 local service에서 상승을 시도합니다.
<br>
<br>
<br>
<br>
<br>

![image 63](/Pictur/Hacking%20lab/AD/privesc2/63.png)<br>
After the port is activated, waiting will commence.<br>
포트 활성화 후 기다리겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 64](/Pictur/Hacking%20lab/AD/privesc2/64.png)<br>
The Print Spooler service operates with SYSTEM privileges.<br>
PrintSpoofer.exe induces the Print Spooler service to establish a fake printer connection.<br>

Print Spooler 서비스는 SYSTEM 권한으로 작동합니다.<br>
PrintSpoofer.exe는 Print Spooler 서비스에게 가짜 프린터 연결을 유도합니다.
<br>
<br>
<br>
<br>
<br>

![image 65](/Pictur/Hacking%20lab/AD/privesc2/65.png)<br>
Privilege escalation to SYSTEM privileges was successfully achieved.<br>
SYSTEM 권한으로 권한상승에 성공하였습니다.
<br>
<br>
<br>
<br>
<br>

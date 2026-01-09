![image 1](/Pictur/Hacking%20lab/AD/privesc/1.png)<br>
The second method will be to perform privilege escalation following the standard approach provided by TryHackMe.<br>
두 번째 방법은 Tryhackme에서 제공하는 힌트대로 권한상승을 하겠습니다.

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

![image 16](/Pictur/Hacking%20lab/AD/privesc2/16.png)<br>
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
<br>
<br>

![image 23](/Pictur/Hacking%20lab/AD/privesc2/23.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 24](/Pictur/Hacking%20lab/AD/privesc2/24.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 25](/Pictur/Hacking%20lab/AD/privesc2/25.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 26](/Pictur/Hacking%20lab/AD/privesc2/26.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 27](/Pictur/Hacking%20lab/AD/privesc2/27.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 28](/Pictur/Hacking%20lab/AD/privesc2/28.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 29](/Pictur/Hacking%20lab/AD/privesc2/29.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 30](/Pictur/Hacking%20lab/AD/privesc2/30.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 31](/Pictur/Hacking%20lab/AD/privesc2/31.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 32](/Pictur/Hacking%20lab/AD/privesc2/32.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 33](/Pictur/Hacking%20lab/AD/privesc2/33.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 34](/Pictur/Hacking%20lab/AD/privesc2/34.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 35](/Pictur/Hacking%20lab/AD/privesc2/35.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 36](/Pictur/Hacking%20lab/AD/privesc2/36.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 37](/Pictur/Hacking%20lab/AD/privesc2/37.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 38](/Pictur/Hacking%20lab/AD/privesc2/38.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 39](/Pictur/Hacking%20lab/AD/privesc2/39.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 40](/Pictur/Hacking%20lab/AD/privesc2/40.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 41](/Pictur/Hacking%20lab/AD/privesc2/41.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 42](/Pictur/Hacking%20lab/AD/privesc2/42.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 43](/Pictur/Hacking%20lab/AD/privesc2/43.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 44](/Pictur/Hacking%20lab/AD/privesc2/44.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 45](/Pictur/Hacking%20lab/AD/privesc2/45.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 46](/Pictur/Hacking%20lab/AD/privesc2/46.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 47](/Pictur/Hacking%20lab/AD/privesc2/47.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 48](/Pictur/Hacking%20lab/AD/privesc2/48.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 49](/Pictur/Hacking%20lab/AD/privesc2/49.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 50](/Pictur/Hacking%20lab/AD/privesc2/50.png)<br>
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
<br>
<br>
<br>
<br>
<br>

![image 53](/Pictur/Hacking%20lab/AD/privesc2/53.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 54](/Pictur/Hacking%20lab/AD/privesc2/54.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 55](/Pictur/Hacking%20lab/AD/privesc2/55.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 56](/Pictur/Hacking%20lab/AD/privesc2/56.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 57](/Pictur/Hacking%20lab/AD/privesc2/57.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 58](/Pictur/Hacking%20lab/AD/privesc2/58.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 59](/Pictur/Hacking%20lab/AD/privesc2/59.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 59](/Pictur/Hacking%20lab/AD/privesc2/59-1.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 60](/Pictur/Hacking%20lab/AD/privesc2/60.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 61](/Pictur/Hacking%20lab/AD/privesc2/61.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 62](/Pictur/Hacking%20lab/AD/privesc2/62.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 63](/Pictur/Hacking%20lab/AD/privesc2/63.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 64](/Pictur/Hacking%20lab/AD/privesc2/64.png)<br>
<br>
<br>
<br>
<br>
<br>

![image 65](/Pictur/Hacking%20lab/AD/privesc2/65.png)<br>
<br>
<br>
<br>
<br>
<br>

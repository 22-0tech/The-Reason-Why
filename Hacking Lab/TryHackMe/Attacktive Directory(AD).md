![image 1](/Pictur/Hacking%20lab/attacktivedirectory/1.png)<br>

<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/2.png)<br>
Ports 80, 88, 139, 445, and 3389 are all open. The domain is spookysec.local.<br>
80,88,139,445,3389 모두 열려있습니다. 도메인은 spookysec.local입니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/3.png)<br>
Without SMB signing, communication seems impossible due to security being enforced.<br>
SMB 사인이 없으면 대화 불가로 보안이 적용되어 있습니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/4.png)<br>
Port 80 is active, allowing access to the web.<br>
80번 포트 활성화로 웹에 접속할 수 있습니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/5.png)<br>
When ports 139 and 445 are active, enum4linux can be used to enumerate shared folders, user accounts, group information, and password policies from the SMB service.<br>
The domain controller's name and the SID for a possible Golden Ticket attack can be identified.<br>

139,445 포트가 활성화 되어 있을 때 enum4linux를 이용해 SMB 서비스의 공유 폴더, 사용자 계정, 그룹 정보 및 패스워드 정책 열거가 가능합니다.<br>
도메인 컨트롤의 이름과 골든 티켓 공격이 가능한 Sid를 확인할 수 있습니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/6.png)<br>
The server identity and user account extraction through SMB are blocked.<br>
SMB를 통한 서버 신원, 사용자 계정 추출이 모두 막혀있습니다.
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/7.png)<br>
The password policy enumeration also failed.<br>
비밀번호 정책 또한 실패했습니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/8.png)<br>
The special account managing the entire domain, krbtgt, has been identified, confirming the domain controller (DC).<br>
도메인 전체를 관리하는 특수 계정을 확인했습니다. krbtgt로 도메인 컨트롤러(DC)임을 확인이 가능합니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/9.png)<br>
Since further progress is difficult without the password, a valid account is needed through kerbrute. 
The User List provided by TryHackMe was used.<br>

비밀번호 없이 더 이상의 진전은 어렵기 때문에, kerbrute를 통한 유효한 계정이 필요합니다.<br>
TryHackMe에서 제공된 User List를 사용했습니다.

<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/10.png)<br>
With the found account, GetNPUsers is used to steal the hash values and attempt to find the password without directly accessing it.<br>
찾은 계정으로 비밀번호 없이 GetNPUsers를 이용해 해시값을 훔쳐 비밀번호를 찾겠습니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/11.png)<br>
The hash values were cracked using John the Ripper, successfully revealing the password.<br>
john을 이용해 해시값을 crack해 비밀번호를 찾았습니다. 
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/12.png)<br>
Since the svc-admin account is fully known, the SMB share list is queried.<br>
svc-admin 계정을 완벽히 알고 있기 때문에 smb 공유 리스트를 조회합니다. 
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/13.png)<br>
The credential file was found in the shared folder backup.<br>
공유 폴더 backup에서 자격증명 파일을 확인했습니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/14.png)<br>
The base64-encoded string is decoded.<br>
base64로 인코딩된 문자열을 디코딩합니다. 
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/15.png)<br>
The backup account is a special account with access to the NTDS.dit file.<br>
Using secretsdump, all user password hashes can be extracted from the domain controller.<br>

backup은 NTDS.dit 파일에 접근 가능한 특수 계정입니다.<br>
secretsdump를 이용해 도메인 컨트롤러 내의 모든 사용자 비밀번호 해시를 추출할 수 있습니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/16.png)<br>
The Administrator's NTLM hash has been obtained.<br>
With a Pass the Hash attack, remote access to the target system can be achieved with Administrator privileges, without the need to crack the password.<br>

Administrator의 NTLM해시까지 확보한 상태입니다.<br>
'Pass the Hash'공격을 통해 비밀번호 크래킹 없이 Administrator 권한으로 대상 시스템의 원격 접속이 가능합니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/17.png)<br>
All flags, including the Administrator flag, have been successfully obtained.<br>
Administrator를 포함한 모든 flag를 획득했습니다. 
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/18.png)<br>

<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/19.png)<br>

<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/attacktivedirectory/20.png)<br>
Access to the GUI environment beyond the shell can be attempted.<br>
셸 환경을 넘어 GUI 환경까지 접속 시도해볼 수 있습니다. 

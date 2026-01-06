![image 1](/Pictur/Hacking%20lab/AD/template/1.png)<br>
It can be inferred that the room name is a certificate template,<br>
and that the attack involves forging a certificate to obtain administrator privileges.<br>

Room이름이 인증서 템플릿입니다. 인증서를 위조해서 관리자 권한을 탈취하는 방향으로 추측이 가능합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/2.png)<br>

It begins with remote access via RDP using a domain account.<br>
시작은 도메인 계정을 통해 rdp 원격 접속으로 시작합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/3.png)<br>
Remote access is initiated.<br>
원격 접속 실행합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/4.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/5.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/5-1.png)<br>
Initially, a THM account is provided, and there is a THM tools folder.<br>
처음에 thm 계정이 주어졌는데, THM 도구 폴더가 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/5-2.png)<br>
Rubeus is present, which strongly suggests that Kerberos attacks are being addressed.<br>
Rubeus가 있습니다. 커버로스 공격을 다루는 걸 강력하게 추론할 수 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/5-3.png)<br>
Given that the title is AD Certificate Templates, it follows the standard flow of the AD CS vulnerability attack ESC1 technique, first using certutil.<br>
제목이 AD 인증서 템플릿인 만큼, AD CS 취약점 공격 ESC1 기법의 정석적인 흐름으로 certutil을 먼저 이용합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/5-4.png)<br>
To verify whether a certificate can be used, the Allow Enroll permission must first be identified,<br>
as even if a vulnerability exists, it may not be usable.<br>
Since the permissions are limited to READ only, the approach moves on to the next direction.<br>

인증서 사용 가능 여부를 확인하기 위해 Allow Enroll을 먼저 찾아야합니다. 취약점이 존재해도 사용하지 못할 가능성이 있습니다.<br>
권한 또한 READ밖에 없기 때문에 다음 방향으로 넘어갑니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/6.png)<br>
A certificate will be generated in order to utilize Rubeus.<br>
Rubeus 활용을 위해 인증서 생성을 하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/7.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/8.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/9.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/10.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/11.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/12.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/13.png)<br>
The certificate enrollment is performed.<br>
인증서 등록을 합니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/14.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/15.png)<br>
The process is completed only after the certificate is enrolled and then extracted.<br>
인증서를 등록하고 추출까지 해야 완성입니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/16.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/17.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/18.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/19.png)<br>
A TGT will be requested using Rubeus<br>
Rubeus를 이용해 TGT를 요구하겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/20.png)<br>
A TGT ticket granting administrator privileges has been issued.<br>
관리자 권한을 행사할 수 있는 TGT 티켓이 발급되었습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/20-2.png)<br>
This time, a certificate will be obtained using the aaaa account, and a TGT will be requested.<br>
이번엔 aaaa라는 계정으로 인증서를 받아 TGT를 발급 받아 보겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/20-3.png)<br>
The issuance failed. The reason for the failure will be examined.<br>
발급에 실패했습니다. 실패한 이유를 살펴보겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/20-4.png)<br>
This time, the certificate will be requested using the name gpage.<br>
또 다른 gpage라는 이름으로 발급을 받겠습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/20-5.png)<br>
This time, the TGT ticket was successfully issued.<br>
이번엔 TGT 티켓 발급에 성공했습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/20-6.png)<br>



![image 1](/Pictur/Hacking%20lab/AD/template/20-7.png)<br>
The request succeeded because the certificate account name was created using a user that exists in the domain.<br>
*WHY-인증서 계정 이름을 만들 때 도메인에 존재하는 유저로 만들었기 때문에 성공했습니다.
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/AD/template/20-1.png)<br>
The initial ticket could be issued because a user named svc.gitlab exists in the domain.<br>
처음에 티켓이 발급될 수 있었던 이유는 svc.gitlab이라는 유저가 존재했기 때문입니다. 
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/22.png)<br>
The master key (TGT) will be checked using klist to confirm it was received correctly.<br>
klist로 마스터키(TGT)가 제대로 들어왔는지 확인하겠습니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/23.png)<br>
The password of one of the existing users will be changed.<br>
존재하는 유저 중 한 유저의 비밀번호를 변경하겠습니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/24.png)<br>


<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/24-1.png)<br>
The password change failed because the identity of the logged-in session was strictly verified.<br>
로그인된 세션의 신분을 엄격하게 따져 변경에 실패했습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/25-1.png)<br>
It will be executed in PowerShell using the injected Kerberos ticket.<br>
주입된 커버로스 티켓을 통해 PowerShell에서 실행하겠습니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/.25.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/26.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/.27.png)<br>
The administrator folder was accessed, and the penetration testing flag was successfully obtained.<br>
관리자 폴더로 이동해 모의해킹의 flag까지 획득했습니다.

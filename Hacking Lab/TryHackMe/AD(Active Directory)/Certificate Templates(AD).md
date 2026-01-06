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
제목이 AD 인증서 템플릿인 만큼, AD CS취약점 공격 ESC1기법의 정석적인 흐름으로 certutil을 먼저 이용합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/5-4.png)<br>

scp를 이용해 리눅스에서 파일을 원활하게 봅니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/6.png)<br>

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

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/20.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/21.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/22.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AD/template/23.png)<br>

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

![image 1](/Pictur/Hacking%20lab/AD/template/25.png)<br>

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

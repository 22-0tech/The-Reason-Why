![image 1](/Pictur/Hacking%20lab/owasp/injection/bac/1.png)<br>
Among the OWASP Top 10, it is the highest-ranked issue: Broken Access Control, which refers to the misuse of unauthorized privileges.<br>
OWASP TOP 10 중 가장 높은 Broken Access Control로, 허용되지 않은 권한 오용입니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/bac/2.png)<br>

When the target IP received after starting the machine is searched in a web browser,<br>
the following page is displayed. An account will be created.<br>

머신을 시작하고 받은 대상 IP를 웹페이지에 검색하면 이런 화면이 나옵니다. 계정 생성하겠습니다.
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/bac/3.png)<br>

Login is performed using the created account.<br>
생성한 계정으로 로그인 하겠습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/bac/4.png)<br>

The dashboard page (dashboard.php) displays the created account’s name(gildong) and email(aa-aa.com), as well as the administrator’s email.<br>
생성한 계정의 이름(gildong)과 이메일(aa-aa.com)이 나왔으며, 관리자 이메일까지 나왔습니다. 웹페이지는 dashboard.php로 나옵니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/bac/5.png)<br>

The webpage is accessed by replacing dashboard.php with admin.php.<br>

웹페이지 dashboard.php 대신 admin.php로 바꿔서 검색하겠습니다.<br>
관리자 전용 페이지로, 일반 계정 gildong에서 비인가 접근 수행으로 수직적 권한 상승 취약점을 확인했습니다. 
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
* Burp Suite<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/bac/6.png)<br>

<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/bac/7.png)<br>

<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/owasp/injection/bac/8.png)<br>

<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/bac/9.png)<br>

<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/bac/10.png)<br>

<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/bac/11.png)<br>

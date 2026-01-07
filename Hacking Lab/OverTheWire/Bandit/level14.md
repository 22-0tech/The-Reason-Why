By sending the current password to localhost port 30000, the next password can be obtained.<br>
로컬호스트의 30000번 포트로 현재 비밀번호를 보내면 다음 비밀번호를 얻을 수 있다고 합니다.<br>
<br>
<br>

* Approach 1

![image break](/Pictur/Level14/bandit1.png) <br>
A telnet connection is made to localhost on port 30000, and the current password is entered.<br>
텔넷 로컬호스트 30000번에 연결 후 현재 비밀번호를 입력합니다.<br>
<br>
<br>
<br>
<br>
<br>

* Apprach 2

![image break](/Pictur/Level14/bandit2.png) <br>
Another method is available: the password can be sent using netcat (nc).<br>
또 다른 방법입니다. netcat인 nc로 비밀번호를 보낼 수 있습니다.

**showtext<br>
<br>
<br>
<br>
<br>



(Kali)

![image break](/Pictur/Level25/bandit1.png) <br>
There is a private key to access 26; a connection will be established.<br>
26으로 가는 개인키가 있습니다. 접속하겠습니다.<br>

![image break](/Pictur/Level25/bandit2.png) <br>
The connection was terminated immediately after access. It seems checking the login shell should be the first step.<br>
접속하자마자 끊겼습니다. 로그인 쉘을 확인하는 게 우선인거 같습니다.<br>

![image break](/Pictur/Level25/bandit3.png) <br>
The shell is set to "showtext"; <br>
it is a restricted login script that displays paged text instead of providing an interactive shell. <br>
It is a special shell that prevents entering an interactive bash session.<br>
쉘이 showtext로 되어있는데,<br>
대화형 쉘 대신에 텍스트를 페이징만 보여주는 제한된 로그인 스크립트입니다.<br>
*Key-대화형 쉘인 bash로 진입하지 못하게 하는 특수한 쉘입니다.<br>

![image break](/Pictur/Level25/bandit4.png) <br>
Unlike the bash shell, it is set to "showtext."<br>
bash쉘과 다르게 showtext로 되어있습니다.

![image break](/Pictur/Level25/bandit5.png) <br>
The method is to reduce the terminal length so that the text cannot fit on one screen, <br>
causing it to appear with more. At this point, v can be used to enter the editor.<br>
방법은 터미널의 길이를 줄여서 텍스트가 한 화면에 못 나오게 한 후, more로 나오게 하는 것입니다. <br>
이때, v로 편집기에 들어갈 수 있습니다.<br>

![image break](/Pictur/Level25/bandit6.png) <br>
The shell can be changed to bash.<br>
쉘 설정을 bash쉘로 변경할 수 있습니다. 

![image break](/Pictur/Level25/bandit7.png) <br>
After running sh, an interactive shell can be opened to check the password.<br>
sh 실행 후 대화형 쉘을 열고 비밀번호를 확인할 수 있습니다. 

![image break](/Pictur/Level25/bandit8.png) <br>

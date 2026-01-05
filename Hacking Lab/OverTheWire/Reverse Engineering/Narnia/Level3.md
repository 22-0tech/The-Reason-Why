![image break](/Pictur/Level3/nar1.png) <br>

<br>
<br>
<br>

![image break](/Pictur/Level3/nar2.png) <br>
The executable file will be run. A file to run alongside it is needed, and it is said to be sent to /dev/null.<br>
실행 파일을 실행하겠습니다. 같이 실행할 파일이 필요하며 /dev/null로 보낸다고 합니다. 
<br>
<br>
<br>

![image break](/Pictur/Level3/nar4-0.png) <br>
The source code will be examined. The ifile[32] is located right after or near ofile[16].<br>
The ifile is 32 bytes in size, and if argv[1] is longer than this, it will overwrite the contents of the ofile variable.<br>
The attacker wants to read the password file, but since the program sends it to /dev/null, the goal is to manipulate it to send to a readable path instead.<br>
<br>
소스코드를 보겠습니다. ifile[32]는 ofile[16]바로 다음 또는 근처에 위치합니다.<br>
ifile은 32바이트 크기인데, argv[1]이 이보다 길면 ofile변수의 내용을 덮어버리게 됩니다.<br>
공격자는 비밀번호 파일을 읽고싶지만, 프로그램은 /dev/null로 보내기 때문에 읽을 수 있는 경로로 조작하는 것이 목표입니다.
<br>
<br>
<br>
<br>



![image break](/Pictur/Level3/nar3.png) <br>

<br>
<br>
<br>

![image break](/Pictur/Level3/nar4.png) <br>

The input value (ifile) is made extremely long to fill the ifile buffer and overflow into the ofile buffer.<br>
A symbolic link is created to point to the actual password file, /etc/narnia_pass/narnia4, allowing it to be read.<br>
Because the input string is too long, it exceeds the 32-byte size of ifile, and /tmp/out is written in place of the ofile variable.<br>

입력값(ifile)을 아주 길게 만들어서 ifile 영역을 꽉 채우고 ofile 영역까지 침범하게 만듭니다.<br>
심볼릭 링크를 걸어 실제 비밀번호 파일인 /etc/narnia_pass/narnia4가 읽히도록 연결합니다.<br>
입력 문자열이 너무 길어서 ifile의 32바이틀 넘어 /tmp/out이 ofile 변수 위치에 써지게 됩니다.<br>
<br>
<br>
<br>

![image break](/Pictur/Level3/nar5.png) <br>

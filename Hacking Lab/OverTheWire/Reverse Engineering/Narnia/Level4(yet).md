![image break](/Pictur/Level4/nar1.png) <br>


The executable was run, but there was no change. The source code will be examined.<br>
실행 파일을 실행했는데 아무런 변화가 없습니다. 소스코드를 보겠습니다.
<br>
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/Level4/nar2.png) <br>
The buffer size is 256 bytes. The environment variable is large and convenient, but the shellcode can be placed in the space and used.<br>
However, memset initializes the entire space by overwriting it with zeros.<br>
The attacker can inject the attack code only through argv[1].<br>

버퍼 크기는 256바이트입니다. 환경 변수는 넓고 편하나 공간에 쉘코드를 넣어두고 사용하면 됩니다.<br>
하지만, memset이 공간을 전부 0으로 덮어써서 초기화합니다.<br>
공격자는 오직 argv[1]을 통해서만 공격 코드를 주입할 수 있습니다. 

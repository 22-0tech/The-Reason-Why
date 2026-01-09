![image break](/Pictur/Level4/nar1.png) <br>
The Setuid is set to narnia5. Let's take a look at the source code first.<br>
Setuid가 narnia5로 설정되어 있습니다. 소스코드를 먼저 보겠습니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Level4/nar2.png) <br>
irst, memset is examined. When the program is executed, all environment variable strings are set to NULL,<br>
which indicates that environment variable–based attacks are fundamentally blocked.<br>
This indicates that the buffer overflow must be triggered using only argv[1].

memset먼저 보겠습니다.<br>
프로그램이 실행되면 모든 환경변수 문자열을 NULL로 만들기 때문에 환경변수 기반 공격을 원천 차단을 나타냅니다.<br>
argv[1]로만 BOF를 일으켜야함을 나타냅니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Level4/nar3.png) <br>
The return address is checked by entering the GDB environment and using BBBB.<br>
At the end, 42, which represents the character B, can be observed.<br>

gdb 내부로 가서 BBBB로 리턴주소를 확인하겠습니다. 마지막에 B를 나타내는 42가 보입니다. 
<br>
<br>
<br>
<br>

![image break](/Pictur/Level4/nar4.png) <br>
It can be observed that the return address is filled with B.<br>
B로 리턴주소가 점점 채워지는 걸 볼 수 있습니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Level4/nar5.png) <br>
The return address has been completely filled with 0x42424242. The topmost stack memory value is then checked.<br>
0x42424242로 리턴주소가 완전히 채워졌습니다. 최상단 스택 메모리값 확인하겠습니다. 
<br>
<br>
<br>
<br>
<br>
<br>
* 1
<br>

![image break](/Pictur/Level4/nar6.png) <br>
*WHY - To secure sufficient space, the return address is set to 0xffffd4f0 at the beginning.<br>
*WHY - 공간 확보를 위해, 앞부분 0xffffd4f0으로 리턴주소로 설정하겠습니다. 
<br>
<br>
<br>
<br>

![image break](/Pictur/Level4/nar7.png) <br>
Execution was attempted using a 23-byte classic shellcode, but privilege retention failed because the required conditions were not satisfied.<br>
23바이트 클래식 쉘 코드로 실행했지만, 요구 조건을 만족하지 못해 권한 유지에 실패했습니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Level4/nar8.png) <br>
Although a shell was spawned externally, privilege escalation failed due to /bin/sh dropping privileges when executed under setuid.<br>
외부에서도 쉘은 열렸지만,  setuid로 시작되면 권한을 드롭하는 /bin/sh의 문제로 승격에 실패했습니다.
<br>
<br>
<br>
<br>
<br>
<br>
<br>
* 2
<br>

![image break](/Pictur/Level4/nar9.png) <br>
This time, an attempt was made using a 32-byte shellcode designed to induce privilege escalation,<br>
but it failed because it contained a \x00 null byte.<br>

이번엔, 권한상승을 유도하는 32바이트로 시도를 했지만, x00 널 바이트를 포함하고 있어 실패했습니다.

<br>
<br>
<br>
<br>

* 3
<br>
<br>

![image break](/Pictur/Level4/nar10.png) <br>
Even without including any \x00 null bytes in accordance with the narnia4 conditions,<br>
privilege escalation was not achieved because the effective UID could not be preserved until the end.<br>

narnia4 조건에 맞게 x00 널 바이트를 포함하고 있지 않아도, 최종까지 euid를 유지에 실패해 권한 승격에 도달하지 못했습니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Level4/nar11.png) <br>

<br>
<br>
<br>
<br>
<br>
<br>
<br>

* Success
<br>
<br>

![image break](/Pictur/Level4/nar12.png) <br>
It was confirmed that the return address has been completely overwritten.<br>
리턴 주소가 완전히 채워지는 걸 확인했습니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Level4/nar13.png) <br>
The topmost stack memory value is checked.<br>
최상단 스택 메모리값 확인하겠습니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Level4/nar14.png) <br>
To secure sufficient space, the return address is set to 0xffffd4f0.<br>
공간 확보를 위해 0xffffd4f0으로 리턴주소를 설정하겠습니다.
<br>
<br>
<br>
<br>

![image break](/Pictur/Level4/nar15.png) <br>
*WHY - Because it includes (/bin/sh -p), which preserves the effective UID until the end, the narnia5 privileges can be confirmed.<br>
*WHY - 최종까지 euid를 유지하는 (/bin/sh -p) 를 포함하고 있어 narnia5 권한을 확인할 수 있습니다. 


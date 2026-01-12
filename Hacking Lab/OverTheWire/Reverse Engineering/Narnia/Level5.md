*Format String Attack(포맷 스트링 공격)
<br>
<br>
<br>
<br>

![image break](/Pictur/Level5/.nar1.png) <br>


<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/Level5/nar2.png) <br>
If user input argv[1] is used in snprintf instead of format strings like %s or %x, a format string vulnerability arises.<br>
This enables direct memory access through injected format strings.<br>

snprintf에서 포맷 스트링(%s, %x)이 들어갈 자리에 사용자 입력값 argv[1]이 들어가면 직접 포맷 스트링을 주입해 메모리를 쓸 수 있게됩니다. 
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/Level5/nar3.png) <br>
By inserting %x, memory can be examined one word at a time.<br>
Since 41414141 appears when %x is placed after AAAA, it can be confirmed that it is the first argument.<br>

%x를 넣어 메모리를 한 칸씩 볼 수 있습니다. AAAA다음에 %x을 넣어 41414141이 나왔기 때문에 첫 번째 인자임을 확인할 수 있습니다. 
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/Level5/nar4.png) <br>
The objective is to set i to 500. In format string attacks, %n is the only specifier used to write values to memory.<br>
The attacker places the desired address in the position of the first argument and causes snprintf to reference that first argument.<br>
Before setting i to 500, a smaller value of 200 is written first.<br>

i를 500으로 만드는 게 목적입니다. 포맷스트링에서 메모리에 값을 쓰기 위해 %n이 유일하게 사용됩니다.<br>
첫 번째 인자 위치에 공격자가 원하는 주소를 배치하고 snprintf가 1번 인자를 참조하게 합니다. 500을 만들기 전에 보다 작은 값인 200을 먼저 넣습니다.
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/Level5/nar5.png) <br>
WHY – %1$n is used instead of %n because it directly references the first argument without traversing all preceding stack entries.<br>
By combining the 4 bytes of the address value with 496 bytes of padding to make i equal to 500, privilege escalation was successfully achieved.<br>

*WHY - 여기서 %n대신 %1\$n을 사용하는 이유는 앞에 있는 모든 스택을 참조할 필요 없이 1번 인자만 바로 참조합니다.<br>
주소값 4바이트와 496바이트를 합쳐 i를 500을 만듬으로써 권한 상승에 성공했습니다. 

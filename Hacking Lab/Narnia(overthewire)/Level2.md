![image break](/Pictur/Level2/nar1.png) <br>
The executable must be run with arguments.<br>
인자와 같이 실행파일을 실행해야 합니다.<Br>
<br>
<br>

![image break](/Pictur/Level2/nar2.png) <br>
The program is configured to terminate immediately if no additional arguments are provided.<br>
argv[1] is the first input value that must be supplied to trigger the overflow.<br>
추가 인자가 없으면 프로그램이 바로 종료되도록 설정되어있습니다.<br>
argv[1]은 오버플로우를 위해 입력해야할 첫 번째 데이터입니다.<br>
<br>
<br>

![image break](/Pictur/Level2/nar3.png) <br>
A breakpoint will be set at the point where the overflow occurs.<br>
오버플로우가 발생하는 지점에서 break을 설정하겠습니다.
<br>
<br>
<br>

![image break](/Pictur/Level2/nar4.png) <br>
After triggering an overflow with 136 bytes of data—8 bytes larger than the buffer size,<br>
the stack memory state will be examined.<br>
버퍼의 크기보다 8바이트 더 큰 136바이트의 데이터로 오버플로우를 발생시킨 뒤<br>
스택 메모리 상태를 확인하겠습니다.<br>
<br>
<br>

![image break](/Pictur/Level2/nar5.png) <br>
The buffer is filled with 136 bytes, which is 8 bytes larger than its size.<br>
버퍼의 크기보다 8바이트 더 큰 136바이트가 채워진 상태입니다.
<br>
<br>
<br>

![image break](/Pictur/Level2/nar6.png) <br>
The return address was set to the target address using 136 bytes, but privilege escalation was not achieved.<br>
136바이트에 맞춰서 중간주소를 리턴주소로 설정했지만, 권한 상승은 시키지 못했습니다.<br>
<br>
<Br>

![image break](/Pictur/Level2/nar7.png) <br>
The buffer size is adjusted again, the shellcode is replaced with one capable of privilege escalation, and the overflow is carried out.<br>
다시 버퍼 크기에 맞춰, 권한상승이 가능한 쉘코드로 변경 후 오버플로우를 진행합니다.<br>

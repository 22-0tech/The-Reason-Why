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

AAAA를 넣었더니 41414141로 buffer의 첫 시작이자 첫 번째 인자가 됩니다.  
<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/Level5/nar4.png) <br>

<br>
<br>
<br>
<br>
<br>

![image break](/Pictur/Level5/nar5.png) <br>


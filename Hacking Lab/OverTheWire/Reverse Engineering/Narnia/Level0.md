**Narnia<br>
<br>
binary exploitation &nbsp;(and reverse engineering)<br>
바이너리 익스플로잇 &nbsp;(및 리버스 엔지니어링)<br>
<Br>
<Br>


![image break](/Pictur/Level0/nar0.png) <br>
<br>
There are two files for each stage.<br>
각 단계마다 두 개 파일이 있습니다. 
<Br>
<br>
<Br>
<Br>

![image break](/Pictur/Level0/nar1.png) <br>
The executable file was run, and it prompted for input, which seems to be read using scanf<br>
It received 'a' as input, displayed 'buf: a', and then terminated.<br>
실행파일을 실행하고 입력하라고 나오는데, scanf로 입력을 받는 거 같습니다.<br>
a를 입력했고, buf: a가 나오고 종료되었습니다.<br> 


![image break](/Pictur/Level0/nar2.png) <br>

<br>
The system's architecture was verified using 'buf'." "It is x86_64 and is little-endian.<br>
buf가 나와 시스템의 아키텍처를 확인했습니다.x86_64로 리틀에디안입니다.<br>

<Br>
<br>
<Br>

![image break](/Pictur/Level0/nar3.png) <br>
According to the script, the allocated memory is 20 bytes, but it receives 24 bytes through scanf.<br>
If 4 bytes of 'val' are filled with deadbeef, the shell is activated.<br>
스크립트를 보면 할당된 메모리는 20바이트이며, scanf를 통해 24바이트를 받습니다.<br>
val은 deadbeef로 4바이트를 채우면 쉘이 활성화 됩니다.<br>



<br>
<Br>
<Br>
<br>

![image break](/Pictur/Level0/narnia.4.png) <br>
<br>
There are two methods.<br>
두 가지 방법입니다.<br>

<Br>

![image break](/Pictur/Level0/nar5.png) <br>

** The Importance of a Router 라우터의 중요성<br>
<br>

Accessing a Router via CLI (Command-Line Interface)라우터 입력 방법<br>


Command-Line Mode (Router CLI)<br>
![image break](../../Pictur/step2/vn.step2.png) <br>






<br>
<br>
<br>

![image break](../../Pictur/step2/vn.step2.1.png) <br>


en: enable<br>
conf t: configure terminal<br>
int f0/1: interface fastethernet0/1<br>
ip add(r) : ip address + IP + MASK<br>
no sh: no shutdown (Activation)<br>
sh ip int br : show ip interface brief<br>
<br>
<br>
<Br>
<Br>



![image break](../../Pictur/step2/vn.step2.2.png)<br>

If you entered the wrong IP<br>
Enter the interface and type no ip add(r)<br>
 
만약 ip를 잘못 입력했다면, 해당 인터페이스 들어가서 no ip addr 입력

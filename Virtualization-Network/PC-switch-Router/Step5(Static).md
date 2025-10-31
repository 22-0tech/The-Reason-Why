** Static Routing 정적라우팅<br>
<br>
<br>


(Packet Tracer)<br>
![image break](../../Pictur/step5/differentnet.1.png)<br>
To enable communication between different networks, a router is used, and routes must be entered into the routing table.
Based on the distance, one side uses a UTP cable, while the other side uses a fiber-optic cable.<br>
서로 다른 대역들의 통신을 위해 라우터를 이용하는데 라우팅 테이블에 경로를 입력해야 합니다.<br>
거리를 보면 한 쪽은 UTP케이블 다른 쪽은 광케이블을 이용합니다. 


![image break](../../Pictur/step5/differentnet.2.png)<br>

![image break](../../Pictur/step5/differentnet.3.png)<br>

![image break](../../Pictur/step5/differentnet.4.png)<br>
<br>
Enter them into each router.<br>
라우터에 각각 입력합니다. 

<br>
<br>
<br>

![image break](../../Pictur/step5/differentnet.5.png)<br>
An IP address can also be assigned to a switch. The default interface is VLAN1.<br>
스위치에도 ip입력을 할 수 있습니다. 기본 인터페이스는 Vlan1입니다.<br>


It is also possible to convert a physical port to a routed port (using the no switchport command).<br>
** However, from this point, the device functions as a router, so routes must be registered in the routing table.<br>
- 물리 포트를 routed port로 변환도 가능(no switch port라는 명령어 이용)<br>
- 단, 이때부터 라우터 역할이므로 테이블 경로 등록해야함.<br>
- <br>
- <br>
-
-
-
-






<br>
<br>
<br>


![image break](../../Pictur/step5/differentnet.6.png)<br>
After configuring the gateway, remote Telnet access can be enabled.<br>
게이트웨이를 입력 후 원격으로 telnet 접속하게 할 수 있습니다. <br>
** login local != login

<br>
<br>
<br>
<br>

![image break](../../Pictur/step5/different-net.7.png)<br>
**For more efficient network management, the two networks on the left can be combined.<br>
네트워크 관리 효율을 위해 왼쪽 두 개 대역을 축약할 수 있습니다. 

![image break](../../Pictur/step5/differentnet.8.png)<br>
<br>
<br>
<br>
<br>



* For reference 참고<br>

*Security 보안

NTP Synchronization: Important for quickly identifying the cause in case of failures.<br>
NTP 동기화: 장애 발생 시 빠른 원인 파악에 중요<br>
Command: ntp server <IP> → Synchronizes the time between the server and the client.<br>
명령어: ntp server IP → 서버와 클라이언트 시간 일치
<br>
<br>
The AUX port is a auxiliary (backup) port. 예비 포트<br>
Switch(config)#line aux 0<br>
Switch(config-line)#transport input/output none 입출력 차단 <br>
Switch(config-line)#no password<br>
Switch(config-line)#exec-timeout 0 1  ← Automatically logs out if there is no input for 1 second.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1초 동안 입력 없으면 자동으로 로그아웃

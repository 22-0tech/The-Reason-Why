*Arp Spoofing<br>
<Br>
<Br>

(diagrams.net)

![image break](../../Pictur/MITM/arp18.png)<br>
This will be regarded as the normal communication route.<br>
이게 정상적인 통신 경로라고 하겠습니다.<br>
<br>
<br>
<br>
<br>

![image break](../../Pictur/MITM/arp19.png)<br>
At the core of a Man-in-the-Middle (MitM) attack,<br>
the attacker forges MAC addresses to intercept communications between the victim and the gateway, functioning as a monitor positioned in the middle.<br>
맨 인 더 미들(Man-in-the-Middle, MitM) 공격의 핵심으로 <br>
공격자가 MAC 주소를 위조해 피해자와 게이트웨이의 양쪽 통신을 가로채 중간에서 감시하는 역할을합니다.<br>

<br>
<br>
<br>
(Kali)


![image break](../../Pictur/MITM/arp2.png) ![image break](../../Pictur/MITM/arp1.png) <br>
The IP on the left is that of the attacker’s PC, and the IP on the right is that of the victim’s PC.<br>
왼쪽이 공격자 PC의 IP이고, 오른쪽이 피해자 PC의 IP입니다.<Br>
<br>
<Br>



![image break](../../Pictur/MITM/arp3.png)<br>
Netdiscover collects IP and MAC addresses within a specified network range.<br>
After configuring eth1, it scans the 10.0.2.0/24 network<br>
netdiscover는 특정 네트워크 대역에서 IP와 MAC주소를 수집합니다.<br>
eth1 설정 후 10.0.2.0/24에서 네트워크를 탐색합니다.<br>
<br>
<Br>

![image break](../../Pictur/MITM/arp4.png)<br>
When scanning, the first address that appears, 10.0.2.1, is usually the router gateway.<br>
This is not strictly predetermined, but it can be identified by checking the MAC vendor listed next to the MAC address.<br>
보통 탐색했을 때, 가장 위에 나오는 10.0.2.1이 라우터 게이트웨이입니다.<br>
정해진 건 아니지만 MAC 주소옆에 MAC vendor를 보고 알 수 있습니다.<br>

<br>
<Br>
<Br>


![image break](../../Pictur/MITM/arp5.png)<br>
The default value for IP forwarding is 0, meaning it is disabled, but it is changed to 1 to enable it.<Br>
This allows the traffic received by the intermediary to be forwarded to its intended destination without being dropped.<Br>
기본 값이 ip 포워딩이 0으로 비활성화 되어있는데, 이걸 1로 활성화합니다.<BR>
이로 인해 중간자에게 온 트래픽이 목적지로 끊기지 않게 보내게 됩니다.<br>
<Br>
<br>
<br>


![image break](../../Pictur/MITM/arp10.png)<br>
![image break](../../Pictur/MITM/arp11.png)<br>
Before performing ARP spoofing, these are the IP and MAC addresses of the victim PC and the intermediary PC.<br>
Arp spoofing 하기 전, 피해자PC와 중간자PC의 IP와 MAC주소입니다.<BR>
<BR>
<br>


![image break](../../Pictur/MITM/arp8.png)<br>
By sending ARP packets to both sides from the middle, the intermediary disguises itself as the router to the victim PC and as the victim PC to the router.<br>
* -r: executes in both directions<Br>
이렇게 중간에서 양쪽으로 arp 패킷을 보냄으로써, 피해자PC에게는 라우터로, 라우터에게는 피해자 PC로 위장합니다.<br>
* -r : 양방향으로 실행해줍니다.<br>
<br>
<Br>
<BR>
<br>

![image break](../../Pictur/MITM/arp9.png)<br>
It sends signals to both sides<br>
양쪽에 신호를 보냅니다.<br>
<BR>
<br>
<BR>
<br>

![image break](../../Pictur/MITM/arp12.png)<br>
![image break](../../Pictur/MITM/arp13.png)<br>
After ARP packets are sent, checking the ARP table shows that the victim’s MAC address appears spoofed as the intermediary’s MAC address.<Br>
At this point, all traffic passes through the intermediary before reaching the router.<Br>
ARP 패킷을 보내고 arp테이블 조회를 하면 피해자의 MAC주소는 중간자의 MAC주소로 위조되어 나옵니다. 이때 중간에서 모든 트래픽을 거쳐서 라우터로 이동하게 됩니다.
<BR>
<br>
<BR>
<br>

![image break](../../Pictur/MITM/arp14.png)<br>
When logging into a website over HTTP,<Br>
the information is not encrypted, allowing the intermediary to capture and view all login credentials through packet monitoring<Br>
HTTP로 이루어진 웹사이트에 로그인을 했을 때, 암호화 되어있지 않기 때문에 중간자는 패킷 감시로 로그인 정보를 전부알 수 있게 됩니다.
<BR>
<br>
<BR>
<br>

![image break](../../Pictur/MITM/arp15-1.png)<br>
Login information can be viewed through Wireshark.<br>
wireshark를 통해 로그인 정보를 볼 수 있습니다.


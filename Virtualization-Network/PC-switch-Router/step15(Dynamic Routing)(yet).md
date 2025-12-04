**RIP

<br>
<br>
동적 라우팅 중 거리 벡터(Distance Vector) 방식
<br>
<br>
<Br>
<br>
<Br>
<br>
<Br>


![image break](../../Pictur/step15/rip1.png)<Br>

<br>

![image break](../../Pictur/step15/rip2.png)<Br>

네트워크 주소(Network address)<br>
1.1.10.0<br>
1.1.12.0<br>
1.1.23.0<br>
1.1.30.0<br>

4개 모두 써야하지만, network 1.0.0.0으로 설정 후,<br>
version 2와 no auto-summary를 이용해 1.x.x.x에 속하는 모든 인터페이스를 한 번에 지정해 RIP 프로토콜을 활성화합니다.<br>

All four must be used, but after setting the network to 1.0.0.0,<br>
use version 2 and no auto-summary to enable the RIP protocol on all interfaces belonging to the 1.x.x.x range at once.<br>
<Br>

![image break](../../Pictur/step15/rip3.png)<Br>
If a 0.0.0.0/0 default route to the outside is configured on the ISP, default-information originate propagates it to the connected routers.<br>
default-information originate는 ISP에 외부로 나가는 0.0.0.0/0 기본 경로가 설정되어 있다면 연결된 다른 라우터에 전파합니다.




**distribute-list
<br>
<br>









**offset-list
<br>
<br>






**PBR
<br>
<br>

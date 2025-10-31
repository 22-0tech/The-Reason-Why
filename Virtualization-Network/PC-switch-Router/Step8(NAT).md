**NAT 

A technology that translates private IP addresses into public IP addresses.<br>
사설 IP 주소를 공인 IP 주소로 변환하는 기술<br>
<br>
<br>



*Security<br>

-Hides internal IP addresses → Enhances security.<br>
내부 IP를 숨김 → 보안성 향상 <br>
-Converts multiple IP addresses into a single IP → Partially alleviates the problem of IP address exhaustion.<br>
여러 개의 IP를 하나의 IP로 변환 → 주소 고갈 문제 일정 부분 해소<br>
<br>
<br>

 Three types ;

<br>


(GNS3)

![image break](../../Pictur/step8/NAT.1.png) <br>

* Static NAT


![image break](../../Pictur/step8/NAT2.png) <br>
When 192.168.1.1 goes out to the external network, it is translated to 10.1.1.101.<br>
When 192.168.1.2 goes out to the external network, it is translated to 10.1.1.102.<br>
192.168.1.1 가 외부로 나갈때, 10.1.1.101 로 변환<br>
192.168.1.2 가 외부로 나갈때, 10.1.1.102 로 변환<br>


* Dynamic NAT

![image break](../../Pictur/step8/NAT3.png) <br>
Erase the previous configuration.<br>
기존 설정 삭제 <br>
<br>

First, create a NAT pool.<br>
Next, apply NAT translation rules.<br>
Finally, specify internal IPs with an ACL.<br>

ㅡ NAT 풀 생성<br>
ㅡ NAT 변환 규칙 적용<br>
ㅡ ACL로 내부 IP 지정<br>


* PAT<br>

When no pool is used, each internal IP is distinguished by its external port number.<br>
*pool 없이 외부포트 번호로 (포트 번호 다르면 내부 IP 다름)

(GNS3)

![image break](../../Pictur/step8/NAT.1.png) <br>







![image break](../../Pictur/step8/NAT.4.png) <br>
First, configure the interface.<br>
Next, apply PAT (Port Address Translation).<br>
Finally, define an ACL (specifying the internal IP range for NAT).<br>

ㅡ 인터페이스 설정<br>
ㅡ PAT 적용<br>
ㅡ ACL정의 ( NAT 대상 내부 IP 범위) <br>



(f2/0 = f0/1,only here)

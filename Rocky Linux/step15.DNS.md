**DNS<br>
<Br>
<br>


Forward :   Domain → IP<br>
Reverse :   IP → Domain<br>
<br>
<Br>
A system that converts human-friendly website addresses into computer addresses (IP).<br>
사람이 기억하기 쉬운 웹사이트 주소를 컴퓨터의 주소(IP)로 바꿔주는 시스템<br>

<br>
<br>
<Br>
<Br>
<br>

![image break](../Pictur/step15/dns1.png)<br>
bind : DNS 서비스를 제공하는 서버 구축 시 필요<br>
bind-utils : DNS 관련 문제 해결 및 정보 조회 ex) nslookup<br>
<br>
<Br>
<Br>
<Br>

![image break](../Pictur/step15/dns3.png)<br>
vi /etc/resolv.conf  DNS 서버 주소 저장소.<br>
시스템 네트워크 관리 도구에 의해 자동적으로 관리되므로 유동적입니다.<Br>
<br>
nmcli con mod ens160 ipv4.dns 192.168.111.2<br>
수동으로 DNS 서버 주소를 설정합니다. 영구적 설정입니다.<br>

<br>
<Br>
<Br>
<br>
<br>



![image break](../Pictur/step15/dns2.png)<br>
vi /etc/named.conf<br>
zone : 도메인의 목록<br>

<Br>
<Br>
<Br>
<Br>
<br>

* Example
<br>
Domain name structure<br>
도메인 작성 양식
<br>
<Br>
<Br>


zone "Koreabcd.com" IN {<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        type master;<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;       file "Koreabcd.com.zone";<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;        allow-update { none; };<br>
};<br>
<br>

domain: Koreabcd.com<BR>
typy masterthe main server managing a domain zone.<br>
typy master : 도메인 영역의 주 관리 서버<br>

**DNS<br>
<Br>
<br>


Forward :   Domain → IP<br>
Reverse :   IP → Domain<br>

사람이 기억하기 쉬운 웹사이트 주소를 컴퓨터의 주소(IP)로 바꿔주는 시스템<br>

<br>
<br>


vi /etc/resolv.conf-유동<br>
nmcli con mod ens160 ipv4.dns 192.168.111.2<br>
<br>
<Br>




bind : DNS 서비스를 제공하는 서버 구축 시 필요<br>
bind-utils : DNS 관련 문제 해결 및 정보 조회 ex) nslookup<br>



마스터 DNS 서버 : DNS 중개 정보를 지니고 쿼리에 대한 응답<br>

vi /etc/named.conf<br>


zone : 서버가 관리하는 도메인의 목록<br>

새로운 도메인 영역 기입 시에,
<br>

zone "Koreabcd.com" IN {<br>
        type master;<br>
        file "Koreabcd.com.zone";<br>
        allow-update { none; };<br>
};<br>

typy master : 도메인 영역의 주 관리 서버<br>





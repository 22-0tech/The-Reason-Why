**Apache/Nginx<br>
<br>

웹 서버(Web Sever)<br>
<br>

![image break](../Pictur/step16/1.png)<br>
<br>
<br>
아파치의 패키지 이름은 httpd입니다.<br>

<br>
<br>


![image break](../Pictur/step16/2.png)<br>
<br>
아파치를 활성화합니다.<br>

<br>
<br>

![image break](../Pictur/step16/3.png)<br>

방화벽을 허용합니다.<br>

<br>
<br>

![image break](../Pictur/step16/4.png)<br>
<br>
<br>
웹 서버의 기본 디렉터리는 /var/www/html/입니다.<br>


<br>
<br>

![image break](../Pictur/step16/5.png)<br>
<br>
각각 제목과 내용의 위치입니다.<br>


<br>
<br>

![image break](../Pictur/step16/6.png)<br>
<br>
IP를 입력하면 웹페이지가 나옵니다.<br>

<br>
<br>
<br>
<Br>
<Br>
<Br>

* 일반 사용자 계정의 웹 설정<br>
<br>


![image break](../Pictur/step16/7.png)<br>
<br>
<br>
![image break](../Pictur/step16/8.png)<br>
<br>
각각 주석처리와 적용을 합니다.<br>


<br>
<br>

![image break](../Pictur/step16/9.png)<br>
<br>
적용 후에 다시 동작시킵니다.<br>

<br>
<br>

![image break](../Pictur/step16/10.png)<br>
<br>
일반 계정 생성 후 디렉터리를 만듭니다. 최소 권한 설정을 합니다.<br>


<br>
<br>

![image break](../Pictur/step16/11.png)<br>

HTML 형식에 맞게 작성합니다.<br>

<br>
<br>


![image break](../Pictur/step16/12.png)<br>
<br>
IP 주소 아래 사용자 계정까지 입력 접속합니다. 이런 식으로 접근 권한이 없다고 나올 수 있습니다.<br>

<br>
<br>



![image break](../Pictur/step16/13.png)<br>

Selinux 보안 적용을 해제 하는 setenforce 0을 적용시키면 접속이 가능합니다.<br>




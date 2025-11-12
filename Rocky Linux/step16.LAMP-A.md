**Apache/Nginx<br>
<br>

웹 서버(Web Sever)<br>
<br>

![image break](../Pictur/step16/1.png)<br>
<br>
<br>
The package name for Apache is httpd.<br>
아파치의 패키지 이름은 httpd입니다.<br>

<br>
<br>


![image break](../Pictur/step16/2.png)<br>
Apache is activated.<br>
아파치를 활성화합니다.<br>

<br>
<br>

![image break](../Pictur/step16/3.png)<br>
The firewall is allowed.<br>
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
These are the respective locations of the title and content.<br>
각각 제목과 내용의 위치입니다.<br>


<br>
<br>

![image break](../Pictur/step16/6.png)<br>
The webpage appears when the IP is entered.<br>
IP를 입력하면 웹페이지가 나옵니다.<br>

<br>
<br>
<br>
<Br>
<Br>
<Br>
* Web settings for a general user account are configured.<br>
* 일반 사용자 계정의 웹 설정<br>
<br>


![image break](../Pictur/step16/7.png)<br>
<br>
<br>
![image break](../Pictur/step16/8.png)<br>
A comment is made and applied to each one.<br>
각각 주석처리와 적용을 합니다.<br>


<br>
<br>

![image break](../Pictur/step16/9.png)<br>
After application, it is operated again.<br>
적용 후에 다시 동작시킵니다.<br>

<br>
<br>

![image break](../Pictur/step16/10.png)<br>
After creating the general account, the directory is created. Minimum privilege settings are configured.<br>
일반 계정 생성 후 디렉터리를 만듭니다. 최소 권한 설정을 합니다.<br>


<br>
<br>

![image break](../Pictur/step16/11.png)<br>
It is written in accordance with the HTML format.<br>
HTML 형식에 맞게 작성합니다.<br>

<br>
<br>


![image break](../Pictur/step16/12.png)<br>
The connection is made by entering the IP address followed by the user account. Access denied may appear in this manner.<br>
IP 주소 아래 사용자 계정까지 입력 접속합니다. 이런 식으로 접근 권한이 없다고 나올 수 있습니다.<br>

<br>
<br>



![image break](../Pictur/step16/13.png)<br>
By applying setenforce 0, which disables the SELinux security enforcement, connection becomes possible.<br>
Selinux 보안 적용을 해제 하는 setenforce 0을 적용시키면 접속이 가능합니다.<br>




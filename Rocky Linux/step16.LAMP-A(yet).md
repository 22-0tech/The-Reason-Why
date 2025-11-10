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
<br>

![image break](../Pictur/step16/7.png)<br>
<br>
<br>
![image break](../Pictur/step16/8.png)<br>
<br>
<br>
![image break](../Pictur/step16/9.png)<br>
<br>
<br>
![image break](../Pictur/step16/10.png)<br>
<br>
<br>
![image break](../Pictur/step16/11.png)<br>
<br>
<br>
![image break](../Pictur/step16/12.png)<br>
<br>
<br>
![image break](../Pictur/step16/13.png)<br>







/etc/httpd/conf/httpd.conf
httpd 서버 기본 설정 파일
<BR>
<bR>
<bR>
<BR>


아파치 사용자 계정 설정 파일
/etc/httpd/conf.d/userdir.conf
<br>

#    UserDir disabled
UserDir public_html
<br>
**chmod 701 .(현재 디렉터리)

chmod 701 public_html


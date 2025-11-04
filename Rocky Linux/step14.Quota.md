**Quota<br>
<Br>
Disk Quota<br>
정해진 한도<br>
<Br>

<br>
<Br>

usrquota : 개별 사용자의 쿼터 제한할 수 있는 속성<br>
qrpquota : 개별 그룹의 쿼터 제한할 수 있는 속성<br>
<br>
<br>
![image break](../Pictur/step14/0.png)<br>
<br>
This is the current disk status.<br>
현재 디스크 상태입니다.

Command : vi /etc/fstab<br>
<br>
An option must be added to the script to activate the quota function.<Br>
해당 스크립트에 옵션을 추가해야 쿼터 기능이 활성화됩니다.<br>
<br>
<br>
<Br>
![image break](../Pictur/step14/1.png)<br>
The disk will be formatted before the quota is set.<Br>
쿼터 설정하기 전에, 디스크 포맷을 먼저하겠습니다<br>

![image break](../Pictur/step14/2.png)<br>
Disk format.<br>
디스크 포맷입니다.<br>
<Br>

![image break](../Pictur/step14/3.png)<br>
Mounts to each mount point.<br>
마운트 포인트에 각각 마운트합니다.<br>
<br>
<Br>

![image break](../Pictur/step14/4.png)<br>
It is configured according to individual user properties.<br>
개별 사용자 속성에 맞게 작성합니다<br>
<br>
<br>
<Br>

![image break](../Pictur/step14/5.png)<br>
The filesystem must be remounted since quota settings do not take effect right away.<br>
쿼터 속성을 설정 후 바로 적용되는 것이 아니기때문에, 파일 시스템을 다시 마운트합니다<br>
<br>
<Br>
quotacheck: Creation of the quota database = 쿼터용 데이터베이스(aquota.user, aquota.group) 생성<br>

![image break](../Pictur/step14/6.png)<br>


![image break](../Pictur/step14/7.png)<br>
<br>
\The quota database file has been created.<br>
쿼터 데이터베이스 파일이 생성되었습니다..<br>
<Br>
<br>

quotaon : Activates the quota = 쿼터 기능 활성화<br>

![image break](../Pictur/step14/8.png)<br>
<br>
<br>
<br>
<br>
edquota : Configures the quota = 쿼터 설정<br>

![image break](../Pictur/step14/9.png)<br>


![image break](../Pictur/step14/10.png)<br>

<br>
<br>
Command: The quota information can be viewed using the quota command.<br>
Command : quota를 사용하여 쿼터 정보를 볼 수 있습니다.


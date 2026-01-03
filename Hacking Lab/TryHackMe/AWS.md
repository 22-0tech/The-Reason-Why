![image 1](/Pictur/Hacking%20lab/AWS/1.png)<br>

<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AWS/2.png)<br>
When the machine is run, the AWS execution screen appears.<br>
머신을 실행하면 AWS 실행 화면이 나옵니다.
<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/AWS/3.png)<br>
There is an AWS folder in the hidden folder.<br>
숨겨진 폴더에 AWS가 있습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AWS/4.png)<br>
The credentials show a key that grants access to the AWS Cloud Center.<br>
자격증명을 보면 AWS 클라우드 센터 출입이 가능한 키가 나왔습니다.
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AWS/5.png)<br>
The Access Key allows for identity verification using the aws sts get-caller-identity command. The user SirCarrotBane was found.<br>
Access Key소지로 aws sts get-caller-identity 신분확인을 할 수 있습니다. sircarrotbane인 사용자를 찾았습니다.
<br>
<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/AWS/6.png)<br>
In AWS, policies are permissions, so a lookup is performed.<br>
AWS에서는 정책이 권한이기 때문에 조회를 진행합니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AWS/7.png)<br>

<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AWS/8.png)<br>
Roles can also be permissions, so a lookup is performed. The role bucketmaster was found.<br>
역할 또한 권한이 될 수 있기 때문에 조회를 진행합니다. bucketmaster를 발견했습니다. 
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AWS/9.png)<br>
After assuming the role of bucketmaster, an temporary identity token was received.<br>
bucketmaster로 역할로 변신 후, 임시 신분증을 받았습니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AWS/10.png)<br>
After setting the temporary identity token with export, the current status confirms the role as bucketmaster.<br>
export로 임시 신분증 설정 후 현재 상태를 확인하면 bucketmaster로 확인이 됩니다.
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AWS/11.png)<br>
Since the role is bucketmaster, an S3 lookup is performed.<br>
bucketmaster이기 때문에 s3를 조회합니다. 
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/AWS/12.png)<br>
The THM flag has been captured, and the cloud password has been found.<br>
THM의 flag를 쟁취했고, 클라우드 비밀번호를 확인했습니다.

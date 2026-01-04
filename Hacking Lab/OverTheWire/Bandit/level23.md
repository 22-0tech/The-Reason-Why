**Cron<br>
<br>
<br>

(Kali)

![image break](/Pictur/Level23/bandit1.png) <br>
The next step is 24, so files related to 24 are checked.<br>
The key point is that the script runs every minute under the bandit24 account.<br>
다음 단계가 24이기 때문에 24관련 파일을 봅니다.<br>
*Key-매 분마다 스크립트가 실행되는데 bandit24 권한으로 실행되는 게 핵심입니다.<br>

![image break](/Pictur/Level23/bandit2.png) <br>
It moves to the folder and executes the files.<br>
Since the next step is 24, the intermediate path is assumed to be under bandit24.<br>
해당 폴더로 이동해서 파일을 실행한다고 합니다.<br>
다음 단계가 24이기 때문에 중간 경로는 bandit24일 것으로 추측합니다.<br>

![image break](/Pictur/Level23/bandit3.png) <br>
<br>
<br>


![image break](/Pictur/Level23/bandit4.png) <br>
Because the script runs with the privileges of user 24,<br>
the password for user 24 is read and passed to a temp file.<br>
24의 권한으로 스크립트를 실행하기 때문에<br>
24의 비밀번호를 보고 임시 디렉터리의 파일로 넘겨주는 방식으로 합니다.<br>

![image break](/Pictur/Level23/bandit5.png) <br>
Full rwx permissions were set, but giving only minimal permissions is safer.<br>
rwx권한 모두 줬지만, 최소 권한만 주는 게 안전합니다.<br>

![image break](/Pictur/Level23/bandit6.png) <br>
Although user 23 cannot know user 24's password,<br>
this method can be used because the script runs with user 24's privileges.<br>
23은 24의 비밀번호를 알 수 없지만<br>
24의 권한으로 실행되기 때문에, 이런 방법을 사용할 수 있습니다.<br>

![image break](/Pictur/Level23/bandit7.png) <br>
Execution confirmed by the file being missing.<br>
파일이 없음으로 실행됨을 알 수 있습니다.<br>

![image break](/Pictur/Level23/bandit8.png) <br>



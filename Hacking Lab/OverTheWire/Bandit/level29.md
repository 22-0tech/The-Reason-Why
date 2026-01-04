**branch<br>
<br>
<br>
Clone fetches all data, but only the default branch is checked out locally, usually main or master. <br>
Other remote branches also exist.<br>

clone은 전체 데이터들을 가져오지만, 기본 브랜치만 로컬에 체크아웃 된 것입니다.<br>
보통 main 또는 master입니다. 이 외에 원격 브랜치들이 있습니다.<br>
<br>
<br>


(Kali)

![image break](/Pictur/Level29/bandit1.png) <br>
It is said that passwords are not stored in the production environment.<br>
운영 환경에 비밀번호를 저장하지 않는다고 합니다.<br>


![image break](/Pictur/Level29/bandit2.png) <br>
Unlike the previous stage, no useful hints were found even after checking the logs.<br>
전단계와 다르게 log를 봐도 별다른 힌트를 얻지 못했습니다.<br>


![image break](/Pictur/Level29/bandit3.png) <br>
The log history of the remote branch dev was checked first.<br>
원격 브랜치 중에서 dev의 log 기록을 먼저 봤습니다.<br>

![image break](/Pictur/Level29/bandit4.png) <br>
There was a record titled “add needed data,” so the commit history was checked.<br>
필요한 데이터 추가라는 기록이 있어 커밋 기록을 봤습니다. <br>


![image break](/Pictur/Level29/bandit5.png) <br>
It can be seen that the password was added.<br>
비밀번호가 추가됨을 알 수 있습니다.<br>
<br>
<br>
<br>

![image break](/Pictur/Level29/bandit6.png) <br>
At first, the dev branch was checked, and the password was luckily found right away.<br>
However, the log history of all local and remote branches can be viewed.<br>
처음에 dev를 먼저 보고 운이 좋게 바로 나왔지만,<br>
로컬과 원격에 있는 모든 브랜치의 로그 기록을 볼 수 있습니다.<br>

![image break](/Pictur/Level29/bandit7.png) <br>
There are slight differences, but this command can also display the log history of all branches.<br>
약간의 차이는 있지만, 해당 명령어도 모든 브랜치의 로그 기록을 볼 수 있습니다.<br>
<br>
<br>

![image break](/Pictur/Level29/bandit8.png) <br>
In order: current local branch, remote branch, and local + remote branches.<br>
순서대로 현재 로컬 브랜치, 원격 브랜치, 로컬+원격 브랜치입니다.

![image break](/Pictur/Level29/bandit9.png) <br>
The current local branch will be switched from master to dev.<br>
현재 로컬 브랜치 master에서 dev로 바꿔보겠습니다.<br>

![image break](/Pictur/Level29/bandit10.png) <br>
The local branch can be changed using checkout.<br>
Since the password could be verified using only log, the branch was not changed.<br>
checkout을 통해 로컬 브랜치를 변경할 수 있습니다. <br>
*Why-log만으로 비밀번호를 확인할 수 있었기에 변경하지 않았습니다.

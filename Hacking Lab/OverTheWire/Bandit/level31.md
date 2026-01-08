**push<br>
<br>
<br>
(Kali)

![image break](/Pictur/Level31/bandit1.png) <br>
The task is to create the file according to the conditions and push it to the remote branch to obtain the password.<br>
Looking at the branches, it should be pushed from the local master branch to the remote master branch.<br>

조건에 맞게 해당 파일을 만들어서 원격 브랜치로 보내서 암호를 얻는 문제입니다.<br>
브랜치를 보면 로컬 master브랜치에서 원격 master브랜치로 보내야합니다.<Br>
<br>
<br>

![image break](/Pictur/Level31/bandit.2.png) <br>
After the file is created according to the conditions, it is added to Git.<br>
An error occurs due to .gitignore rules. The error can be bypassed by forcing the add with -f<br>

조건에 맞게 파일을 만든 후, git에 추가합니다.<br>
이때, .gitignore 규칙 때문에 오류가 납니다. -f를 이용해 무시할 수 있다고 합니다.<br>

![image break](/Pictur/Level31/bandit3.png) <br>
<br>
<br>
<br>

<br>

![image break](/Pictur/Level31/bandit4.png) <br>
After committing with a message like “add,” checking shows that it appears to have been recorded correctly.<br>
add라는 메시지를 이용해 기록한 후, 확인해보니 맞게 잘 된 거 같습니다.<br>
<br>
<br>
<br>


![image break](/Pictur/Level31/bandit5.png) <br>
The password is obtained by pushing to the remote master branch using git push.<br>
git push로 원격 master브랜치로 보내면 비밀번호를 얻을 수 있습니다. 
<br>
<br>
<br>


![image break](/Pictur/Level31/bandit6.png) <br>


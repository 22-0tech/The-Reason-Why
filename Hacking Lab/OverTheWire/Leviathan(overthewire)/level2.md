![image break](/Pictur/Level2/levia1.png) <br>
Just connect. 접속합니다.

![image break](/Pictur/Level2/levia2.png) <br>
An executable file with the SUID (setuid) bit set prompts you to enter a password when run.<br>
s(setuid)설정된 실행 파일 실행 -> 비밀번호를 입력해야함

![image break](/Pictur/Level2/levia3.png) <br>
Using strings, you can check which strings and functions are included (optional).<br>
strings으로 어떤 문자열과 함수가 포함되어 있는지 확인 가능 (선택)

![image break](/Pictur/Level2/levia4.png) <br>
**Why – Use ltrace to check the actual function behavior.<br>
The strcmp function compared the strings (jj vs sex) and returned -1, indicating they are different.
→ Therefore, you need to enter sex.<br>
<br>
*why-실제 함수 동작을 확인하기 위해 ltrace 사용
jj 입력해봤더니 strcmp함수 문자열 비교 (개수x) jj와 sex가 다름 = -1<br>
-> sex를 입력해야함
 <br>
 <br>
 <br>
 <br>
![image break](/Pictur/Level2/levia5.png) <br>
After entering sex, the return value changed to 0.
The UID 12001 is confirmed, and setreuid() is used to change the privileges to 12001, then a shell is obtained.
However, running ltrace ./check executes with the current user privileges (currently leviathan1).<br>
So, run ./check directly to verify the password.<br>

sex입력했더니 값이 0으로 바뀌면서 
UID 12001 확인 후 setreuid()로 권한을 12001로 변경 후 쉘 획득
하지만, ltrace ./check실행이 현재 사용자 권한으로 실행이므로 현재 leviathan1 
그냥./check로 실행 후 비밀번호 확인 

![image break](/Pictur/Level2/levia6.png) <br>
It can now be verified since the current user is leviathan2.<br>
지금은 leviathan2로 확인 가능

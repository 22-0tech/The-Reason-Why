![image break](/Pictur/Level2/bandit1.png) <br>
The filename runs from --spaces to --, but because of the spaces, the shell interprets the command as separate arguments,<br>
so it cannot be read as a whole.<br>
It must be specified so that the entire string from --spaces to -- is recognized as a single filename.<br>
--spaces부터 --까지가 파일명인데,<br>
공백 때문에 쉘이 명령어를 나눠서 해석하므로 전체를 한 번에 읽을 수 없습니다.<br>
--spaces부터 --까지 자체를 파일 명으로 인식하게 표시를 해줘야합니다.

![image break](/Pictur/Level2/bandit2.png) <br>
Using a backslash before spaces prevents them from being recognized as argument separators.<br>
\을 넣어주면 공백을 구분자로 인식하지 않고 있는 그대로 해석합니다.

![image break](/Pictur/Level2/bandit3.png) <br>
Another way is to enclose the entire file name in double quotes so that it is recognized as a single file.<br>
또 다른 방법은 "큰따옴표로 파일 전체를 감싸면 파일로 인식합니다.

![image break](/Pictur/Level2/bandit4.png) <br>
The entire name can also be enclosed.<br>
전체를 감싸줘도 됩니다.

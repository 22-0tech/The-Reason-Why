![image break](/Pictur/Level6/bandit1.png) <br>
With no hidden files in the home directory, the command searches for files that meet the conditions in the root directory.<br>
홈 디렉토리에서 숨겨진 파일도 없어 최상위 디렉토리에서 조건에 맞는 파일을 찾아보겠습니다.

![image break](/Pictur/Level6/bandit2.png) <br>
However, starting the search from the root directory may cause permission issues.<br>
Adding 2>/dev/null suppresses error messages such as “Permission denied.<br>
하지만 파일 찾는 경로가 루트에서 시작이기 때문에 권한 문제가 생깁니다.<br>
2>/dev/null을 넣어 권한 거부 등의 에러 메세지를 표시하지 않고 출력합니다.

![image break](/Pictur/Level6/bandit3.png) 

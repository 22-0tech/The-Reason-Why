**It is a step for extracting the archive.<br>
압축을 푸는 게 목적인 단계입니다.<br>
<br>
<Br>

![image break](/Pictur/Level12/bandit1.png) <br>
This is data.txt, which is a hexdump of a file that has been repeatedly compressed.<br>
data.txt는 여러 번 압축된 파일을 헥사덤프로 저장한 파일입니다.


![image break](/Pictur/Level12/bandit2.png) <br>
A temporary directory is created for the task, and the output is redirected to a new file to prevent corruption when converting to binary.<br>
command : xxd -r<br>
작업할 수 있는 임시 디렉터리를 만들고 바이너리로 변환 후 바이너리가 깨질 수 있기 때문에 리다이렉션으로 새파일에 보내겠습니다.<br>
명령어는 xxd -r입니다. 


![image break](/Pictur/Level12/bandit3.png) <br>
The hex file's header shows 1f8b, indicating it is compressed with gzip.<br>
The extension was changed to .gz, and it was then extracted.<br>
헥사값 파일의 헤더를 보면 1f8b가 보입니다. gzip로 압축됨을 알 수 있습니다. <br>
확장자를 gz로 바꾸고 압축해제를 했습니다.

![image break](/Pictur/Level12/bandit4.png) <br>
The type of the extracted file showed it was compressed with bzip2.<br>
The extension is changed to .bz2, and it is then extracted.<br>
압축하고 난 파일의 타입을 봤더니 또 bzip2로 압축되어 있다고 합니다.<br>
이것도 확장자를 bz2로 바꾼 후 압축 해제를 진행합니다.


![image break](/Pictur/Level12/bandit5.png) <br>
After extraction, the file was found to be compressed with gzip. It is extracted again and then inspected.<br>
압축 해제 후 파일을 봤더니 gzip으로 압축된 파일입니다. 압축 해제 후 다시 조회합니다.

![image break](/Pictur/Level12/bandit6.png) <br>
The files are archived. <br>
The extraction command : tar -xf.<br>
아카이브로 묶여 있습니다. 해제 명령어는 tar -xf입니다.

![image break](/Pictur/Level12/bandit7.png) <br>
Upon inspection, a new file was found. This file is also inspected.<br>
조회 했더니 새파일이 보입니다. 이 파일도 조회합니다. 


![image break](/Pictur/Level12/bandit7.7.png) <br>
The new file is also extracted from the archive, and another file came out.<br>
새파일도 아카이브 해제를 해줍니다. 또 다른 파일이 나옵니다.

![image break](/Pictur/Level12/bandit8.png) <br>
The newly extracted file is inspected and then decompressed according to the conditions.<br>
새로 나온 파일도 조회 후 조건에 맞게 압축 해제합니다. 

![image break](/Pictur/Level12/bandit9.png) <br>
This process is repeated as before, and finally, an ASCII file is obtained.<br>
위에서 했던 것처럼 반복 후, ASCII인 마지막 파일이 보입니다. 

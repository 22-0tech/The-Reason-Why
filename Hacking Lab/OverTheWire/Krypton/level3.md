![image break](/Pictur/Level3/krypton.1.png) <br>

Running encrypt requires a plaintext file.<br>
A temporary directory was created for testing, but the attempt failed.<br>
Since only encrypt can access keyfile.dat, the solution is to create a symbolic link to it in the temporary directory.<br>

encyrpt를 실행시켰더니 평문이 들어있는 파일이 필요하다고 합니다.
임시 디렉을 만들어서 읽었봤는데 실패했다고 나옵니다.<br>
keyfile.dat에는 encrypt가 접근 가능한데,
keyfile.dat 또한 권한이 없기 때문에 임시디렉토리에 심볼릭 링크를 걸어보겠습니다.
<br>
<br>
<br>
<br>
<br>



![image break](/Pictur/Level3/krypton2.png) <br>
Permissions were granted to the current directory.<br>
Although 777 was set, it poses a security risk, so 700 is recommended instead.<br>

현재 디렉토리 권한을 줬습니다. <br>
777을 줬지만, 보안상 위험하기 때문에 700이 좋을 거 같습니다. 
<br>
<br>
<br>
<br>
<br>
<br>



![image break](/Pictur/Level3/krypton3.png) <br>
A plaintext file was created in the directory with the symbolic link and read using encrypt.<br>
A ciphertext file was generated, which is the encrypted output from encrypt.<br>
'AAAA' became 'MMMM', showing a shift of 12 positions.<br>
By applying an additional shift of 14 positions and reading the krypton3 file, the password can be obtained.<br>

심볼릭 링크가 걸린 디렉토리에 평문이 있는 파일을 만들고 encrypt로 읽습니다. <br>
ciphertext 파일이 생겼습니다. encrypt가 만든 암호문입니다.<br>
AAAA를 넣은 평문이 MMMM으로 나왔습니다.<br>
12칸 이동한 걸 볼 수 있습니다. 14칸을 더 이동시켜서 krypton3 파일을 읽으면 비밀번호입니다.
<br>
<br>
<br>
<br>
<br>
<br>



![image break](/Pictur/Level3/krypton4.png) <br>

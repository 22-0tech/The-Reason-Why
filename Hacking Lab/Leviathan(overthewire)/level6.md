![image break](/Pictur/Level6/levia1.png)<br>
A 4-digit number is required. To find the variable value, gdb must be used, as it provides more detailed information than ltrace.<br>
4자리 숫자 입력 요구, 변수 값을 찾기 위해 ltrace보다 더 자세한 gdb를 이용합니다.

![image break](/Pictur/Level6/levia2.png)<br>
Check the assembly code.<br>
어셈블리코드 확인 

![image break](/Pictur/Level6/levia3.png) <br>
Execution stops at +84. The cmp instruction compares eax (the user input value) with the value stored at (ebp).<br>
+84에 멈춤 cmp(비교) eax(사용자 입력 값)과 (ebp)내부값을 비교합니다.

![image break](/Pictur/Level6/levia4.png) <br>
x/u $ebp-0xc → Viewing the variable in memory shows the value 7123.<br>
x/u $ebp-0xc 변수값 메모리 보기 7123이네요.

![image break](/Pictur/Level6/levia5.png) <br>
It is also possible to enter the values one by one in the terminal.<br>
터미널에 하나씩 값을 입력하는 방법도 있습니다. 

![image break](/Pictur/Level6/levia6.png) <br>
It stops at the same point, 7123.<br>
똑같이 7123번에서 멈춥니다.

![image break](/Pictur/Level6/levia7.png) <br>

![image break](/Pictur/Level6/levia8.png) <br>
This method does not reveal the number, but the answer can still be obtained.<br>
이 방법은 번호는 안 나오지만 답은 구할 수 있습니다.

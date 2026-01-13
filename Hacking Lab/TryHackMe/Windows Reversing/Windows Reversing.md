* 사전 지식 지식(prior knowledge)<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/windowreversing/1.png)
<br>
<br>
(Windows)  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;&ensp; &ensp; &ensp; &ensp;&ensp; &ensp; (Linux)<br>

----------------------------------
mov [목적지], [시작]  &ensp; &ensp;  &ensp; &nbsp; &ensp; &ensp;  mov [시작], [목적지]<br>

rax, rbx &ensp; &ensp;  &ensp; &nbsp; &ensp; &ensp;  &ensp; &nbsp; &ensp; &ensp; &ensp; &ensp;  &ensp; &nbsp; %rax, %rbx<br>

100, 0xFF  &ensp; &ensp;  &ensp; &nbsp; &ensp; &ensp;  &ensp; &nbsp;&ensp; &ensp;  &ensp; &ensp; &nbsp; $100, $0xFF<br>

[rax]  &ensp; &ensp;  &ensp; &nbsp; &ensp; &ensp; &ensp; &nbsp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &nbsp; (%rax)<br>
<br>
<br>
<br>


16진수(Base 16): 2진수를 4개씩 묶어 표현. A=10, B=11, C=12, D=13, E=14, F=15<br>

표기법 :  앞에 0x 또는 뒤에 h<br>

예시: 0x4B = (16^1 x 4) + (16^0 + 11) = 64 + 11 = 75(10진수)<br>
<br>
<br>
<br>
<br>
<br>
<br>
컴퓨터의 참(True) & 거짓(False)<br>
<br>
* False : Only 0<br>
* True : 0이 아닌 모든 값<br>

*Exeample : TEST EAX, EAX &ensp; &ensp; → &ensp; &ensp; EAX가 0(거짓)인지 아닌지 체크<br>
<br>
<br>
<br>
<br>
<br>
비트 연산<br>
<br>

* NOT(!) : 반대로 뒤집기 (0 → 1, 1 → 0)<br>
* AND(&) : 둘 다 1   &ensp;  → &ensp;  1<br>
* OR(|) : 둘 중 하나만 1이면 1<br>
* XOR(^) : 둘이 다르면 1, 같으면 0 (배타적 논리합)<br>
<br>
*Exeample : XOR EAX, EAX &ensp; &ensp; → &ensp; &ensp; 레지스터 0으로 초기화<br>
<br>
<br>
<br>
<br>
<br>
<br>
범용 레지스터<br>
<br>

* RAX (Accumulator): 함수의 리턴 값 저장소<br>
* RCX (Counter) : 반복문(Loop) 횟수 저장<br>
* RDX (Data) : 연산 또는 입출력 보조<br>
* RBX (Base) : 메모리 주소를 가리키는 기준점<br>
* RSI / RDI : 데이터 복사할 때 (Source) / (Destination)<br>
* RSP / RBP(Base) : 스택의 최상단 및 기준점<br>
<br>
<br>
<br>
<br>
<br>
<br>
레지스터의 계층<br>
<br>

* RAX : 64비트 전체 (8바이트)<br>
* EAX : 하위 32비트 (4바이트)<br>
* AX : 하위 16비트 (2바이트)<br>
* AH /AL : AX를 상위 8비트, 하위 8비트로 나눈 것 (1바이트)<br>
<br>
<br>
<br>
<br>
<br>
<br>
특수 레지스터<br>
<br>

* RIP (Instrucion) : (가장 중요) 다음에 실행할 코드의 주소<br>
* XMM / YMM : 소수점 계산 또는 여러 데이터를 한번에 처리(벡터 연산)시 사용<br>
<br>
<br>
<br>
<br>
<br>
<br>
어셈블리어(Assembly Language)<br>
<br>

* MOV : 데이터 복사
* LEA : 계산된 주소값 입력
* PUSH :  값을 스택에 PUSH(백업)
* POP : 스택 최상단에서 값을 꺼내 레지스터에 복구
* ADD /SUB : 더하기 / 빼기<br>
* INC / DEC :  1 증가 / 1 감소
* MUL / DIV : 곱하기 / 나누기
* CMP : 두 값 비교
* JCC : jne(다르면 점프), jg(크면 점프)
*  CALL / RET : 함수 호출 / Return(복귀)
<br>
<br>
<br>
<br>
<br>
상태 플래그(Status Flag)<br>
<br>

이름  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;약자  &ensp; &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp;조건  &ensp; &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp;의미

------------------------
Zero Flag &ensp; &ensp; &ensp; ZF  &ensp; &ensp; &ensp; &ensp; 결과 0  &ensp; &ensp; &ensp; &ensp; 두 값이 같을 때<br>
Sign Flag  &ensp; &ensp; &ensp; SF &ensp; &ensp; &ensp; 결과 음수(-)  &ensp; &ensp;  가장 왼쪽 비트 1<br>
Carry Flag  &ensp; &ensp; &ensp; CF  &ensp; &ensp; &ensp; 부호 없는 수 연산에서 넘칠 때  &ensp; 자릿수 올림 또는 빌림<br>
Overflow Flag  &ensp; &ensp;  OF &ensp; &ensp; &ensp; 부호 있는 수 연산에서 넘칠 때  &ensp; 결과가 레지스터 용량 초과<br>


















<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>


![image 1](/Pictur/Hacking%20lab/windowreversing/2.png)

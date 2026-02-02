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

이름  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; 약자  &ensp; &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; 조건  &ensp; &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; 의미

------------------------
Zero Flag &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;ZF  &ensp; &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &nbsp; 결과 0  &ensp; &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;&ensp; &ensp; 두 값이 같을 때<br>

Sign Flag  &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;SF &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;결과 음수(-)  &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;&ensp; &ensp; 가장 왼쪽 비트 1<br>

Carry Flag  &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;CF  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; 부호 없는 수 연산에서 넘칠 때  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;자릿수 올림 또는 빌림<br>

Overflow Flag  &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;OF &ensp; &ensp; &ensp;  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;부호 있는 수 연산에서 넘칠 때  &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp; &ensp;결과가 레지스터 용량 초과<br>
<br>

*Example : mov rax, 4<br>
&ensp; &ensp;&ensp; &ensp; &ensp; &ensp; &ensp;cmp rax, 4<br>

계산 결과가 0이므로 ZF가 1이 됩니다. 만약 음수(-)라면 SF가 1이 되며, ZF 또한 0이 됩니다.<br>
<br>
<br>
<br>
<br>
<br>
<br>
메모리 영역 구역<br>
<br>
* .text(Code) : 실제 실행되는 기계어 코드가 들어있는 곳
* .data : 초기화된 전역 변수나 정적 변수가 저장되는 곳
* .bss : 초기화되지 않은 전역 변수가 저장되는 곳
* Heap(힙) : 실행 중 malloc 등 동적으로 할당되는 데이터가 저장되는 곳 (낮은 주소 → 높은 주소)
* Stack(스택) : 지역 변수, 함수 매개변수, 리턴 주소 등 저장되는 임시 공간 (높은 주소 → 낮은 주소)
<br>
<br>
<br>
<br>
<br>
스택 동작 원리<br>
<br>
* LIFO (Last-In-First-Out) : 마지막에 넣은 데이터가 가장 먼저 나옵니다.<br>
* Push : 데이터를 넣는 동작.<br>
* Pop : 데이터를 꺼내는 동작. RSP가 증가하며 아래로 줄어듭니다. (높은 주소가 아래)<br>
* RSP : 현재 스택의 가장 꼭대기(가장 낮은 주소)<br>
* RBP : 현재 함수가 사용하는 메모리 공간(스택 프레임)의 '고정된 기준점'<br>
<br>
<br>
<br>
<br>
<br>
<br>
스택 프레임<br>
<br>
함수 인자 : 함수에 전달되는 값들<br>
리턴 주소 : 함수가 끝난 후 돌아갈 코드 위치<br>
이전 RBP 값 : 이전 함수의 바닥 주소를 저장 후 나중에 복구<br>
지역 변수 : 함수 내부에서 선언된 변수<br>
<br>
<br>
<br>
<br>
<br>
<br>
엔디언(Endianness) : 메모리 배치 방식<br>
<br>
Big Endian : 사람이 읽는 순서<br>
Little Endian : 하위 바이트부터 거꾸로 저장 (0xDEADBEEF → EF BE AD DE)

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/windowreversing/2.png)<br>
An introduction to Windows reverse engineering for beginners.<br>
윈도우 리버싱 엔지니어링 Intro로 입문편입니다.
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/windowreversing/3.png)<br>

When the machine is started, the IDA engineering tool and two files to be analyzed are provided.<br>
머신을 시작하면 IDA 엔지니어링 도구와 분석해야 할 파일 2개가 나옵니다.
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/windowreversing/4.png)<br>
The HelloWorld.exe executable will be analyzed first.<br>
HelloWorld.exe 실행파일 먼저 보겠습니다.
<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/windowreversing/5.png)<br>
<br>

The analysis begins at the program entry point, the main function.<br>
The first instruction executed is a subtraction (sub) of 28h from rsp, which allocates stack space.<br>
Before a function call (call), the arguments are set up using lea. The first argument is passed in rcx, and the second argument is passed in rdx.<br>

프로그램 시작점 main함수부터 보겠습니다. 가장 먼저 실행되는 명령은 빼기(sub)로 28h - rsp로 메모리 공간을 확보하는 행위입니다.<br>
함수를 호출(call)하기 전, 인자 설정(lea)을 먼저합니다. 첫 번째 인자는 rcx, 두 번째 인자는 rdx입니다.<br>

<br>
<br>
<br>
<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/windowreversing/6.png)<br>

<br>
<br>
<br>

![image 1](/Pictur/Hacking%20lab/windowreversing/7.png)<br>

<br>
<br>
<br>

**booting<br>
<Br>
<br>



1.BIOS (Basic Input/Output System)<br>
<br>
PC를 켜면 먼저 바이오스가 작동합니다.<br>
기본적인 하드웨어의 상태(ON-OFF)를 확인 후, 부팅 장치를 선택하여 그 디스크의 첫 섹터 512B(MBR)를 로딩합니다.<br>
MBR에는 부트로더 위치 정보가 있습니다. 이를 메모리에 로딩해 2차 부팅 프로그램을 실행합니다<br>

BIOS 단계 : 하드웨어 검사 → 부팅장치 선택 → MBR 로드 → 부트 로더로드<br>
<br>
<Br>


2.부트 로더(GRUB)<br>

오픈 소스인 리눅스 커널을 메모리에 로딩합니다.<br>
<br>
![image break](../Pictur/step13/GRUB1.png)<br>



3. 커널 초기화 단계<br>

시스템에 연결된 하드웨어를 사용 가능한 상태로 준비하고 커널을 초기화합니다. 이후 서비스 실행을 위해 '첫 번째' 프로세스를 생성합니다.<br>
<br>
<Br>

4. Systemd 서비스 단계<br>

systemd가 첫 번째 프로세스로 실행된 후, 핵심 서비스와 데몬이 활성화됩니다.<br>
초기 프로세스인 init과의 호환성도 여전히 유지됩니다.<br>

init = 모든 프로세스의 조상 역할, 현대는 systemed로 대체 <br>
<br>
<br>
vi /etc/inittab<br>

init + 런레벨 = 시스템 상태 즉시 변경<br>
      (0 ~ 6)
init 0 = poweroff<br>
init 6 = reboot<br>



<br>
<br>

![image break](../Pictur/step13/GRUB.2.png)<br>

로그인 프롬포트 화면, 부팅 과정 완료<br>
<br>
<Br>


vi /etc/grub.d/00_header
cat << EOF
set superusers="mylinux"
password mylinux 1234
EOF

적용
grub2-mkconfig -o /boot/grub2/grub.cfg


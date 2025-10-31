**Quota<br>
<Br>
정해진 한도<br>
<Br>


Systemed가 데몬(daemon)을 시작합니다. quota도 systemd가 관리하는 하나의 데몬입니다.<br>
<br>
<Br>

usrquota : 개별 사용자의 쿼터 제한할 수 있는 속성<br>
qrpquota : 개별 그룹의 쿼터 제한할 수 있는 속성<br>



vi /etc/fstab 

(defaults,usrjquota=aquota.user,jqfmt=vfsv0  1  2)
usrjquota=aquota.user → 사용자 쿼터 파일 이름 지정

jqfmt=vfsv0 → 쿼터 포맷 지정 (Linux용 최신 형식)

/etc/fstab에 위 옵션을 추가해야 쿼터 기능이 활성화됨




UUID=xxxx-xxxx  /home  ext4  defaults  1  2

UUID=xxxx-xxxx  /home  ext4  defaults,usrjquota=aquota.user,jqfmt=vfsv0  1  2

#####################
quotacheck -augmn

quotacheck: 쿼터용 데이터베이스(즉, aquota.user, aquota.group) 생성

옵션 의미:

-a: /etc/mtab에 기록된 모든 파일시스템 점검
-m: 마운트 해제하지 않음
-n: 파일시스템을 실제 수정하지 않음 (단순 점검)

######################
quotaon -avug
quotaon: 쿼터 기능 활성화

-a: 모든 파일시스템
-v: 상세 출력

######################
quotaoff -avug
quotaoff: 쿼터 기능 비활성화


#######################

UUID="73e62b26-8ae6-4d04-921c-831c55c3faa9"  /home3  xfs  defaults,uquota,gquota  0  0
/home3 파티션에 XFS용 쿼터 기능을 활성화

uquota: 사용자 쿼터

gquota: 그룹 쿼터
→ usrjquota, jqfmt는 ext4용이라 XFS에서는 사용 안 함

📌 수정 후 반드시 재마운트

bash
코드 복사
mount -o remount /home3



xfs_quota -x /home3
-x: 관리자 모드(확장 명령 사용 가능)

/home3: 쿼터 적용할 파일시스템 경로



📊 3️⃣ 상태 확인
state


→ /home3 파일시스템에 사용자/그룹 쿼터가 활성화되어 있는지 확인
📈 4️⃣ 현황 보기
report -h


→ 현재 각 사용자/그룹의 디스크 사용량과 제한(soft/hard) 표시
(-h: human-readable, 단위 보기 좋게 표시)


🚫 5️⃣ 사용자별 제한 설정
limit bsoft=1G bhard=2G quota3


limit: 쿼터 설정 명령

bsoft: 소프트 제한 (1GB 넘으면 경고)

bhard: 하드 제한 (2GB 넘으면 저장 불가)

quota3: 사용자 이름

✅ 결과 →
quota3 사용자는 /home3 파티션에 최대 2GB까지만 파일 저장 가능


################################

SCSI 디스크 50G 1개를 /qhome1 마운트하시오.

2명의 유저에게 다음을 구성하시오.

xfs로 /qhome1에 마운트
4gluser1 블록 소프트 30M 하드 50M
4gluser2 블록 소프트 100M 하드 500M

이후 /etc/fstab에 등록 시 반드시 장치명이 아닌 해당 파티션의 UUID로 등록하시오.

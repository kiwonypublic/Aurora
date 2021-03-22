# Aurora의 다양한 기능을 살펴 봅니다.

## Backup & Recovery

**Aurora MySQL은 5분 주기 자동 Backup 기능을 제공 합니다.**
**실습에서는 Manual Backup과 복구를 해보도록 하겠습니다.**
**Manual Backup의 경우 별도로 삭제 하지 않을 경우 Data가 영구 저장 되기 때문에, Compliance 목적으로 사용 가능합니다.**
**Manual Backup을 이용하여 개발, 테스트 시스템을 구성 가능하며 Migration 용도도 가능합니다.**

1. Services => RDS => Databases

2. auroralab-mysql-node-1 선택 후 Actions => Take Snapshot

   <kbd> ![GitHub Logo](images/21.png) </kbd>
   <kbd> ![GitHub Logo](images/22.png) </kbd>
   <kbd> ![GitHub Logo](images/23.png) </kbd>

3. Snapshot status "Available" 확인

4. Backup Snapshot 선택 후 "Restore snapshot 수행"
   <kbd> ![GitHub Logo](images/24.png) </kbd>

5. N

bookchat module 분리
1. 우선 현재 각 의존성 유지한채로 java로 분리
2. 분리한 각 모듈의 버전 관련 정보 gradle.properties로 통일
3. 분리 이후 배포 프로세스 변경 
4. core-db, support-logging, core-broker 모듈 분리

---

- [ ] 채팅방 정보수정 api 문서 http 요청 추가
- [ ] 채팅방 정보수정 api 버그(?) 수정
- [ ] 사용자 정보 조회 api 수정
- [ ] 채팅방 퇴장시 chatId, dispatchTime, targetUserId null로 fcm 발송되는거 확인
- [ ] 
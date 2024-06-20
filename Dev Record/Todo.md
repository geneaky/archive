bookchat module 분리
1. 우선 현재 각 의존성 유지한채로 java로 분리
2. 분리한 각 모듈의 버전 관련 정보 gradle.properties로 통일
3. 분리 이후 배포 프로세스 변경 
4. core-db, support-logging, core-broker 모듈 분리

---

- [ ] 내 방식대로 클린아키텍처 구현
	- [ ] interface사용도 추상화 비용이 있음
		- [ ] service layer에서 in/out port로 사용되는 파라미터나 응답 값에 대한 in/out port로 지정하는건 강결합을 끊어낼 수 있어서 좋다고 생가함
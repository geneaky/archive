bookchat module 분리
1. 우선 현재 각 의존성 유지한채로 java로 분리
2. 분리한 각 모듈의 버전 관련 정보 gradle.properties로 통일
3. 분리 이후 배포 프로세스 변경 
4. core-db, support-logging, core-broker 모듈 분리

---

- [ ] 내 방식대로 클린아키텍처 구현
	- [ ] interface사용도 추상화 비용이 있음
		- [ ] service interface(usecase)로 대체될 새로운 구현체가 생기기 전까지는 interface로 뽑지 않아도 괜찮다고 생각함
	- [ ] service layer에서 사용되는 파라미터나 응답 값에 대한 in/out port로 지정하는건 강결합을 끊어낼 수 있어서 좋다고 생각함
		- [ ] in은 command/query로 구분
		- [ ] out은 도메인을 반환해도 괜찮고 별도로 만들어도 괜찮은듯
			- [ ] 도메인을 외부로 내보내도 getter정도만 접근 권한을 주면 도메인을 보존할 수 있다고 생각하고, 도메인 내부에서 외부 어떤 값에도 의존하고 있지 않도록 제한을 둔다면 오히려 가장 이해하기 쉬운 도메인이라는 클래스가 여기저기 사용되는게 좋은게 아닌가? -> 요건 일단 고민중
	- [ ] controller에서 사용되는 request/response는 api명세로 가장 변화가 많은 부분이니 이부분도 별도로 뽑아서 사용

``` java
//trx start
try {
	transfer.success();
	conn.commit();
}catch() {
}
//trx end
try {

}
firm_bank_api_call();

```
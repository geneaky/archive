 mysql - java data type mapping : [참고](https://dev.mysql.com/doc/connector-j/en/connector-j-reference-type-conversions.html)
- jpa column converter
- jpa column default : [참고](https://gksdudrb922.tistory.com/279)
- entitymanager flush, clear vs jpa repository flush
- jpa persistence context를 mybatis가 공유하지 못함에 대하여
- https://mycup.tistory.com/425 
- repeatable_read transaction에서 주의 할점 -> read_committed로 변경 해서 해결한 부분
- https://docs.spring.io/spring-boot/docs/current/reference/html/application-properties.html datasource 등록시
- spi pattern
- component 조합으로 비즈니스 로직 구성
	- query형 feature의 경우 특정 화면에 fit한 응답 데이터가 많기 때문에 component로 뽑아도 재사용성이 높지 않음
		- 그래서 entity나, 비즈니스 객체를 반환하는 경우에만 query component에 명시
	- command형 feature의 경우 재사용성이 높고 의미를 내포하기 더 쉽고 간결해져서 자주 사용했음
	-  서로 다른 domain feature 사용시에는 핵심 도메인 service로 통신
- timezone
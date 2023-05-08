
repository interface에 메서드를 jpa에서 정한 규칙대로 작성했을때 구현을 jpa가 해주는 것인데 
이게 entity내부 필드에 매핑된 연관 entity가 있고 이 entity의 id를 사용해서 query method의 파라미터로 작성하는 경우 쿼리가 날아가는 시점에 left join이 걸리며 fetch join을 진행하게된다.


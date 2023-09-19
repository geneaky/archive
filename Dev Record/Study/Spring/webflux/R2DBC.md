
#### 1.1 R2DBC 이전
전통적인 방식의 JDBC(Java Database Connectivity) 드라이버는 하나의 커넥션에 하나의 스레드를 사용하는 Thread Per Connection 방식이다.
> Thread Per Connection 방식은 데이터베이스로 부터 응답을 받기 전까지 스레드가 블로킹이된다.
> 높은 처리량과 대규모 애플리케이션을 위해 비동ㄱ
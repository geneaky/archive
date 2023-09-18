
리액티브 프로그램의 표준 API 사양을 말한다.
`비동기 데이터 스트림`과 `논-블로킹 백프레셔`에 대한 사양을 제공한다.

리액티브 스트림은 TCK(Technology Compatibility Kit)을 지원하기 때문에 라이브러리가 정해진 사양에 맞게 구현되었는지 보장할 수 있다.
	라이브러리가 정해진 사양에 맞게 구현되었는지 보장하기 위해 만들어진 테스트 도구


#### Reactive Stream 구현체들

- Project Reactor
- RxJava
- Akka Streams
- Vert.x



#### reactive stream interface

| 인터페이스   | 설명                                      |
| ------------ | ----------------------------------------- |
| Publisher    | 데이터를 생성하고 구독자에게 통지         |
| Subscriber   | 데이터를 구독하고 통지 받은 데이터를 처리 |
| Subscription | Publisher, Subscriber간의 데이터를 교환하도록 연결하는 역할을 하며 전달받ㅇ                                          |

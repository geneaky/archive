
@EnableAsnyc를 통해 해당 애네터이션을 사용한 비동기 처리 방식을 설정한다.

public 메서드에 붙여 해당 메서드의 태스크를 비동기로 처리할 수 있다.

별도의 thread pool를 생성하지 않으면 기본 동작 방식인 `SimpleAsyncTaskExecutor` 를 사용해서 동작

#### SimpleAsyncTaskExecutor

- 각 작업마다 새로운 스레드를 생성하고 비동기 방식으로 동작
- concurrencyLimit 프로퍼티를 사용해서 요청 수 제한 (default는 unlimit)
- 스레드를 재사요하지 않아서 스레드 생성, 작업할당에 오버헤드가 있음


@Async 애너테이션 안에 threadPoolExecutor의 이름을 지정하여 해당 threadPool을 사용하여 비동기 동작하도록 할 수 있다


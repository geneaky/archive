
java로 코드를 작성할때 try-catch를 상당히 많이 사용하는데 이 try-catch문에서 발생하는 퍼포먼스 문제에 대해 알아보았다.

[참고 링크](https://www.baeldung.com/java-exceptions-performance)

비교 상황
1 예외가 발생하지 않은 상황
2 예외를 던지고 잡는 상황
3 예외를 던지는 상황
4 에외를 던지고 잡지만 예외를 Stack Trace에 포함시키지는 않는 상황
5 예외를 던지고 잡아서 Stack Trace를 풀어보는 상황

``` java
Benchmark                                                 Mode  Cnt    Score   Error  Units
ExceptionBenchmark.createExceptionWithoutThrowingIt       avgt   10   16.605 ± 0.988  ms/op
ExceptionBenchmark.doNotThrowException                    avgt   10    0.047 ± 0.006  ms/op
ExceptionBenchmark.throwAndCatchException                 avgt   10   16.449 ± 0.304  ms/op
ExceptionBenchmark.throwExceptionAndUnwindStackTrace      avgt   10  326.560 ± 4.991  ms/op
ExceptionBenchmark.throwExceptionWithoutAddingStackTrace  avgt   10    1.185 ± 0.015  ms/op
```

예외가 발생하지 않은 상황은 당연히 속도가 가장 빨르다.

예외를 던지고 잡는 상황과, 던지기만한 상황을 비교해보면 둘의 수행시간이 비슷하다 -> 잡는 곳에서 발생하는 퍼포먼스 저하는 미미하다 -> 생성하고 해당 예외를 stack trace에 추가하는 과정에서 퍼포먼스 저하가 발생하는 것으로 jvm 옵션을 주어 스택을 살펴보고 해당 프레임에 예외를 추가하는 행위를 막으니 실행시간이 다시 감소한다.(즉,예외를 스택 추적하는 경우도 성능 저하가 발생할 수 있음)




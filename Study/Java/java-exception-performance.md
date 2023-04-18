
java로 코드를 작성할때 try-catch를 상당히 많이 사용하는데 이 try-catch문에서 발생하는 퍼포먼스 문제에 대해 알아보았다.

[참고 링크](https://www.baeldung.com/java-exceptions-performance)

비교 상황
1 예외가 발생하지 않은 상황
2 예외를 만들어서 던지는 상황
3 예외를 만들고 던지지 않는 상황
4 에외를 던지고 잡지만 예외를 Stack Trace에 포함시키지는 않는 상황
5 예외를 던지고 잡아서 Stack Trace를 풀어보는 상황

``` java
```

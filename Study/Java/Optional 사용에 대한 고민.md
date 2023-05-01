
java에서 optional은 null이 아닌 값을 포함하거나 포함하지 않는 container object인데 
값이 있으면 isPresent()같은 멤버 메서드를 통해 값이 존재할 경우 값을 return 받는 등의 방식으로 사용할 수 있다.

- empty() : 값이 없다는 것을 표현하기 위한 optional
- of(): non-null value에 대한 표현을 위한 optional(null일시 NPE)
- ofNullable(): null일수도 있는 value에 대한 표현을 위한 optional

이러한 optional를 사용하는 것에 대한 비용이 발생하는 것도 무시하지 못하기 때문에 어느 상황에서 사용할지에 대해 고민이된다.

#### 풀고자 하는 문제가 무엇인가? 

optional은 자바 에서 NPE를 감소시키기 위한 시도임
> 좀 더 API의 표현력을 올려서 때때로 값이 없음을 반환하는 것에 대한 표현력


#### 풀고자 하는 문제가 아닌것은?

모든 타입의 null pointer들을 피하기 위한 메커니즘을 의미하는 것이 아니다.

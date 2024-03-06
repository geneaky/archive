모든 특정한 [[Condition]]들에 부합하여 등록되는 적절한 컴포넌트를 가리키기 위해 사용한다
Condition을 구현한 구현체를 인자로 받으며 해당 구현채의 match()의 결과가 true인 경우 빈으로 등록된다.

@Component, @Configuration 애너테이션과 함께 사용할 수 있으며,
@Configuration과 함께 사용할 경우 @Bean이 등록된 메서드, @Import, @ComponentScan에 지정되는 클래스 모두 Condition이 적용된다.

@Conditional을 @Inherited를 메타 에너테이션으로 소유하지 않기 때문에 상속해서 사용할 수 없다.

![[Pasted image 20240306122248.png]]

![[Pasted image 20240306122308.png]]




![[Pasted image 20240306122415.png]]
서버가 계속해서 죽고있다.

서버 메트릭을 확인해본다.

![[Pasted image 20231118211509.png]]

jvm_threads_live_threads metric이 의미하는 바는 뭘까?

참고 : [[jvm_thread]] 에 관하여

해당 메트릭은 daemon thread와 normal thread 둘 다를 합친 live thread를 의미한다

위 메트릭을 보면 33개의 thread가 기본적으로 live 상태이고 추가로 33~35 총 2개의 thread가 생겼다 반환되었다를 반복하다가 서버가 죽은 것을 확인할 수 있다

그렇다면 이시각 deamon thread의 개수는?

![[Pasted image 20231118213519.png]]

24~ 26개를 오가고 있었다.

그렇다면 9개의 normal thread가 최대치일때 동작하고 있었다는 의미가 된다.

이시각 로그도 한 번 확인해보자

![[Pasted image 20231118214507.png]]

위 로그가 서버가 죽기전 마지막 로그인데 의심할만한 부분을 자세히 보자

jvm_gc_memory_allocated_bytes 이게 뭘까?

jvm gc발생 이후 heap의 young, eden 영역들을 sweep한 이후 jvm의 메모리 영역에 추가 여유분이 할당된 크기를 나타낸다

그렇다면 gc를 확인해보자


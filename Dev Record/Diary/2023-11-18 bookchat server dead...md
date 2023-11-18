서버가 계속해서 죽고있다.

서버 메트릭을 확인해본다.

![[Pasted image 20231118211509.png]]

jvm_threads_live_threads metric이 의미하는 바는 뭘까?

참고 : [[jvm_thread]] 에 관하여

해당 메트릭은 daemon thread와 normal thread 둘 다를 합친 live thread를 의미한다

위 메트릭을 보면 33개의 thread가 기본적으로 live 상태이고 추가로 33~35 총 2개의 thread가 생겼다 반환되었다를 반복하다가 서버가 죽은 것을 확인할 수 있다


서버가 계속해서 죽고있다.

서버 메트릭을 확인해본다.

![[Pasted image 20231118211509.png]]

jvm_threads_live_threads metric이 의미하는 바는 뭘까?

참고 : [[jvm_thread]] 에 관하여

해당 메트릭은 daemon thread와 normal thread 둘 다를 합친 live thread를 의미한다


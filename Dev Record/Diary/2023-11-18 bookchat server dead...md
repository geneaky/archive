서버가 계속해서 죽고있다.

서버 메트릭을 확인해본다.

![[Pasted image 20231118211509.png]]

jvm_threads_live_threads metric이 의미하는 바는 뭘까?

thread는 deamon thread, normal thread로 두 종류가 있다.

jvm이 시작되면 생성되는 모든 thread는 main thread를 제외하고 모두 deamon thread이다. (역)


##### proto buffers
구글에서 개발한 이진 직렬화 포맷으로 플랫폼과 언어에 독립적이다.
다양한 언어와 시스템에 효율적으로 전송하기위해 사용한다.
작은 메시지 크기, 빠른 직렬화/역직렬화 속도, 타입 안전성 제공한다.

[protocol buffers docs](https://protobuf.dev/overview/#work)

protobuf를 사용해보면서 장점을 확인해보자.

##### project gradle config

우선 protobuf 의존성을 가져오기 위해 buildscript에 별로로 google() respository를 등록해주고 플러그인 의존성을 받아와서 등록해준다.

![[Pasted image 20231126212900.png]]



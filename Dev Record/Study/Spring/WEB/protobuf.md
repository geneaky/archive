##### proto buffers
구글에서 개발한 이진 직렬화 포맷으로 플랫폼과 언어에 독립적이다.
다양한 언어와 시스템에 효율적으로 전송하기위해 사용한다.
작은 메시지 크기, 빠른 직렬화/역직렬화 속도, 타입 안전성 제공한다.

[protocol buffers docs](https://protobuf.dev/overview/#work)

protobuf를 사용해보면서 장점을 확인해보자.

##### project gradle config

우선 protobuf 의존성을 가져오기 위해 buildscript에 별로로 google() respository를 등록해주고 플러그인 의존성을 받아와서 등록해준다.

![[Pasted image 20231126212900.png]]

![[Pasted image 20231126213037.png]]

이제 실제 개발에서 필요한 java 의존성을 추가해주고 빌드 과정에서 main/test에서 사용하게될 protofile의 위치를 source set으로 지정해준다.

build시에 task를 등록해야하는데 proto file에 작성한 내용을 protoc compiler를 사용해서 java 언어로 생성하겠다는 의미이다

이렇게 작성하면 gradle task에 generateProto가 생성이된다.

![[Pasted image 20231126213329.png]]

응답으로 사용할 message를 .proto파일에 명시해준 후

![[Pasted image 20231126213406.png]]

proto 생성 task를 실행시켜주면 

![[Pasted image 20231126213454.png]]

build결과 디렉토리 하위 generated폴더에 위 이미지처럼 proto file의 이름과 동일한 
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

build결과 디렉토리 하위 generated폴더에 위 이미지처럼 proto file의 이름과 동일한 이름의 클래스가 생성이 된다.


#### 성능 차이?

![[Pasted image 20231126213634.png]]

100만개의 데이터를 각각 proto와 jackson을 사용해 직렬화/역직렬화 해본다.

테스트 결과는 protobuf를 역/직렬화했을때 속도가 2배이상 빨랐고, 직렬화 결과로 나타나는 바이트 결과도 jackson 직렬화 결과가 더 많았다.

protobuf는 데이터를 직렬화할때 binary format을 사용하기 때문에 json과 비교했을때 결과물이 더 작다.

#### gRPC가 아닌 HTTP환경에서 resposne로 사용하기에 적합한가?

protobuf를 회사 신규 프로젝트에서 응답 스펙을 명시해서, 생성하면 관리가 용이하고 dto생성이 편할것이라는 의견이 있었서 http response로 사용하기에 적합한가에 대해 고민해볼 필요가 이
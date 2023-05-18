
websocket connection을 위해 설정해둔 url로 요청이오면 dispatcher servlet이 WebSocketHttpRequestHandler에게 처리를 요청함

WebSocketHttpRequestHandler는 DefaultHandshakeHandler를 사용해서 http -> websocket으로 프로토콜 변경을 위한 핸드쉐이킹을 진행한다 

핸드쉐이킹이 성공적으로 끝나면 등록된 핸드쉐이크 인터셉터들을 순환하며 인터셉터에서 처리를 함
이것들 모두 다 끝나면 StandardWebSocketSession이라는게 생성됨

client <- StandardWebSocketSession -> server

이후 DefaultStompSession 객체로 브로커와 stomp session이 수립이 된다. 

client <- StandardWebSocketSession -> server <- DefaultStompSession -> broker
이런 구조에서 동작을 하게된다.

클라이언트와 서버가 stomp 세션을 맺으면 일단 websocket session또한 가지고 있을 텐데 websocket을 통해 전달받은 메시지를 브로커로 보내고나서 성공적으로 보냈다는 응답을 reciept로 받는지에 대한 테스트가 필요. >> DefaultStompSession에서 send 이후 send에 대한 결과를 Receiptable이란 객체로 받을 수 있는데 이 값은 비동기적으로 send에 대한 응답을 받았을때 callback 메서드로 보낸 메시지가 정상적으로 전달되었을때 에 대한 처리를 작성할 수 있는데 session에서 autoReciept를 true로 한경우는 내부적으로 atomic integer값을 사용해서 receiptId를 할당한다. -> 이 증가 여부를 통해 3이라는 reciept를 받는다면 2,1이라는 이전 reciept는 서버에 정상적으로 전달 받았다는 것을 의미한다. [stomp-protocol-receipt](https://stomp.github.io/stomp-specification-1.2.html#RECEIPT)
이값 지정되어 있어도 native haeder에 별도로 reciept를 지정한 경우 해당 값이 receiptId로 전달받게되는데 이 값을 받았는지 여부로 부가적인 처리가 가능하다.
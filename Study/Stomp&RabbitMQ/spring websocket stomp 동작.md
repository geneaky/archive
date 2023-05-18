
websocket connection을 위해 설정해둔 url로 요청이오면 dispatcher servlet이 WebSocketHttpRequestHandler에게 처리를 요청함

WebSocketHttpRequestHandler는 DefaultHandshakeHandler를 사용해서 http -> websocket으로 프로토콜 변경을 위한 핸드쉐이킹을 진행한다 

핸드쉐이킹이 성공적으로 끝나면 등록된 핸드쉐이크 인터셉터들을 순환하며 인터셉터에서 처리를 함
이것들 모두 다 끝나면 StandardWEbSocketSession이라는게 생성되고 